---
title: How To Setup Stripe Elements Payment Form
date: 2019-03-18 10:30:00
tags: [Stripe, Elements, Payments, HandlebarsJS, ExpressJS]
---

The easiest way to process payments with Stripe is to just use Checkout. I've already written [a post here on how to setup Stripe Checkout to process one-time payments](https://blog.stevelongoria.net/2019/02/26/setup-stripe-checkout-using-expressjs-heroku/) and another post [here](https://blog.stevelongoria.net/2019/03/12/setup-recurring-payments-subscriptions-stripe-checkout/) on how to process automatically recurring payments here.

The only downside to Stripe Checkout in my opinion, is that you can't customize the look and feel of the Stripe Checkout overlay that pops up:

<center>{% asset_img stripecheckoutoverlay.png Stripe Checkout Overlay %}</center>

Some would argue this is a good thing as consumers like the familiar design of the Stripe Checkout overlay and trust it most, but I'm a stickler for cohesive design so I rather the checkout match the look and feel of my site.

Thankfully, Stripe has something called [Stripe Elements](https://stripe.com/payments/elements) which allows you to have a lot more control in designing your payment form.

You can see my final Stripe Elements payment form deployed to Heroku [here](https://secure-lake-20277.herokuapp.com/). You can [test it using the Stripe test cards](https://stripe.com/docs/testing#cards) if you want!

I believe it looks more professional and I don't think having Stripe Checkout would significantly increase your sales conversions, in fact you may find that Stripe Elements converts better. You can always perform an a/b test to find out what works best for your business!

You can view some great examples of Stripe Elements payment forms along with the source code [here](https://stripe.dev/elements-examples/).

I snagged the code from the [first example](https://github.com/stripe/elements-examples/#example-1) and wired it up to my express.js app, the same one I walk you through setting up [here](https://blog.stevelongoria.net/2019/02/26/setup-stripe-checkout-using-expressjs-heroku/).

I'll walk you through the set up if you've already gone through this post to setup your Express.js backend.

**Note: The Express.js app for the Stripe Elements payment form is using HandlebarsJS instead of Pug FYI. I had issues setting up the view using Pug, which is why I ended up using HandlebarsJS. When setting up your Express.js app you'd just set the templating language to HandlebarsJS (hbs) instead of Pug using this command:**

{% codeblock %}

$ express --view=hbs myapp

{% endcodeblock %}


## Step 1: Create main.js file

Enter the following command in terminal to create our main.js file:

{% codeblock %}

$ touch public/javascripts/main.js

{% endcodeblock %}

## Step 2: Open that file in your text editor and paste the code found here.

{% codeblock lang:javascript %}

var stripe = Stripe('pk_test_yourteststripepublishkey');
var elements = stripe.elements();

// Custom styling can be passed to options when creating an Element.
var style = {
  base: {
    color: '#32325d',
    lineHeight: '18px',
    fontFamily: '"Montserrat", Helvetica, sans-serif',
    fontSmoothing: 'antialiased',
    fontSize: '16px',
    '::placeholder': {
      color: '#aab7c4'
    }
  },
  invalid: {
    color: '#fa755a',
    iconColor: '#fa755a'
  }
};

// Create an instance of the card Element.
var card = elements.create('card', {style: style});

// Add an instance of the card Element into the `card-element` <div>.
card.mount('#card-element');

card.addEventListener('change', function(event) {
  var displayError = document.getElementById('card-errors');
  if (event.error) {
    displayError.textContent = event.error.message;
  } else {
    displayError.textContent = '';
  }
});

// Create a token or display an error when the form is submitted.
var form = document.getElementById('payment-form');
form.addEventListener('submit', function(event) {
  event.preventDefault();

  stripe.createToken(card).then(function(result) {
    if (result.error) {
      // Inform the customer that there was an error.
      var errorElement = document.getElementById('card-errors');
      errorElement.textContent = result.error.message;
    } else {
      // Send the token to your server.
      stripeTokenHandler(result.token);
    }
  });
});

function stripeTokenHandler(token) {
  // Insert the token ID into the form so it gets submitted to the server
  var form = document.getElementById('payment-form');
  var hiddenInput = document.createElement('input');
  hiddenInput.setAttribute('type', 'hidden');
  hiddenInput.setAttribute('name', 'stripeToken');
  hiddenInput.setAttribute('value', token.id);
  form.appendChild(hiddenInput);

  // Submit the form
  form.submit();
}

{% endcodeblock %}

## Step 3: Open the style.css file in your text editor and replace the contents with the following: 

{% codeblock lang:css %}

body {
	font-family: 'Montserrat', Helvetica, sans-serif;
}

.StripeElement {
  background-color: white;
  width: 355px;
  height: 20px;
  margin: 10px 0 0 0;
  padding: 10px 12px;
  border-radius: 4px;
  border: 1px solid transparent;
  box-shadow: 0 1px 3px 0 #e6ebf1;
  -webkit-transition: box-shadow 150ms ease;
  transition: box-shadow 150ms ease;
}

#name {
	background-color: white;
	font-family: 'Montserrat', Helvetica, sans-serif;
  width: 300px;
  height: 10px;
  color: #21212d;
  font-size: 16px;
  line-height: 18px;
  padding: 10px 12px;
  margin: 50px 0 10px 0;
  border-radius: 4px;
  border: 1px solid transparent;
  box-shadow: 0 1px 3px 0 #e6ebf1;
  -webkit-transition: box-shadow 150ms ease;
  transition: box-shadow 150ms ease;
}

#email {
	background-color: white;
	font-family: 'Montserrat', Helvetica, sans-serif;
  width: 300px;
  height: 10px;
  color: #21212d;
  font-size: 16px;
  line-height: 18px;
  padding: 10px 12px;
  margin: 10px 0 30px 0;
  border-radius: 4px;
  border: 1px solid transparent;
  box-shadow: 0 1px 3px 0 #e6ebf1;
  -webkit-transition: box-shadow 150ms ease;
  transition: box-shadow 150ms ease;
}

.StripeElement—focus {
  box-shadow: 0 1px 3px 0 #cfd7df;
}

#name—focus {
  box-shadow: 0 1px 3px 0 #cfd7df;
}

#email—focus {
	  box-shadow: 0 1px 3px 0 #cfd7df;
}

.StripeElement—invalid {
  border-color: #fa755a;
}

.StripeElement—webkit-autofill {
  background-color: #fefde5 !important;
}

#checkout {
	display: flex;
	justify-content: center;
}

form {
	display: flex;
	flex-direction: column;
}

.form-row {
	display: flex;	
	flex-direction: column;
}

button {
	background-color: #d81e5b;
	border-radius: 3px;
	color: white;
	font-family: 'Montserrat', Helvetica, sans-serif;
	height: 40px;
	margin: 10px 0 0 0;
}

label {
	margin: 0 5px 0 0;
}

*:focus {
    outline: none;
}	

::placeholder { /* Chrome, Firefox, Opera, Safari 10.1+ */
    color: #dcdfe6;
    font-family: 'Montserrat', Helvetica, sans-serif;
}

{% endcodeblock %}

## Step 4: Under the views directory, open the layout.hbs file and [replace the contents with the code from here](https://github.com/SteveLongoria/stripe-elements/blob/master/views/layout.hbs).

## Step 5: Open up the index.hbs file and replace the contents with the following:

{% codeblock %}

<div id="checkout">
<form action="/charge" method="post" id="payment-form">
  <div class="form-row inline">
    <div class="col">
      <label for="name">
        Name
      </label>
      <input id="name" name="name" placeholder="Your name" required>
    </div>
    <div class="col">
      <label for="email">
        Email
      </label>
      <input id="email" name="email" type="email" placeholder="youremail@yourdomain.com" required>
    </div>
  </div>
  <div class="form-row">
    <label for="card-element">
      Credit or debit card
    </label>
    <div class=".StripeElement" id="card-element">
      <!— A Stripe Element will be inserted here. —>
    </div>

    <!— Used to display Element errors. —>
    <div id="card-errors" role="alert"></div>
  </div>

  <button>SUBMIT PAYMENT</button>
</form>
</div>

{% endcodeblock %}

## Step 6: Replace code in app.js

With our Stripe Checkout setup, we're only collecting credit card and email address from the customer. With the Stripe Elements setup, we're also collecting their name. One other change we're making is the Stripe publishable key is no longer in our app.js file, instead that is inserted in our front-end code (main.js). This leaves only the Stripe secret key in our app.js code. We're also setting HandlebarsJS as the view templating language instead of Pug. Lot's of stuff!

Just go ahead and replace the contents of your app.js with the following:

{% codeblock lang:javascript %}

var createError = require('http-errors');
var express = require('express');
var path = require('path');
var cookieParser = require('cookie-parser');
var logger = require('morgan');

var indexRouter = require('./routes/index');
var usersRouter = require('./routes/users');

const keySecret = process.env.SECRET_KEY;

var app = express();
var stripe = require("stripe")(keySecret);


// view engine setup
app.set('views', path.join(__dirname, 'views'));
app.set('view engine', 'hbs');
app.use(require("body-parser").urlencoded({extended: false}));


app.use(logger('dev'));
app.use(express.json());
app.use(express.urlencoded({ extended: false }));
app.use(cookieParser());
app.use(express.static(path.join(__dirname, 'public')));

app.use('/', indexRouter);
app.use('/users', usersRouter);

app.post("/charge", (req, res) => {
  let amount = 500;

  stripe.customers.create({
     email: req.body.email,
    source: req.body.stripeToken,
    description: req.body.name
  })
  .then(customer =>
    stripe.charges.create({
      amount,
      description: "Sample Charge",
         currency: "usd",
         customer: customer.id
    }))
  .then(charge => res.render("charge.hbs"));
});

app.listen(4567);

// catch 404 and forward to error handler
app.use(function(req, res, next) {
  next(createError(404));
});

// error handler
app.use(function(err, req, res, next) {
  // set locals, only providing error in development
  res.locals.message = err.message;
  res.locals.error = req.app.get('env') === 'development' ? err : {};

  // render the error page
  res.status(err.status || 500);
  res.render('error');
});

module.exports = app;

{% endcodeblock %}

## Step 7: Create your post payment page, for this guide we're going to call it charge.hbs:

{% codeblock %}

$ touch views/charge.hbs

{% endcodeblock %}

Go ahead and open charge.hbs in your text editor and add the following content to it:

{% codeblock %}

<h2> You successfully paid <strong>$5.00</strong>!</h2>

{% endcodeblock %}

That's it! Go ahead and deploy your app to Heroku, test and re-deploy with live Stripe keys [like explained in the original post here](https://blog.stevelongoria.net/2019/02/26/setup-stripe-checkout-using-expressjs-heroku/).

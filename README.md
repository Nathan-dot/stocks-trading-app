# Stocks Trading App

Simulates an investment platform built with the MERN stack and uses Socket.IO for real-time updates. This project is not intended to reflect real world stock performances.

**Stock**

This project uses [JSON](https://www.json.org/json-en.html) to represent stock data in the form of:

```json
[
  {
    "id": 0,
    "ticker": "String",
    "exchange": "String",
    "name": "String",
    "initialPrice": 0.00,
    "currentPrice": 0.00,
    "description": "String",
    "ipoDate": "String",
    "siteURL": "String",
    "industries": ["String", "String"],
    "icon": "URL",
    "favorited": true,
    "timesBought": 0
  }
]
```

The [schema](https://mongoosejs.com/docs/guide.html) of this model can be found in [`/backend/models/stock.js`](https://github.com/Nathan-dot/stocks-trading-app/blob/main/backend/models/stock.js)

## Developing

To run this application locally, you will need the following prerequisite programs:

- [Node.JS and NPM](https://nodejs.org/en/)
- [Create React App](https://github.com/facebook/create-react-app)
- [MongoDB](https://www.mongodb.com/)

**Back-End Setup**

First, install the necessary packages via:

```
npm i
```

Refer to the [`package.json`] in the [`/backend`](https://github.com/Nathan-dot/stocks-trading-app/tree/main/backend) directory for more information about what is being installed.

Then, setup the `.env` file in the root of the [`/backend`](https://github.com/Nathan-dot/stocks-trading-app/tree/main/backend) directory. (**Note**: this will be gitignored)

```bash
# for mongodb connection
MONGO_CONNECTION_STRING=mongo_secret_here

# for authentication via signing tokens
JWT_SECRET=jwt_secret_here

# for guest account login (mongo objectID)
GUEST_ID=guest_id_here
```

Now you can spin up the backend. Default port is `5000`.

```bash
# start server
node .

# explicit command
node index.js
```

**Front-End Setup**

First, install the necessary packages via:

```
npm i
```

Refer to the [`package.json`](https://github.com/Nathan-dot/stocks-trading-app/blob/main/frontend/package.json) in the [`/frontend`](https://github.com/Nathan-dot/stocks-trading-app/tree/main/frontend) directory for more information about what is being installed.

Then, setup the `.env` file in the root of the [`/frontend`](https://github.com/Nathan-dot/stocks-trading-app/tree/main/frontend) directory. (**Note**: this will be gitignored) Also see that `REACT_APP_GUEST_EMAIL` and `REACT_APP_GUEST_PASS` take [base64](https://en.wikipedia.org/wiki/Base64) encoded strings. You can easily encode your credentials using this [site](https://www.base64encode.org/) or with the [btoa()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/btoa) function.

```bash
# backend connection to REST API
REACT_APP_STOCKS_API=api_url

# email of the guest account (encoded)
REACT_APP_GUEST_EMAIL=base64_encoded_string

# password of the guest account (encoded)
REACT_APP_GUEST_PASS=base64_encoded_string
```

Now you can spin up the frontend. Default port is `3000` for a [create-react-app](https://github.com/facebook/create-react-app) project.

```bash
# start react app
npm start
```

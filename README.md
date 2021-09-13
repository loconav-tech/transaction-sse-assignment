# Transaction Management Frontend

Your task is to **build a React app** that:

1. Integrates with the provided Transaction Management API to create and show transaction/account data.
2. Makes the provided E2E tests pass.
3. Pipeline - a test Runner that executes the Cypress tests on push to a branch other than master/main

Here's the mockup with hints:

![Transaction Management Frontend](https://user-images.githubusercontent.com/1162212/116609549-cbf29b80-a934-11eb-876e-6d5c20061f13.png)

Feel free to define the UI, but please ensure that the following is in place.

#### The form for submitting transactions

```html
<form data-type="transaction-form">
  <input data-type="account-id" ... />
  <input data-type="amount" ... />
</form>
```

Both input **fields should be cleared** after the form is submitted.

#### The transaction list

Every newly submitted transaction should go on **the top of the list** and should have an enclosing `<div />` with the following structure:

```html
<div 
     data-type="transaction"
     data-account-id="${transaction-account-id}"
     data-amount="${transaction-amount}"
     data-balance="${current-account-balance}" ...>
  ...
</div>
```

- `${transaction-account-id}` - account id of the corresponding transaction.
- `${transaction-amount}` - transaction amount.
- `${current-account-balance}` - the current account balance right after submitting the transaction (only needed to be initialized for the transactions submitted from the current client).

## Before you get started

#### Boilerplate

We have pre-uploaded Create-React-App boilerplate in the repo.

#### Get familiar with the API

<details>
<summary>Request examples</summary>

##### Get historical transactions

```
GET https://infra.devskills.app/api/transaction-management/transactions
```

##### Create a new transaction

```
POST https://infra.devskills.app/api/transaction-management/transactions
Content-Type: application/json

{
  "account_id": "0afd02d3-6c59-46e7-b7bc-893c5e0b7ac2",
  "amount": 7
}
```

##### Get a transaction by id

```
GET https://infra.devskills.app/api/transaction-management/transactions/7c94635a-40a3-4c87-888a-42c3ce5b9750
```

##### Get an account by id

```
GET https://infra.devskills.app/api/transaction-management/accounts/0afd02d3-6c59-46e7-b7bc-893c5e0b7ac2
```

</details>

#### Try running the E2E tests locally

```bash
npm install
# Run your app here
npm run test
```

## What we expect from you

1. Make the provided E2E tests pass.
2. Implement client-side validation of the form data.
3. Implement error handling for the cases when the API cannot be reached or returns a server error.
4. Ensure that the app remains responsive (i.e. doesn't block the UI) while the data is being loaded.
5. Add instructions that describe how you've made the app responsive.
6. Unit test one module of choice. There is no need to test the whole app, as we only want to understand what you take into consideration when writing unit tests.
7. Avoid duplication and extract re-usable modules where it makes sense. We want to see your approach to creating a codebase that is easy to maintain.
8. Push your code to the new `implementation` branch. We encourage you to commit and push your changes regularly as it's a good way for you to showcase your thinking process.
9. Create a new pull request, but please **do not merge it**.
10. Await further instructions from the hiring team.

## Need help?

Start with [Troubleshooting](https://www.notion.so/Troubleshooting-d18bdb5d2ac341bb82b21f0ba8fb9546), and in case it didn't help, create a new GitHub issue. We'll get back to you.

## Time estimate

About **8 hours**.

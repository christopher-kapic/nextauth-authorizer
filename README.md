# Next-Auth with Authorizer

This repo was created to help debug using Authorizer oauth with Next-Auth.

### Helpful resources

- [Adding a custom oauth provider in Next-Auth](https://next-auth.js.org/configuration/providers/oauth#using-a-custom-provider)
- [Authorizer API endpoints](https://docs.authorizer.dev/core/endpoints)

To get started, run the following commands:

`git clone https://github.com/christopher-kapic/nextauth-authorizer.git`

`cd nextauth-authorizer`

`cp .env.example .env`

Edit the environment variables in `.env` to match your authorizer instance.

```
AUTHORIZER_CLIENT_ID="authorizer-client-id"
AUTHORIZER_CLIENT_SECRET="authorizer-client-secret"
AUTHORIZER_CLIENT_URL="https://demo.authorizer.dev"
```

`npm install; npx prisma db generate; npx prisma db push;`

`npm run dev`

Navigate to the [sign in page](http://localhost:3000/api/auth/signin) and try signing in with Authorizer.

You can see the frontend logs in the web browser console, and the backend logs in the terminal.

The error I was getting was `LinkAccountError`:

```
Unknown arg `roles` in data.roles for type AccountUncheckedCreateInput. Did you mean `type`? Available args:
type AccountUncheckedCreateInput {
  id?: String
  userId: String
  type: String
  provider: String
  providerAccountId: String
  refresh_token?: String | Null
  access_token?: String | Null
  expires_at?: Int | Null
  token_type?: String | Null
  scope?: String | Null
  id_token?: String | Null
  session_state?: String | Null
}
```
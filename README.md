This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.js`. The page auto-updates as you edit the file.

[API routes](https://nextjs.org/docs/api-routes/introduction) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.js`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/api-routes/introduction) instead of React pages.


## How to use AWS-Location and Amplify.

First you need to install AWS-SDK Cli in your system which you can find here https://docs.aws.amazon.com/cli/v1/userguide/install-macos.html . Make sure to setup environment path variables and configure aws-sdk with your access_key_id and secret_key in your cli.

After this install aws-amplify in your system.
To do so follow installation steps on https://docs.amplify.aws/cli/start/install/.

Using "amplify console auth" command you'll be redirected to cognito pool of aws where you can get your applications auth and unauth names.
- Now, go to IAM -> Roles and select the auth role of your amplify.
- Create a new inline policy inside permissions.
- Copy the below permission:- 
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": "geo:GetMap*",
            "Resource": "arn:aws:geo:<REGION>:<ACCOUNTNUMBER>:map/<NAMEOFMAP>"
        }
    ]
}
- Also in cognito pool under amplify app check the unauthorized access box.

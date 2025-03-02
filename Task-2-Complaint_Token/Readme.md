# KYC Complaint Token:

## Create leo Project:
- Command:
    ```sh
    leo new saugatstha_kyc_complaint_token
    ```

## Install dependencies:
- Command:
    ```sh
    cd saugatstha_kyc_complaint_token
    leo add token_registry
    leo add credits
    ```

## Compiled Program:
- Command:
    ```sh
    leo build
    ```

## Deploy to testnet:
- Value of Endpoint must be changed with: `https://api.explorer.provable.com/v1` in `.env` file.
- Now, the value of `PRIVATE_KEY` in `.env` must be replaced.
- We will require some token to deploy our program into testnet.

- Command:
    ```sh
    leo deploy --network testnet -y
    ```
    
    <details><summary> Detailed Output </summary><blockquote>

    ~~~sh
       Leo ✅ Compiled 'saugatstha_kyc_complaint_token.aleo' into Aleo instructions
    📦 Creating deployment transaction for 'saugatstha_kyc_complaint_token.aleo'...


    Base deployment cost for 'saugatstha_kyc_complaint_token.aleo' is 10.22365 credits.

    +-------------------------------------+----------------+
    | saugatstha_kyc_complaint_token.aleo | Cost (credits) |
    +-------------------------------------+----------------+
    | Transaction Storage                 | 4.433000       |
    +-------------------------------------+----------------+
    | Program Synthesis                   | 4.790650       |
    +-------------------------------------+----------------+
    | Namespace                           | 1.000000       |
    +-------------------------------------+----------------+
    | Priority Fee                        | 0.000000       |
    +-------------------------------------+----------------+
    | Total                               | 10.223650      |
    +-------------------------------------+----------------+

    Your current public balance is 10.227283 credits.

    ✅ Created deployment transaction for 'saugatstha_kyc_complaint_token.aleo'

    Broadcasting transaction to https://api.explorer.provable.com/v1/testnet/transaction/broadcast...

    ⌛ Deployment at1xxja0rcdhghpa7slj5cxht4uqr7j8p0635el3jt0vqurdhtzk5rqg0ss2z ('saugatstha_kyc_complaint_token.aleo') has been broadcast to https://api.explorer.provable.com/v1/testnet/transaction/broadcast.
    ~~~

    </blockquote></details>

- On-Chain Outputs: 
    - Transaction ID: `at1xxja0rcdhghpa7slj5cxht4uqr7j8p0635el3jt0vqurdhtzk5rqg0ss2z`
    - Aleo Program: [https://testnet.aleo.info/program/saugatstha_kyc_complaint_token.aleo](https://testnet.aleo.info/program/saugatstha_kyc_complaint_token.aleo)
    - Deploy Txn: [https://testnet.aleo.info/transaction/at1xxja0rcdhghpa7slj5cxht4uqr7j8p0635el3jt0vqurdhtzk5rqg0ss2z](https://testnet.aleo.info/transaction/at1xxja0rcdhghpa7slj5cxht4uqr7j8p0635el3jt0vqurdhtzk5rqg0ss2z) 

# Signature:
## Sign with `Transaction ID`:
- For me, program deployed Transaction ID is: `at1xxja0rcdhghpa7slj5cxht4uqr7j8p0635el3jt0vqurdhtzk5rqg0ss2z`. Command:
    ```sh
    leo account sign -d --private-key <redacted> --message "at1xxja0rcdhghpa7slj5cxht4uqr7j8p0635el3jt0vqurdhtzk5rqg0ss2z" --raw
    ```
- Output:
    ```sh
    sign1c3590ph5psfde8mcpqlvrrfudzytznnyxkp602ws57edc6kgjypxlpuxrq9uk5j4t25ty582cuc56mdulazxjrhqj38ptkc56dnlcq3eqq3cj89tatjmwmxa89tme9lwtgzzqh9jt8g4uwtnm2nj98lppwdncktrq4xqtajq8y3sv40wsdtmwppd5lkvz4atxy3w3lqeewhqczzhq8p
    ```
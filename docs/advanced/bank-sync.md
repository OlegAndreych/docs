# Connecting Your Bank

:::note
Client Version 23.7.0 and
Server Version 23.7.0 or higher are required for this feature.
:::

We are excited to offer this optional bank integration in Actual. 
Here are a couple of considerations to know about before making the decision to use bank sync in your installation of Actual Budget.

- This integration relies on you providing your own API credentials that you will need to get by signing up with the service provider and Generate Keys and Secrets that will be used in Actual.

- The integration only works if you are using actual-server

- The Secrets and Keys are stored in your Actual installed version so it is highly recommended to turn on End to End encryption and create a strong passphrase to encrypt your files.

- You will need to add a config file to your installation

## Supported Providers

* GoCardless

## GoCardless Setup

### Create SECRET and KEY for Actual

1. Create an account with GoCardless - https://bankaccountdata.gocardless.com/overview/
2. Log into your account dashboard at the same URL and select **Developers->User secrets** from the left side menu

![Screenshot of GoCardless developer portal](/static/img/connecting-your-bank/connecting-your-bank-gocardless-01.png)


3. Click on the '+ create new' button at the bottom left.
   - Make sure you download your secrets file since the **key** will not be available to you again in the account dashboard
   - These secrets will be used in Actual to make the bank sync connection

![Screenshot of GoCardless page for creating API secrets](/static/img/connecting-your-bank/connecting-your-bank-gocardless-02.png)


4. Enter a name for your secrets and click Create.
   _This is only for you to easily identify them in the GoCardless User secrets overview_

![Screenshot of GoCardless form for creating new API secret](/static/img/connecting-your-bank/connecting-your-bank-gocardless-03.png)


5. Download this file and keep it on your computer.

![Screenshot of GoCardless API secret after successful creation](/static/img/connecting-your-bank/connecting-your-bank-gocardless-04.png)



6. Back in Actual, click on “+ Add account” at the bottom of the sidebar.

![Actual sidebar with accounts](/static/img/connecting-your-bank/connecting-your-bank-02.png)



7. Click “Set-up GoCardless for bank-sync.”

![Add account dialog](/static/img/connecting-your-bank/connecting-your-bank-gocardless-05.png)

8. You will be asked to enter your GoCardless secret ID and secret key. These values will be saved on the server, so you will only need to enter them once.

![Set-up GoCardless dialoag](/static/img/connecting-your-bank/connecting-your-bank-gocardless-06.png)


### Link Accounts with GoCardless

1. Add the link to your accounts in actual (Existing or New)

   - **_For an existing account, click on that account, select the ... (kebab menu) in the top right, and choose Link Account_**

![Linking an existing account to GoCardless](/static/img/connecting-your-bank/connecting-your-bank-01.png)

   - **_To create a new account with bank syncing click on the '+ Add account' link in the left menu at the bottom_**

![Actual sidebar with accounts](/static/img/connecting-your-bank/connecting-your-bank-02.png)

2. Select the Link your bank account button

![Add acount dialog](/static/img/connecting-your-bank/connecting-your-bank-03.png)

3. Select your country and bank from the list and click the Link bank in browser button

![Link your bank dialog](/static/img/connecting-your-bank/connecting-your-bank-04.png)

4. Clicking Link bank in browser will redirect you to a new tab to grant access to your bank for GoCardless

![Link you bank feedback](/static/img/connecting-your-bank/connecting-your-bank-05.png)

5. Select **I agree** to continue with setting up the connection

![Dialog to approve that GoCardless will be accessing your payment account information](/static/img/connecting-your-bank/connecting-your-bank-gocardless-07.png)

6. If your connection was a success, you will be able to click on the continue button which allows GoCardless to connect

![Feedback for successful linking to your bank](/static/img/connecting-your-bank/connecting-your-bank-07.png)

7. A progress indicator will display while GoCardless connects to your bank to get a list of your accounts

![Dialog saying please wait while we finish linking your account(s).](/static/img/connecting-your-bank/connecting-your-bank-08.png)

8. Once the connection has been made, there will be a list of your accounts that you can choose from

![Select bank acount you want to link](/static/img/connecting-your-bank/connecting-your-bank-09.png)

9. The final step is to select the account you want to sync and click Link account

![Dialog for linking accounts you want to sync](/static/img/connecting-your-bank/connecting-your-bank-10.png)

### Frequently Asked Questions

**Does Actual sync automatically with your Bank?**

At this moment, it is not yet possible for Actual to automatically sync with your bank. You need to do this manually by going to "All Accounts" and pressing "Sync".

![Image showing where in the GUI you can sync your bank accounts](/static/img/connecting-your-bank/syncing-with-your-bank.png)

**The best way to start from scratch in Actual with GoCardless?**

If you are setting up Actual for the first time, it is much easier not to try to pull in historic data. This has caused some users a lot of headaches with subsequent reconciliation. The following process may be more helpful:
1. Set up your account in Actual specifying a correct opening account balance at a recent date.
2. Link the account to GoCardless as above
3. Sync the account with GoCardless. You should find that only transactions subsequent to the opening account balance entry are imported, making reconciliation easy.


**How many times can I sync with  GoCardless?**
In the free tier, you can sync 50 times per month. If you sync to two different banks (with three accounts in each bank), that is counted as two connections.
For more information, see the [Bank Account Data API Usage](https://bankaccountdata.zendesk.com/hc/en-gb/articles/11528933493916-Bank-Account-Data-API-Usage-how-is-your-usage-number-calculated)
topic in the GoCardless FAQ.


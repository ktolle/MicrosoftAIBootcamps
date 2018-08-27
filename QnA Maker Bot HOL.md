QnA Maker and Azure Bot Service Hands-on Lab
============================================

![](media/df98461a95b1de51e22c07b74db4fc9b.png)

Nowadays bots are everywhere. You probably interact with them every day without
realizing it, they changed the way that we interact with businesses,
communities, and even each other. Thanks to light-speed advances in artificial
intelligence (AI) and availability of AI services, bots are not only becoming
more advanced and personalized, but also more accessible to developers.

[Microsoft QnA Maker](https://www.qnamaker.ai/) combined with Azure Bot Service
provides the tools which are needed to build and publish intelligent bots that
interact naturally with users using a range of services.

In this lab you will create a knowledge base built with QnA Maker and connect it
to a bot using the Azure Bot Service. In the end of this lab you will be able to
add a few channels like Cortana or Skype to use your bot.

HoL Objectives
--------------

In this hands-on lab, you will learn how to:

-   create a knowledge base, populate it with data and test it

-   create a chat bot

-   connect chatbot and knowledge base

-   use your chat bot

-   Add additional channels to chatbot

HOL prerequisites
-----------------

To complete this lab, you need:

-   An active Microsoft Azure Subscription.

-   Stable internet connection

Exercise 1: Create a knowledge base with Microsoft QnA Maker
------------------------------------------------------------

[Microsoft QnA Maker](https://www.qnamaker.ai/) is a part of [Azure Cognitive
Services](https://www.microsoft.com/cognitive-services/), which is a suite of
services and APIs for building intelligent apps backed by AI and machine
learning. Rather than code a bot to anticipate every question a user might ask
and provide a response, you can connect it to a knowledge base of questions and
answers created with QnA Maker. A common usage scenario is to create a knowledge
base from a FAQ so the bot can answer domain-specific questions such as “How
young should a student be to apply to your school?” or “What is the required
documentation for admission?”

In this exercise, you will use QnA Maker to create a knowledge base containing
questions related to your school such “Is there a uniform in your school?” or
“Is there a bus service and which areas do you serve?”

1.  Open new In-Private Browser session. Other log-ins can persist and cause
    errors during deployment process

    *In Microsoft Edge Browser:*

    *To start a new browser window in InPrivate mode, click or tap the “Settings
    and more” button in the top-right corner. It looks like three dots. In the
    menu that is shown, choose “New InPrivate window.”*

    ![](media/92342fe766f69f232ba590694d639981.jpg)

2.  Open the [Microsoft QnA Maker portal](https://www.qnamaker.ai/)
    (https://www.qnamaker.ai/) in your browser and sign in with your Microsoft
    account if you aren't already signed in. Then click **Create a knowledge
    base** in the menu bar at the top of the page.

    ![](media/fd5244d0611659ffe7cbbffab35fbbef.png)

    *Sign in*

    ![](media/2dbdca66705ae64e38dc21db554361ae.png)

    *Creating a knowledge base*

3.  Create QnA service

    After clicking on “Create a knowledge base” you will be redirected to the
    next page.

    Here you will find a little instruction what you need to do when you are
    creating the new knowledge base

    ![](media/f71d491a03306cc42d4b0943ad0e4e37.png)

    *Create a knowledge base*

Click “Create a QnA Service”

You were redirected to Azure portal page. Now we need to add a bit technical
information:

![](media/3c33a18b97ffbc0232638d68aeaa639c.png)

*Creating a QnA service*

Find below the information needed:

| №  | Field                   | What to add (example) | Description                                                                                                                        |
|----|-------------------------|-----------------------|------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Name                    | alice-weeu-qna        | The name of future service                                                                                                         |
| 2  | Subscription            | Nothing to add        | The subscription which used to deploy service                                                                                      |
| 3  | Management pricing tier | F0                    | The pricing tier of service                                                                                                        |
| 4  | Location                | West US               | The location in which the service will be deployed. Please note that for this moment only West US location for qna maker available |
| 5  | Resource group          | alice-weeu-qna-rg     | The name of RG in which the service will be deployed                                                                               |
| 6  | Search pricing tier     | F (Free)              | The pricing of Azure Search Service                                                                                                |
| 7  | Search Location         | West Europe           | The location of Azure Search Service                                                                                               |
| 8  | App name                | alice-weeu-qna-app    | The name of App Service                                                                                                            |
| 9  | Website location        | West Europe           | The location of App Service                                                                                                        |
| 10 | App Insights            | Enable                |                                                                                                                                    |
| 11 | App Insights location   | West Europe           |                                                                                                                                    |

Now click Create and wait until you’ll see ‘Succeeded deployment.

You can open Notifications on the portal to see.

![](media/e71cd2ec09319523cae7c982a021f50f.png)

*Succeeded deployment*

1.  Now return to the  [Create a knowledge
    base](https://www.qnamaker.ai/Create) page, refresh it and:

    1.  Choose from drop-down list you Active Directory tenant it’s have to be –
        yourmailadress (without . and \@),

    2.  Choose your Azure Subscription – it h as to be Azure Pass

    3.  *Choose Azure QnA Service. It has to be the name which you have
        specified on step 3*

![](media/55f48980c86c8923b197ff5757f6b276.png)

*QnA Service Connection*

1.  Type the name for you Knowledge base, ex. Alice Greece School Knowledge Base

2.  In order to populate the QnA Maker knowledge base, use one of the
    approaches:

-   Manually

-   Import from local files

-   Import from online FAQs

*Microsoft Word documents, Excel spreadsheets, PDF files and tab-delimited text
files are supported to import from files.*

In this lab we’ll populate from one of Greek school FaQ page, which was found
online.

http://www.acs.gr/faq/

![](media/d214ca69c9fb56420001643e6e544df7.png)

*Populating the knowledge base*

1.  Click ‘Create’ and wait for a few seconds

![](media/2e7930a32eeeae80706cb4cc6f3be0f9.png)

*Populating the knowledge base – waiting page*

After a while (QnA Maker parsed the site and created automatically the QnA
pairs) you will see the next page:

![](media/5bcec7a049abc2bfdcc1e0aaa010e372.png)

*QnA Pairs*

1.  Try to add manually a few QnA pairs

    For that click ‘+ Add Qna pair’ and add the question and answer (see
    screenshots below)

![](media/5c4a72bd3d227c2e5131d58a54626c64.png)

*Adding the new QnA Pair - 1*

![](media/64b8115774fa3a82188f6ea1a53138ec.png)

*Adding the new QnA Pair - 2*

1.  Save the results and train the model for questions and answers. To do it,
    click ‘Save and Train’

    ![](media/b7bf9c0bb4e1f267e6d5d94ac3a79882.png)

    *Save and train*

    *This process can take few minutes*

    ![](media/9d6cb3952af3b50c94f66e0bcb733137.png)

    *Model training*

2.  Test the created knowledge base. Click the ‘Test’ button to the right of the
    ‘Save and train’ button. Type “Hi” into the message box and press Enter.
    Confirm that the response is “Hello cute! Welcome Alice :)”

![](media/28b853ea31d9b7f824adda73a36f41d2.png)

*Test trained knowledge base*

*If everything is ok and responses are the same is expected, we’ll publish our
knowledge base.*

1.  Click the “Test**”** button to collapse the Test panel. Then
    click “Publish” in the menu at the top of the page and click
    the “Publish” button at the bottom of the page to publish the knowledge
    base. *Publishing* makes the knowledge base available publicly.

![](media/a06c0f451aea394b8cd6113e950d3017.png)

>   *Knowledge Base publishing*

![](media/cb0673c53525e38bc44f524514a7e07d.png)

>   *Knowledge Base publishing – waiting screen*

>   Wait for the publication process to complete and confirm that you are told
>   the QnA service has been deployed. With the knowledge base now hosted in an
>   Azure Web App of its own, the next step is to deploy a bot that can use it.

![](media/fe377c10401f29fb40e16b5657b203bd.png)

>   *Knowledge Base publishing – Success result*

Exercise 2: Create a bot and connect it to knowledge base
---------------------------------------------------------

In this exercise we’ll create a bot and deploy it to Azure.

1.  Open the https://portal.azure.com/ in your browser.

2.  Click “+” -\> “Create a resource”, followed by “AI + Machine Learning” and
    then “Web App Bot”.

![](media/3d2637773b85dd26a103291d739735f5.png)

>   *Bot creation process*

1.  Enter a name such as "ai-school-bot" into the “App name box”. 

>   *Attention: This name must be unique within Azure, so make sure a green
>   check mark appears next to it.*

1.  Enter the name of Resource group to store the bot

2.  Choose the location (the nearest, West Europe)

3.  Choose pricing tier – for this demo F0 tier is enough

4.  Choose bot template -\> Question and Answer -\> Select

    ![](media/a61b945ad91d24a1045e2d756bbc4a52.png)

>   *Bot creation process - 1*

1.  App service plan/Location, Azure Storage, Application insights and
    Application insights location settings leave by default

2.  Scroll down

3.  Verify that “Create Microsoft App ID” is enabled to “Auto Create”

4.  Click Create

![](media/18b580b5fb27e55641aa40a0fd5ac80e.png)

>   *Bot creation – 2*

1.  Wait till succeeded deployment notification

    *To verify notifications, you can open notification center in top right
    corner of the portal*

    ![](media/409720f38ae000ee9c9d5d735e664174.png)

>   *Notifications center*

1.  Click ‘Go to resource’

You will be redirected to bot resource page:

![](media/cbe1f1864f3541f6f8884e8d3cf94d06.png)

*Bot resource page*

1.  Close notifications center

2.  Click “Applications Settings” in “App Service Settings” section

    1.  On this page, need to edit the “QnAKnowledgebaseId”,** “**QnAAuthKey”,
        and the “QnAEndpointHostName” fields.

>   *The content of knowledge base ID, host URL, and the endpoint key knowledge
>   base could be found at *[https://qnamaker.ai](https://qnamaker.ai/)

1.  Log in to QnA Maker

2.  Go to your knowledge base

3.  Click on the “Settings**”** tab

![](media/9ce8c090736c808efcc10ef3c00b8c79.png)

*Settings tab*

![](media/759c7a4499538e07d8b584a2d8bdf363.png)

*Helper information*

1.  Copy the necessary information and insert it to *“*Applications Settings”
    page (5.1.)

2.  Click ‘Save’

    ![](media/fd271c50421e3ba784e26e9366e95de1.png)

    *Bot settings*

3.  Test the bot

    1.  Click “Test in Web Chat” tab in “Bot Management” section

        ![](media/474cf8a80394ee46a3871c6a9038b36d.png)

        *Bot testing*

Exercise 3: Adding the channels to the bot
------------------------------------------

In this exercise we’ll add the channels to the bot.

1.  Open the https://portal.azure.com/ in your browser.

2.  Navigate to the Resource group with your bot. Click “Resource groups” on
    Left panel on Azure Portal. In Opened list click on the Resource group with
    your bot

![](media/2a8370eb7e8bfc0124c21ee87e727e0b.png)

*Resources groups page*

1.  Click on your “Web App Bot”

![](media/ef2fd82e1ce7147293b6faf6f928b3f4.png)

*Resources In resource group page*

![](media/7b80797dae30fc794c52c5b4175ace6d.png)

*Initial bot page*

1.  Click on “Channels” on “Bot Management” section

![](media/104b0312f56a92fc538ceca1d15f0874.png)

*Bot channels page*

1.  Add Microsoft Teams as a channel. Click on MS Teams logo on “Add a featured
    channel section”

2.  Tick the checkbox “I agree …” and after “Agree” with “Term of service”

![](media/0e60e4e5c946ad8968bc90662641e789.png)

*Terms of Service page*

![](media/e577d61d28a68a0264180643ff17556f.png)

*Resulting page*

1.  Go to <https://products.office.com/en/microsoft-teams/group-chat-software>
    in new browser tab

2.  Click “Sign-in”

    1.  If it fist time to use MS Teams from this Microsoft Account we need to
        register MS teams for its organization

    2.  Click on “Sign up for Teams”

![](media/35bff557b1463d3029b50664c9074b0a.png)

>   *Sign up for Teams*

1.  Type your Azure account email address and Click “SIGN UP FOR FREE”

![](media/6406684b5c9ce72c82cae4683708f21d.png)

1.  Click “Set up account”

![](media/f06ebd9b7258bb751769188b59157ce4.png)

>   Set-upping MS Teams account

1.  Add information about yourself And click “Next”

![](media/e6c509f32692f959a056a5d4c77c283b.png)

>   *Tell us page*

1.  Waiting for account creation

![](media/065840a3fe9178d3171f04a5ca905c99.png)

>   *Account creation page*

1.  Click “Let’s go”

![](media/1410ee9a0f02ab47d4faf9eb36408a44.png)

>   Resulting page

1.  Open now MS Teams and Log-in with Azure Account

2.  Go back to Azure portal with your bot page (step 2- 3)

3.  Select “Settings” tab in “Bot Management” section

![](media/2d6699d18f93071f10481e6616dc4557.png)

>   Where to found “Settings” tab

1.  On Settings tab copy “Microsoft App ID”

2.  Go to Microsoft Teams, on the Chat pane, select the Add chat icon.
    For To**:**, paste your bot's Microsoft App ID.

![](media/5f36425aadf6a0a20812c40f5848395b.png)

1.  Select your bot and type “Hi”

![](media/153fde07117a5a10d478b3656ae720b4.png)

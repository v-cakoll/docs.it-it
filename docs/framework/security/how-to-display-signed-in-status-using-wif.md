---
title: 'Procedura: Visualizzare lo stato di accesso effettuato con WIF'
ms.date: 03/30/2017
ms.assetid: 4d1174e4-5397-4962-9a5f-3b1ad7b3fc14
author: BrucePerlerMS
ms.openlocfilehash: b07a8930255786686fb1e587b2a29bbc708eff63
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311032"
---
# <a name="how-to-display-signed-in-status-using-wif"></a><span data-ttu-id="27b53-102">Procedura: Visualizzare lo stato di accesso effettuato con WIF</span><span class="sxs-lookup"><span data-stu-id="27b53-102">How To: Display Signed In Status Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="27b53-103">Si applica a</span><span class="sxs-lookup"><span data-stu-id="27b53-103">Applies To</span></span>  
  
-   <span data-ttu-id="27b53-104">Microsoft® Windows® Identity Foundation (WIF) 4.5</span><span class="sxs-lookup"><span data-stu-id="27b53-104">Microsoft® Windows® Identity Foundation (WIF) 4.5</span></span>  
  
-   <span data-ttu-id="27b53-105">Web Form ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="27b53-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="27b53-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="27b53-106">Summary</span></span>  
 <span data-ttu-id="27b53-107">Questo argomento descrive come visualizzare lo stato di accesso in un'applicazione ASP.NET abilitata per WIF.</span><span class="sxs-lookup"><span data-stu-id="27b53-107">This topic describes how to display the sign in status in a WIF-enabled ASP.NET application.</span></span> <span data-ttu-id="27b53-108">WIF fornisce il meccanismo per rendere un'applicazione in grado di riconoscere attestazioni e per gestire autenticazione e autorizzazione per le risorse dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="27b53-108">WIF provides the mechanism for making your application claims-aware, and managing authentication and authorization for application resources.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="27b53-109">Sommario</span><span class="sxs-lookup"><span data-stu-id="27b53-109">Contents</span></span>  
  
-   <span data-ttu-id="27b53-110">Panoramica</span><span class="sxs-lookup"><span data-stu-id="27b53-110">Overview</span></span>  
  
-   <span data-ttu-id="27b53-111">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="27b53-111">Summary of Steps</span></span>  
  
-   <span data-ttu-id="27b53-112">Passaggio 1: installare l'estensione Identity and Access</span><span class="sxs-lookup"><span data-stu-id="27b53-112">Step 1 – Install the Identity and Access Extension</span></span>  
  
-   <span data-ttu-id="27b53-113">Passaggio 2: creare un'applicazione ASP.NET relying party</span><span class="sxs-lookup"><span data-stu-id="27b53-113">Step 2 – Create a Relying Party ASP.NET Application</span></span>  
  
-   <span data-ttu-id="27b53-114">Passaggio 3: abilitare il servizio token di sicurezza per lo sviluppo locale per autenticare gli utenti</span><span class="sxs-lookup"><span data-stu-id="27b53-114">Step 3 – Enable Local Development STS to Authenticate Users</span></span>  
  
-   <span data-ttu-id="27b53-115">Passaggio 4: modificare l'applicazione ASP.NET per visualizzare lo stato di accesso</span><span class="sxs-lookup"><span data-stu-id="27b53-115">Step 4 – Modify Your ASP.NET Application to Display Sign In Status</span></span>  
  
-   <span data-ttu-id="27b53-116">Passaggio 5: testare l'integrazione tra WIF e l'applicazione ASP.NET</span><span class="sxs-lookup"><span data-stu-id="27b53-116">Step 5 – Test the Integration Between WIF and Your ASP.NET Application</span></span>  
  
## <a name="overview"></a><span data-ttu-id="27b53-117">Panoramica</span><span class="sxs-lookup"><span data-stu-id="27b53-117">Overview</span></span>  
 <span data-ttu-id="27b53-118">Questo argomento dimostra come creare una semplice applicazione in grado di riconoscere attestazioni mediante WIF e come visualizzare facilmente se un utente è connesso o meno.</span><span class="sxs-lookup"><span data-stu-id="27b53-118">This topic demonstrates how to create a simple claims-aware application using WIF and how to easily display whether a user is signed in or not.</span></span> <span data-ttu-id="27b53-119">La procedura seguente usa il servizio token di sicurezza per lo sviluppo locale incluso nell'estensione di Visual Studio Identity and Access.</span><span class="sxs-lookup"><span data-stu-id="27b53-119">The following steps use the Local Development STS that is included with the Identity and Access Visual Studio Extension.</span></span> <span data-ttu-id="27b53-120">Il servizio token di sicurezza per lo sviluppo locale è destinato a un ambiente di sviluppo e test per fornire un metodo semplice per l'integrazione delle attestazioni nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="27b53-120">The Local Development STS is intended for a testing and development environment to provide a simple method of integrating claims into your application.</span></span> <span data-ttu-id="27b53-121">Non deve mai essere usato in ambiente di produzione, perché non esegue effettivamente l'autenticazione e non sono richieste credenziali.</span><span class="sxs-lookup"><span data-stu-id="27b53-121">It should never be used in a production environment, as it does not perform real authentication and credentials are not required.</span></span> <span data-ttu-id="27b53-122">Tuttavia, il codice imperativo nei passaggi seguenti è lo stesso per un'applicazione utilizzabile in produzione con i meccanismi di autenticazione effettivi.</span><span class="sxs-lookup"><span data-stu-id="27b53-122">However, the imperative code in the following steps is the same for a production-ready application using real authentication.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="27b53-123">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="27b53-123">Summary of Steps</span></span>  
  
-   <span data-ttu-id="27b53-124">Passaggio 1: installare l'estensione Identity and Access</span><span class="sxs-lookup"><span data-stu-id="27b53-124">Step 1 – Install the Identity and Access Extension</span></span>  
  
-   <span data-ttu-id="27b53-125">Passaggio 2: creare un'applicazione ASP.NET relying party</span><span class="sxs-lookup"><span data-stu-id="27b53-125">Step 2 – Create a Relying Party ASP.NET Application</span></span>  
  
-   <span data-ttu-id="27b53-126">Passaggio 3: abilitare il servizio token di sicurezza per lo sviluppo locale per autenticare gli utenti</span><span class="sxs-lookup"><span data-stu-id="27b53-126">Step 3 – Enable Local Development STS to Authenticate Users</span></span>  
  
-   <span data-ttu-id="27b53-127">Passaggio 4: modificare l'applicazione ASP.NET per visualizzare lo stato di accesso</span><span class="sxs-lookup"><span data-stu-id="27b53-127">Step 4 – Modify Your ASP.NET Application to Display Sign In Status</span></span>  
  
-   <span data-ttu-id="27b53-128">Passaggio 5: testare l'integrazione tra WIF e l'applicazione ASP.NET</span><span class="sxs-lookup"><span data-stu-id="27b53-128">Step 5 – Test the Integration Between WIF and Your ASP.NET Application</span></span>  
  
## <a name="step-1--install-the-identity-and-access-extension"></a><span data-ttu-id="27b53-129">Passaggio 1: installare l'estensione Identity and Access</span><span class="sxs-lookup"><span data-stu-id="27b53-129">Step 1 – Install the Identity and Access Extension</span></span>  
 <span data-ttu-id="27b53-130">Questo passaggio descrive come configurare l'estensione Identity and Access in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="27b53-130">This step describes how to configure the Identity and Access extension to Visual Studio 2012.</span></span> <span data-ttu-id="27b53-131">Questa estensione consente di automatizzare il processo di configurazione dell'applicazione per comunicare con gli endpoint del servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="27b53-131">This extension automates the process of configuring your application to communicate with STS endpoints.</span></span>  
  
#### <a name="to-install-the-identity-and-access-extension"></a><span data-ttu-id="27b53-132">Per installare l'estensione Identity and Access</span><span class="sxs-lookup"><span data-stu-id="27b53-132">To install the Identity and Access extension</span></span>  
  
1. <span data-ttu-id="27b53-133">Avviare Visual Studio come amministratore in modalità con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="27b53-133">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2. <span data-ttu-id="27b53-134">In Visual Studio fare clic su **Strumenti** e quindi su **Gestione estensioni**.</span><span class="sxs-lookup"><span data-stu-id="27b53-134">In Visual Studio, click **Tools** and click **Extension Manager**.</span></span> <span data-ttu-id="27b53-135">Verrà visualizzata la finestra **Gestione estensioni**.</span><span class="sxs-lookup"><span data-stu-id="27b53-135">The **Extension Manager** window appears.</span></span>  
  
3. <span data-ttu-id="27b53-136">In **Gestione estensioni** fare clic su **Estensioni online** nel menu a sinistra e quindi selezionare **Visual Studio Gallery**.</span><span class="sxs-lookup"><span data-stu-id="27b53-136">In **Extension Manager**, click **Online Extensions** from the left menu, then select **Visual Studio Gallery**.</span></span>  
  
4. <span data-ttu-id="27b53-137">Nell'angolo superiore destro di **Gestione estensioni** cercare *Identity and Access*.</span><span class="sxs-lookup"><span data-stu-id="27b53-137">In the top right corner of **Extension Manager**, search for *Identity and Access*.</span></span>  
  
5. <span data-ttu-id="27b53-138">L'elemento **Identity and Access** verrà visualizzato nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="27b53-138">The **Identity and Access** item will appear in the search results.</span></span> <span data-ttu-id="27b53-139">Fare clic su di esso e quindi su **Scarica**.</span><span class="sxs-lookup"><span data-stu-id="27b53-139">Click it, and then click **Download**.</span></span>  
  
6. <span data-ttu-id="27b53-140">Verrà visualizzata la finestra di dialogo **Scarica e installa** .</span><span class="sxs-lookup"><span data-stu-id="27b53-140">The **Download and Install** dialog appears.</span></span> <span data-ttu-id="27b53-141">Se si accettano le condizioni di licenza, fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="27b53-141">If you agree with the license terms, click **Install**.</span></span>  
  
7. <span data-ttu-id="27b53-142">Al termine dell'installazione dell'estensione **Identity and Access**, riavviare Visual Studio in modalità amministratore.</span><span class="sxs-lookup"><span data-stu-id="27b53-142">When the **Identity and Access** extension has finished installing, restart Visual Studio in administrator mode.</span></span>  
  
## <a name="step-2--create-a-relying-party-aspnet-application"></a><span data-ttu-id="27b53-143">Passaggio 2: creare un'applicazione ASP.NET relying party</span><span class="sxs-lookup"><span data-stu-id="27b53-143">Step 2 – Create a Relying Party ASP.NET Application</span></span>  
 <span data-ttu-id="27b53-144">Questo passaggio descrive come creare un'applicazione Web Form ASP.NET relying party che verrà integrata con WIF.</span><span class="sxs-lookup"><span data-stu-id="27b53-144">This step describes how to create a relying party ASP.NET Web Forms application that will integrate with WIF.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="27b53-145">Per creare un'applicazione ASP.NET semplice</span><span class="sxs-lookup"><span data-stu-id="27b53-145">To create a simple ASP.NET application</span></span>  
  
1. <span data-ttu-id="27b53-146">Avviare Visual Studio e fare clic su **File**, **Nuovo** e **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="27b53-146">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2. <span data-ttu-id="27b53-147">Nella finestra **Nuovo progetto** fare clic su **Applicazione Web Form ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="27b53-147">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3. <span data-ttu-id="27b53-148">In **Nome** immettere `TestApp` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="27b53-148">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-3--enable-local-development-sts-to-authenticate-users"></a><span data-ttu-id="27b53-149">Passaggio 3: abilitare il servizio token di sicurezza per lo sviluppo locale per autenticare gli utenti</span><span class="sxs-lookup"><span data-stu-id="27b53-149">Step 3 – Enable Local Development STS to Authenticate Users</span></span>  
 <span data-ttu-id="27b53-150">Questo passaggio descrive come abilitare il servizio token di sicurezza per lo sviluppo locale nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="27b53-150">This step describes how to enable Local Development STS in your application.</span></span> <span data-ttu-id="27b53-151">Il servizio token di sicurezza per lo sviluppo locale viene abilitato tramite l'estensione Identity and Access per Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="27b53-151">Local Development STS is enabled by using the Identity and Access extension for Visual Studio.</span></span>  
  
#### <a name="to-enable-local-development-sts-in-your-aspnet-application"></a><span data-ttu-id="27b53-152">Per abilitare il servizio token di sicurezza per lo sviluppo locale nell'applicazione ASP.NET</span><span class="sxs-lookup"><span data-stu-id="27b53-152">To enable Local Development STS in your ASP.NET application</span></span>  
  
1. <span data-ttu-id="27b53-153">In Visual Studio fare clic con il pulsante destro del mouse sul progetto **TestApp** in **Esplora soluzioni** e quindi scegliere **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="27b53-153">In Visual Studio, right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
2. <span data-ttu-id="27b53-154">Verrà visualizzata la finestra **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="27b53-154">The **Identity and Access** window appears.</span></span> <span data-ttu-id="27b53-155">In **Providers** (Provider) selezionare **Test your application with the Local Development STS** (Testare l'applicazione con il servizio token di sicurezza per lo sviluppo locale) e quindi fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="27b53-155">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
## <a name="step-4--modify-your-aspnet-application-to-display-sign-in-status"></a><span data-ttu-id="27b53-156">Passaggio 4: modificare l'applicazione ASP.NET per visualizzare lo stato di accesso</span><span class="sxs-lookup"><span data-stu-id="27b53-156">Step 4 – Modify Your ASP.NET Application to Display Sign In Status</span></span>  
 <span data-ttu-id="27b53-157">Questo passaggio descrive come modificare l'applicazione ASP.NET per visualizzare in modo dinamico se l'utente corrente ha effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="27b53-157">This step describes how to modify your ASP.NET application to dynamically display whether the current user is signed in.</span></span> <span data-ttu-id="27b53-158">Una volta configurato il provider del servizio token di sicurezza, WIF gestisce le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="27b53-158">Once your STS provider has been configured, WIF handles the incoming claims.</span></span> <span data-ttu-id="27b53-159">È ora necessario configurare il codice dell'applicazione per visualizzare il risultato dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="27b53-159">Now you need to configure your application’s code to display the result of the authentication.</span></span>  
  
#### <a name="to-display-sign-in-status"></a><span data-ttu-id="27b53-160">Per visualizzare lo stato di accesso</span><span class="sxs-lookup"><span data-stu-id="27b53-160">To display sign in status</span></span>  
  
1. <span data-ttu-id="27b53-161">In Visual Studio aprire il file **Default.aspx** nel progetto **TestApp**.</span><span class="sxs-lookup"><span data-stu-id="27b53-161">In Visual Studio, open the **Default.aspx** file under the **TestApp** project.</span></span>  
  
2. <span data-ttu-id="27b53-162">Sostituire il markup esistente nel file **Default.aspx** con il seguente:</span><span class="sxs-lookup"><span data-stu-id="27b53-162">Replace the existing markup in the **Default.aspx** file with the following markup:</span></span>  
  
    ```  
    <%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head runat="server">  
        <title>Logged In Status</title>  
    </head>  
    <body>  
        <asp:label ID="myLabel" runat="server" />  
    </body>  
    </html>  
    ```  
  
3. <span data-ttu-id="27b53-163">Salvare **Default.aspx** e quindi aprire il file code-behind denominato **Default.aspx.cs**.</span><span class="sxs-lookup"><span data-stu-id="27b53-163">Save **Default.aspx**, and then open its code behind file named **Default.aspx.cs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27b53-164">Il file **Default.aspx.cs** potrebbe essere nascosto sotto **Default.aspx** in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="27b53-164">**Default.aspx.cs** may be hidden beneath **Default.aspx** in Solution Explorer.</span></span> <span data-ttu-id="27b53-165">Se **Default.aspx.cs** non è visibile, espandere **Default.aspx** facendo clic sul triangolo accanto.</span><span class="sxs-lookup"><span data-stu-id="27b53-165">If **Default.aspx.cs** is not visible, expand **Default.aspx** by clicking on the triangle next to it.</span></span>  
  
4. <span data-ttu-id="27b53-166">Sostituire il codice esistente nel file **Default.aspx.cs** con il seguente:</span><span class="sxs-lookup"><span data-stu-id="27b53-166">Replace the existing code in **Default.aspx.cs** with the following code:</span></span>  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        protected void Page_Load(object sender, EventArgs e)  
        {  
            ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
            if (claimsPrincipal != null)  
            {  
                myLabel.Text = "You are signed in.";  
            }  
            else  
            {  
                myLabel.Text = "You are not signed in.";  
            }  
        }  
    }  
    ```  
  
5. <span data-ttu-id="27b53-167">Salvare **Default.aspx.cs** e compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="27b53-167">Save **Default.aspx.cs**, and build the application.</span></span>  
  
## <a name="step-5--test-the-integration-between-wif-and-your-aspnet-application"></a><span data-ttu-id="27b53-168">Passaggio 5: testare l'integrazione tra WIF e l'applicazione ASP.NET</span><span class="sxs-lookup"><span data-stu-id="27b53-168">Step 5 – Test the Integration Between WIF and Your ASP.NET Application</span></span>  
 <span data-ttu-id="27b53-169">Questo passaggio descrive la procedura per testare l'integrazione tra WIF e l'applicazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="27b53-169">This step describes how you can test the integration between WIF and your ASP.NET application.</span></span>  
  
#### <a name="to-test-the-integration-between-wif-and-aspnet"></a><span data-ttu-id="27b53-170">Per testare l'integrazione tra WIF e ASP.NET</span><span class="sxs-lookup"><span data-stu-id="27b53-170">To test the integration between WIF and ASP.NET</span></span>  
  
1. <span data-ttu-id="27b53-171">In Visual Studio premere **F5** per avviare il debug dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="27b53-171">In Visual Studio, press **F5** to start debugging your application.</span></span> <span data-ttu-id="27b53-172">Se non vengono rilevati errori, verrà aperta una nuova finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="27b53-172">If no errors are found, a new browser window will open.</span></span>  
  
2. <span data-ttu-id="27b53-173">Si può notare che il browser reindirizza automaticamente la richiesta al servizio token di sicurezza e quindi apre la pagina Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="27b53-173">You may notice that the browser silently redirects your request to the STS, and then opens the Default.aspx page.</span></span> <span data-ttu-id="27b53-174">Se WIF è configurato correttamente, deve visitare il sito verrà visualizzato il testo seguente: **"Si è connessi"**.</span><span class="sxs-lookup"><span data-stu-id="27b53-174">If WIF is properly configured, you should see the site display the following text: **"You are signed in"**.</span></span>

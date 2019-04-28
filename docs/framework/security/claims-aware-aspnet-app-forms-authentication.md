---
title: "Procedura: Compilare un'applicazione ASP.NET che può riconoscere attestazioni con l'autenticazione basata su moduli"
ms.date: 03/30/2017
ms.assetid: 98a3e029-1a9b-4e0c-b5d0-29d3f23f5b15
author: BrucePerlerMS
ms.openlocfilehash: ecaf1de0b806d5568d81fac2ddb2b39b697135ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792745"
---
# <a name="how-to-build-claims-aware-aspnet-application-using-forms-based-authentication"></a><span data-ttu-id="9914a-102">Procedura: Compilare un'applicazione ASP.NET che può riconoscere attestazioni con l'autenticazione basata su moduli</span><span class="sxs-lookup"><span data-stu-id="9914a-102">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>

## <a name="applies-to"></a><span data-ttu-id="9914a-103">Si applica a</span><span class="sxs-lookup"><span data-stu-id="9914a-103">Applies To</span></span>

- <span data-ttu-id="9914a-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="9914a-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>

- <span data-ttu-id="9914a-105">Web Form ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="9914a-105">ASP.NET® Web Forms</span></span>

## <a name="summary"></a><span data-ttu-id="9914a-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="9914a-106">Summary</span></span>

<span data-ttu-id="9914a-107">Questo argomento include le procedure dettagliate per creare un'applicazione Web Form ASP.NET semplice, in grado di riconoscere attestazioni, che usa l'autenticazione basata su form.</span><span class="sxs-lookup"><span data-stu-id="9914a-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application that uses Forms authentication.</span></span> <span data-ttu-id="9914a-108">Sono inoltre disponibili istruzioni per testare l'applicazione al fine di assicurarsi che le attestazioni vengano presentate quando un utente accede con l'autenticazione basata su form.</span><span class="sxs-lookup"><span data-stu-id="9914a-108">It also provides instructions for how to test the application to verify that claims are presented when a user signs in with Forms authentication.</span></span>

## <a name="contents"></a><span data-ttu-id="9914a-109">Sommario</span><span class="sxs-lookup"><span data-stu-id="9914a-109">Contents</span></span>

- <span data-ttu-id="9914a-110">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="9914a-110">Objectives</span></span>

- <span data-ttu-id="9914a-111">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9914a-111">Overview</span></span>

- <span data-ttu-id="9914a-112">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="9914a-112">Summary of Steps</span></span>

- <span data-ttu-id="9914a-113">Passaggio 1: creare una semplice applicazione Web Form ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9914a-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>

- <span data-ttu-id="9914a-114">Passaggio 2: configurare l'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione basata su form</span><span class="sxs-lookup"><span data-stu-id="9914a-114">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>

- <span data-ttu-id="9914a-115">Passaggio 3: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="9914a-115">Step 3 – Test Your Solution</span></span>

## <a name="objectives"></a><span data-ttu-id="9914a-116">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="9914a-116">Objectives</span></span>

- <span data-ttu-id="9914a-117">Configurare un'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione basata su form</span><span class="sxs-lookup"><span data-stu-id="9914a-117">Configure an ASP.NET Web Forms application for claims using Forms authentication</span></span>

- <span data-ttu-id="9914a-118">Testare l'applicazione Web Form ASP.NET per verificare se funziona correttamente</span><span class="sxs-lookup"><span data-stu-id="9914a-118">Test the ASP.NET Web Forms application to see if it is working properly</span></span>

## <a name="overview"></a><span data-ttu-id="9914a-119">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9914a-119">Overview</span></span>

<span data-ttu-id="9914a-120">In .NET 4.5, WIF e l'autorizzazione basata sulle attestazioni sono diventati parte integrante del framework.</span><span class="sxs-lookup"><span data-stu-id="9914a-120">In .NET 4.5, WIF and its claims-based authorization have been included as an integral part of the Framework.</span></span> <span data-ttu-id="9914a-121">In precedenza, per usare le attestazioni da un utente ASP.NET, era necessario installare WIF e quindi effettuare il cast delle interfacce su oggetti Principal come `Thread.CurrentPrincipal` o `HttpContext.Current.User`.</span><span class="sxs-lookup"><span data-stu-id="9914a-121">Previously, if you wanted claims from an ASP.NET user, you were required to install WIF, and then cast interfaces to Principal objects such as `Thread.CurrentPrincipal` or `HttpContext.Current.User`.</span></span> <span data-ttu-id="9914a-122">Ora le attestazioni vengono gestite automaticamente da questi oggetti Principal.</span><span class="sxs-lookup"><span data-stu-id="9914a-122">Now, claims are served automatically by these Principal objects.</span></span>

<span data-ttu-id="9914a-123">L'autenticazione basata su form ha tratto vantaggio dall'inclusione di WIF in .NET 4.5, perché a tutti gli utenti autenticati con credenziali basate su form vengono associate automaticamente le attestazioni.</span><span class="sxs-lookup"><span data-stu-id="9914a-123">Forms authentication has benefited from WIF’s inclusion in .NET 4.5 because all users authenticated by Forms automatically have claims associated with them.</span></span> <span data-ttu-id="9914a-124">È possibile iniziare subito a usare queste attestazioni in un'applicazione ASP.NET che usa l'autenticazione basata su form, come illustrato di seguito in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="9914a-124">You can begin using these claims immediately in an ASP.NET application that uses Forms authentication, as this How-To demonstrates.</span></span>

## <a name="summary-of-steps"></a><span data-ttu-id="9914a-125">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="9914a-125">Summary of Steps</span></span>

- <span data-ttu-id="9914a-126">Passaggio 1: creare una semplice applicazione Web Form ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9914a-126">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>

- <span data-ttu-id="9914a-127">Passaggio 2: configurare l'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione basata su form</span><span class="sxs-lookup"><span data-stu-id="9914a-127">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>

- <span data-ttu-id="9914a-128">Passaggio 3: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="9914a-128">Step 3 – Test Your Solution</span></span>

## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="9914a-129">Passaggio 1: creare una semplice applicazione Web Form ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9914a-129">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>

<span data-ttu-id="9914a-130">In questo passaggio si creerà una nuova applicazione Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="9914a-130">In this step, you will create a new ASP.NET Web Forms application.</span></span>

#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="9914a-131">Per creare un'applicazione ASP.NET semplice</span><span class="sxs-lookup"><span data-stu-id="9914a-131">To create a simple ASP.NET application</span></span>

1. <span data-ttu-id="9914a-132">Avviare Visual Studio e fare clic su **File**, **Nuovo** e **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="9914a-132">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>

2. <span data-ttu-id="9914a-133">Nella finestra **Nuovo progetto** fare clic su **Applicazione Web Form ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="9914a-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>

3. <span data-ttu-id="9914a-134">In **Nome** immettere `TestApp` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9914a-134">In **Name**, enter `TestApp` and press **OK**.</span></span>

## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="9914a-135">Passaggio 2: configurare l'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione basata su form</span><span class="sxs-lookup"><span data-stu-id="9914a-135">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>

<span data-ttu-id="9914a-136">In questo passaggio si aggiungerà una voce al file di configurazione *Web.config* e si modificherà il file *Default.aspx* per visualizzare le informazioni sulle attestazioni per un account.</span><span class="sxs-lookup"><span data-stu-id="9914a-136">In this step you will add a configuration entry to the *Web.config* configuration file and edit the *Default.aspx* file to display claims information for an account.</span></span>

#### <a name="to-configure-aspnet-application-for-claims-using-forms-authentication"></a><span data-ttu-id="9914a-137">Per configurare l'applicazione ASP.NET per le attestazioni usando l'autenticazione basata su form</span><span class="sxs-lookup"><span data-stu-id="9914a-137">To configure ASP.NET application for claims using Forms authentication</span></span>

1. <span data-ttu-id="9914a-138">Nel file *Default.aspx* sostituire il markup esistente con il seguente:</span><span class="sxs-lookup"><span data-stu-id="9914a-138">In the *Default.aspx* file, replace the existing markup with the following:</span></span>

    ```aspx
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>

    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">
        <p>
            This page displays the claims associated with a Forms authenticated user.
        </p>
        <h3>Your Claims</h3>
        <p>
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">
                <AlternatingRowStyle BackColor="White" />
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />
            </asp:GridView>
        </p>
    </asp:Content>
    ```

    <span data-ttu-id="9914a-139">Questo passaggio aggiunge alla pagina *Default.aspx* un controllo GridView che verrà popolato con le attestazioni recuperate dall'autenticazione basata su form.</span><span class="sxs-lookup"><span data-stu-id="9914a-139">This step adds a GridView control to your *Default.aspx* page that will be populated with the claims retrieved from Forms authentication.</span></span>

2. <span data-ttu-id="9914a-140">Salvare il file *Default.aspx* e quindi aprire il relativo file code-behind denominato *Default.aspx.cs*.</span><span class="sxs-lookup"><span data-stu-id="9914a-140">Save the *Default.aspx* file, then open its code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="9914a-141">Sostituire il codice esistente con quello seguente:</span><span class="sxs-lookup"><span data-stu-id="9914a-141">Replace the existing code with the following:</span></span>

    ```csharp
    using System;
    using System.Web.UI;
    using System.Security.Claims;

    namespace TestApp
    {
        public partial class _Default : Page
        {
            protected void Page_Load(object sender, EventArgs e)
            {
                ClaimsPrincipal claimsPrincipal = Page.User as ClaimsPrincipal;

                if (claimsPrincipal != null)
                {
                    this.ClaimsGridView.DataSource = claimsPrincipal.Claims;
                    this.ClaimsGridView.DataBind();
                }
            }
        }
    }
    ```

    <span data-ttu-id="9914a-142">Il codice sopra riportato visualizzerà le attestazioni relative a un utente autenticato, inclusi gli utenti identificati dall'autenticazione basata su form.</span><span class="sxs-lookup"><span data-stu-id="9914a-142">The above code will display claims about an authenticated user, including users identified by Forms authentication.</span></span>

## <a name="step-3--test-your-solution"></a><span data-ttu-id="9914a-143">Passaggio 3: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="9914a-143">Step 3 – Test Your Solution</span></span>

<span data-ttu-id="9914a-144">In questo passaggio verrà testata l'applicazione Web Form ASP.NET e si verificherà che le attestazioni vengano presentate quando un utente accede con l'autenticazione basata su form.</span><span class="sxs-lookup"><span data-stu-id="9914a-144">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Forms authentication.</span></span>

#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="9914a-145">Per testare le attestazioni con l'applicazione Web Form ASP.NET usando l'autenticazione basata su form</span><span class="sxs-lookup"><span data-stu-id="9914a-145">To test your ASP.NET Web Forms application for claims using Forms authentication</span></span>

1. <span data-ttu-id="9914a-146">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9914a-146">Press **F5** to build and run the application.</span></span> <span data-ttu-id="9914a-147">Verrà visualizzata la pagina *Default.aspx*, con i collegamenti **Register** e **Log in** nella parte superiore destra.</span><span class="sxs-lookup"><span data-stu-id="9914a-147">You should be presented with *Default.aspx*, which has **Register** and **Log in** links in the top right of the page.</span></span> <span data-ttu-id="9914a-148">Fare clic su **Register**.</span><span class="sxs-lookup"><span data-stu-id="9914a-148">Click **Register**.</span></span>

2. <span data-ttu-id="9914a-149">Nella pagina **Register** creare un account utente e quindi fare clic su **Register**.</span><span class="sxs-lookup"><span data-stu-id="9914a-149">On the **Register** page, create a user account, and then click **Register**.</span></span> <span data-ttu-id="9914a-150">L'account verrà creato usando l'autenticazione basata su form e l'utente verrà automaticamente connesso.</span><span class="sxs-lookup"><span data-stu-id="9914a-150">Your account will be created using Forms authentication, and you will be automatically signed in.</span></span>

3. <span data-ttu-id="9914a-151">Dopo il reindirizzamento alla home page, sotto il titolo **Your Claims** dovrebbe essere visualizzata una tabella che include le informazioni sulle attestazioni **Issuer**, **OriginalIssuer**, **Type**, **Value** e **ValueType** per l'account usato.</span><span class="sxs-lookup"><span data-stu-id="9914a-151">After you have been redirected to the home page, you should see a table beneath the **Your Claims** heading that includes the **Issuer**, **OriginalIssuer**, **Type**, **Value**, and **ValueType** claims information about your account.</span></span>

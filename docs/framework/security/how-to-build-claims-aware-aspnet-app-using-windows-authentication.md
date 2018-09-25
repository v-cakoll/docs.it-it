---
title: "Procedura: Compilare un'applicazione ASP.NET in grado di riconoscere attestazioni con l'autenticazione di Windows"
ms.date: 03/30/2017
ms.assetid: 11c53d9d-d34a-44b4-8b5e-22e3eaeaee93
author: BrucePerlerMS
ms.openlocfilehash: 2c7877c452c729b30029cad1a8e17600f3dc9661
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47112426"
---
# <a name="how-to-build-claims-aware-aspnet-application-using-windows-authentication"></a><span data-ttu-id="24b93-102">Procedura: Compilare un'applicazione ASP.NET in grado di riconoscere attestazioni con l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="24b93-102">How To: Build Claims-Aware ASP.NET Application Using Windows Authentication</span></span>
## <a name="applies-to"></a><span data-ttu-id="24b93-103">Si applica a</span><span class="sxs-lookup"><span data-stu-id="24b93-103">Applies To</span></span>  
  
-   <span data-ttu-id="24b93-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="24b93-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="24b93-105">Web Form ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="24b93-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="24b93-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="24b93-106">Summary</span></span>  
 <span data-ttu-id="24b93-107">Questo argomento include le procedure dettagliate per creare una semplice applicazione Web Form ASP.NET in grado di riconoscere attestazioni che usa l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="24b93-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application that uses Windows authentication.</span></span> <span data-ttu-id="24b93-108">Sono inoltre disponibili istruzioni per testare l'applicazione per assicurarsi che le attestazioni vengano presentate quando un utente accede con l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="24b93-108">It also provides instructions for how to test the application to verify that claims are presented when a user signs in using Windows authentication.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="24b93-109">Sommario</span><span class="sxs-lookup"><span data-stu-id="24b93-109">Contents</span></span>  
  
-   <span data-ttu-id="24b93-110">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="24b93-110">Objectives</span></span>  
  
-   <span data-ttu-id="24b93-111">Panoramica</span><span class="sxs-lookup"><span data-stu-id="24b93-111">Overview</span></span>  
  
-   <span data-ttu-id="24b93-112">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="24b93-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="24b93-113">Passaggio 1: creare una semplice applicazione Web Form ASP.NET</span><span class="sxs-lookup"><span data-stu-id="24b93-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="24b93-114">Passaggio 2: configurare l'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="24b93-114">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
  
-   <span data-ttu-id="24b93-115">Passaggio 3: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="24b93-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="24b93-116">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="24b93-116">Objectives</span></span>  
  
-   <span data-ttu-id="24b93-117">Configurare un'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="24b93-117">Configure an ASP.NET Web Forms application for claims using Windows authentication</span></span>  
  
-   <span data-ttu-id="24b93-118">Testare l'applicazione Web Form ASP.NET per verificare se funziona correttamente</span><span class="sxs-lookup"><span data-stu-id="24b93-118">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="24b93-119">Panoramica</span><span class="sxs-lookup"><span data-stu-id="24b93-119">Overview</span></span>  
 <span data-ttu-id="24b93-120">In .NET 4.5, WIF e l'autorizzazione basata sulle attestazioni sono diventati parte integrante del framework.</span><span class="sxs-lookup"><span data-stu-id="24b93-120">In .NET 4.5, WIF and its claims-based authorization have been included as an integral part of the Framework.</span></span> <span data-ttu-id="24b93-121">In precedenza, per usare le attestazioni da un utente ASP.NET, era necessario installare WIF e quindi effettuare il cast delle interfacce su oggetti Principal come `Thread.CurrentPrincipal` o `HttpContext.Current.User`.</span><span class="sxs-lookup"><span data-stu-id="24b93-121">Previously, if you wanted claims from an ASP.NET user, you were required to install WIF, and then cast interfaces to Principal objects such as `Thread.CurrentPrincipal` or `HttpContext.Current.User`.</span></span> <span data-ttu-id="24b93-122">Ora le attestazioni vengono gestite automaticamente da questi oggetti Principal.</span><span class="sxs-lookup"><span data-stu-id="24b93-122">Now, claims are served automatically by these Principal objects.</span></span>  
  
 <span data-ttu-id="24b93-123">L'autenticazione di Windows ha tratto vantaggio dall'inclusione di WIF in .NET 4.5, perché a tutti gli utenti autenticati con credenziali di Windows vengono associate automaticamente le attestazioni.</span><span class="sxs-lookup"><span data-stu-id="24b93-123">Windows authentication has benefited from WIF’s inclusion in .NET 4.5 because all users authenticated by Windows credentials automatically have claims associated with them.</span></span> <span data-ttu-id="24b93-124">È possibile iniziare subito a usare queste attestazioni in un'applicazione ASP.NET che usa l'autenticazione di Windows, come illustrato di seguito in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="24b93-124">You can begin using these claims immediately in an ASP.NET application that uses Windows authentication, as this How-To demonstrates.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="24b93-125">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="24b93-125">Summary of Steps</span></span>  
  
-   <span data-ttu-id="24b93-126">Passaggio 1: creare una semplice applicazione Web Form ASP.NET</span><span class="sxs-lookup"><span data-stu-id="24b93-126">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="24b93-127">Passaggio 2: configurare l'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="24b93-127">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
  
-   <span data-ttu-id="24b93-128">Passaggio 3: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="24b93-128">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="24b93-129">Passaggio 1: creare una semplice applicazione Web Form ASP.NET</span><span class="sxs-lookup"><span data-stu-id="24b93-129">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="24b93-130">In questo passaggio si creerà una nuova applicazione Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="24b93-130">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="24b93-131">Per creare un'applicazione ASP.NET semplice</span><span class="sxs-lookup"><span data-stu-id="24b93-131">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="24b93-132">Avviare Visual Studio e quindi fare clic su **File**, **Nuovo** e **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="24b93-132">Start Visual Studio, then click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="24b93-133">Nella finestra **Nuovo progetto** fare clic su **Applicazione Web Form ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="24b93-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="24b93-134">In **Nome** immettere `TestApp` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="24b93-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="24b93-135">Dopo la creazione del progetto **TestApp** fare clic su di esso in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="24b93-135">After the **TestApp** project has been created, click on it in **Solution Explorer**.</span></span> <span data-ttu-id="24b93-136">Le proprietà del progetto verranno visualizzate nel riquadro **Proprietà** sotto a **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="24b93-136">The project’s properties will appear in the **Properties** pane below **Solution Explorer**.</span></span> <span data-ttu-id="24b93-137">Impostare la proprietà **Autenticazione di Windows** su **Abilitata**.</span><span class="sxs-lookup"><span data-stu-id="24b93-137">Set the **Windows Authentication** property to **Enabled**.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="24b93-138">L'autenticazione di Windows è disabilitata per impostazione predefinita nelle nuove applicazioni ASP.NET, pertanto è necessario abilitarla manualmente.</span><span class="sxs-lookup"><span data-stu-id="24b93-138">Windows authentication is disabled by default in new ASP.NET applications, so you must manually enable it.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-windows-authentication"></a><span data-ttu-id="24b93-139">Passaggio 2: configurare l'applicazione Web Form ASP.NET per le attestazioni usando l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="24b93-139">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
 <span data-ttu-id="24b93-140">In questo passaggio si aggiungerà una voce di configurazione al file di configurazione *Web.config* e si modificherà il file *Default.aspx* per visualizzare informazioni sulle attestazioni per un account.</span><span class="sxs-lookup"><span data-stu-id="24b93-140">In this step you will add a configuration entry to the *Web.config* configuration file and modify the *Default.aspx* file to display claims information for an account.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-using-windows-authentication"></a><span data-ttu-id="24b93-141">Per configurare l'applicazione ASP.NET per le attestazioni usando l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="24b93-141">To configure ASP.NET application for claims using Windows authentication</span></span>  
  
1.  <span data-ttu-id="24b93-142">Nel file *Default.aspx* del progetto **TestApp** sostituire il markup esistente con il seguente:</span><span class="sxs-lookup"><span data-stu-id="24b93-142">In the **TestApp** project’s *Default.aspx* file, replace the existing markup with the following:</span></span>  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Windows authenticated user.          
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
  
     <span data-ttu-id="24b93-143">Questo passaggio aggiunge un controllo GridView alla pagina *Default.aspx* che verrà popolato con le attestazioni recuperate dall'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="24b93-143">This step adds a GridView control to your *Default.aspx* page that will be populated with the claims retrieved from Windows authentication.</span></span>  
  
2.  <span data-ttu-id="24b93-144">Salvare il file *Default.aspx* e quindi aprire il relativo file code-behind denominato *Default.aspx.cs*.</span><span class="sxs-lookup"><span data-stu-id="24b93-144">Save the *Default.aspx* file, then open its code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="24b93-145">Sostituire il codice esistente con quello seguente:</span><span class="sxs-lookup"><span data-stu-id="24b93-145">Replace the existing code with the following:</span></span>  
  
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
                this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                this.ClaimsGridView.DataBind();  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="24b93-146">Il codice sopra riportato visualizzerà le attestazioni relative a un utente autenticato.</span><span class="sxs-lookup"><span data-stu-id="24b93-146">The above code will display claims about an authenticated user.</span></span>  
  
3.  <span data-ttu-id="24b93-147">Per modificare il tipo di autenticazione dell'applicazione, modificare il blocco **\<authentication>** nella sezione **\<system.web>** del file *Web.config* radice del progetto in modo che includa solo la voce di configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="24b93-147">To change the application’s authentication type, modify the **\<authentication>** block in the **\<system.web>** section of the project’s root *Web.config* file so that it only includes the following configuration entry:</span></span>  
  
    ```xml  
    <authentication mode="Windows" />  
    ```  
  
4.  <span data-ttu-id="24b93-148">Modificare infine il blocco **\<authorization>** nella sezione **\<system.web>** dello stesso file *Web.config* per forzare l'autenticazione:</span><span class="sxs-lookup"><span data-stu-id="24b93-148">Finally, modify the **\<authorization>** block in the **\<system.web>** section of the same *Web.config* file to force authentication:</span></span>  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    ```  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="24b93-149">Passaggio 3: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="24b93-149">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="24b93-150">In questo passaggio verrà testata l'applicazione Web Form ASP.NET e si verificherà che le attestazioni vengano presentate quando un utente accede con l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="24b93-150">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Windows authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-windows-authentication"></a><span data-ttu-id="24b93-151">Per testare le attestazioni con l'applicazione Web Form ASP.NET usando l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="24b93-151">To test your ASP.NET Web Forms application for claims using Windows authentication</span></span>  
  
1.  <span data-ttu-id="24b93-152">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="24b93-152">Press **F5** to build and run the application.</span></span> <span data-ttu-id="24b93-153">Verrà visualizzato il file *Default.aspx* e il nome dell'account Windows personale (incluso il nome di dominio) dovrebbe già essere visualizzato come utente autenticato in alto a destra nella pagina.</span><span class="sxs-lookup"><span data-stu-id="24b93-153">You should be presented with *Default.aspx*, and your Windows account name (including domain name) should already appear as the authenticated user in the top right of the page.</span></span> <span data-ttu-id="24b93-154">Il contenuto della pagina deve includere una tabella con le attestazioni recuperate dall'account di Windows.</span><span class="sxs-lookup"><span data-stu-id="24b93-154">The page’s content should include a table filled with claims retrieved from your Windows account.</span></span>

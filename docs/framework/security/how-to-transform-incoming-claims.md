---
title: 'Procedura: Trasformare le attestazioni in ingresso'
ms.date: 03/30/2017
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
author: BrucePerlerMS
ms.openlocfilehash: 8673b4520d9727ae1aa78ef0bc9f435defb02598
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47171322"
---
# <a name="how-to-transform-incoming-claims"></a><span data-ttu-id="afac7-102">Procedura: Trasformare le attestazioni in ingresso</span><span class="sxs-lookup"><span data-stu-id="afac7-102">How To: Transform Incoming Claims</span></span>
## <a name="applies-to"></a><span data-ttu-id="afac7-103">Si applica a</span><span class="sxs-lookup"><span data-stu-id="afac7-103">Applies To</span></span>  
  
-   <span data-ttu-id="afac7-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="afac7-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="afac7-105">Web Form ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="afac7-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="afac7-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="afac7-106">Summary</span></span>  
 <span data-ttu-id="afac7-107">Questo argomento include le procedure dettagliate per creare una semplice applicazione Web Form ASP.NET in grado di riconoscere attestazioni e trasformare le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="afac7-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application and transforming incoming claims.</span></span> <span data-ttu-id="afac7-108">Sono inoltre disponibili istruzioni su come testare l'applicazione per verificare che le attestazioni trasformate vengano presentate quando l'applicazione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="afac7-108">It also provides instructions for how to test the application to verify that transformed claims are presented when the application is run.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="afac7-109">Sommario</span><span class="sxs-lookup"><span data-stu-id="afac7-109">Contents</span></span>  
  
-   <span data-ttu-id="afac7-110">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="afac7-110">Objectives</span></span>  
  
-   <span data-ttu-id="afac7-111">Panoramica</span><span class="sxs-lookup"><span data-stu-id="afac7-111">Overview</span></span>  
  
-   <span data-ttu-id="afac7-112">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="afac7-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="afac7-113">Passaggio 1: creare una semplice applicazione Web Form ASP.NET</span><span class="sxs-lookup"><span data-stu-id="afac7-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="afac7-114">Passaggio 2: implementare la trasformazione delle attestazioni con un ClaimsAuthenticationManager personalizzato</span><span class="sxs-lookup"><span data-stu-id="afac7-114">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
  
-   <span data-ttu-id="afac7-115">Passaggio 3: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="afac7-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="afac7-116">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="afac7-116">Objectives</span></span>  
  
-   <span data-ttu-id="afac7-117">Configurare un'applicazione Web Form ASP.NET per l'autenticazione basata su attestazioni</span><span class="sxs-lookup"><span data-stu-id="afac7-117">Configure an ASP.NET Web Forms application for claims-based authentication</span></span>  
  
-   <span data-ttu-id="afac7-118">Trasformare le attestazioni in ingresso tramite l'aggiunta di un'attestazione per il ruolo di amministratore</span><span class="sxs-lookup"><span data-stu-id="afac7-118">Transform incoming claims by adding an Administrator role claim</span></span>  
  
-   <span data-ttu-id="afac7-119">Testare l'applicazione Web Form ASP.NET per verificare se funziona correttamente</span><span class="sxs-lookup"><span data-stu-id="afac7-119">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="afac7-120">Panoramica</span><span class="sxs-lookup"><span data-stu-id="afac7-120">Overview</span></span>  
 <span data-ttu-id="afac7-121">WIF espone una classe denominata <xref:System.Security.Claims.ClaimsAuthenticationManager> che consente agli utenti di modificare le attestazioni prima che vengano presentate a un'applicazione relying party.</span><span class="sxs-lookup"><span data-stu-id="afac7-121">WIF exposes a class named <xref:System.Security.Claims.ClaimsAuthenticationManager> that enables users to modify claims before they are presented to a relying party (RP) application.</span></span> <span data-ttu-id="afac7-122">La classe <xref:System.Security.Claims.ClaimsAuthenticationManager> è utile per la separazione dei compiti tra l'autenticazione e il codice dell'applicazione sottostante.</span><span class="sxs-lookup"><span data-stu-id="afac7-122">The <xref:System.Security.Claims.ClaimsAuthenticationManager> is useful for separation of concerns between authentication and the underlying application code.</span></span> <span data-ttu-id="afac7-123">L'esempio seguente dimostra come aggiungere un ruolo alle attestazioni nel <xref:System.Security.Claims.ClaimsPrincipal> in ingresso che potrebbe essere richiesto dalla relying party.</span><span class="sxs-lookup"><span data-stu-id="afac7-123">The example below demonstrates how to add a role to the claims in the incoming <xref:System.Security.Claims.ClaimsPrincipal> that may be required by the RP.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="afac7-124">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="afac7-124">Summary of Steps</span></span>  
  
-   <span data-ttu-id="afac7-125">Passaggio 1: creare una semplice applicazione Web Form ASP.NET</span><span class="sxs-lookup"><span data-stu-id="afac7-125">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="afac7-126">Passaggio 2: implementare la trasformazione delle attestazioni con un ClaimsAuthenticationManager personalizzato</span><span class="sxs-lookup"><span data-stu-id="afac7-126">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
  
-   <span data-ttu-id="afac7-127">Passaggio 3: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="afac7-127">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="afac7-128">Passaggio 1: creare una semplice applicazione Web Form ASP.NET</span><span class="sxs-lookup"><span data-stu-id="afac7-128">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="afac7-129">In questo passaggio si creerà una nuova applicazione Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="afac7-129">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="afac7-130">Per creare un'applicazione ASP.NET semplice</span><span class="sxs-lookup"><span data-stu-id="afac7-130">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="afac7-131">Avviare Visual Studio come amministratore in modalità con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="afac7-131">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2.  <span data-ttu-id="afac7-132">In Visual Studio fare clic su **File**, **Nuovo** e quindi su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="afac7-132">In Visual Studio, click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="afac7-133">Nella finestra **Nuovo progetto** fare clic su **Applicazione Web Form ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="afac7-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
4.  <span data-ttu-id="afac7-134">In **Nome** immettere `TestApp` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="afac7-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
5.  <span data-ttu-id="afac7-135">Fare clic con il pulsante destro del mouse sul progetto **TestApp** in **Esplora soluzioni** e quindi scegliere **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="afac7-135">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
6.  <span data-ttu-id="afac7-136">Verrà visualizzata la finestra **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="afac7-136">The **Identity and Access** window appears.</span></span> <span data-ttu-id="afac7-137">In **Providers** (Provider) selezionare **Test your application with the Local Development STS** (Testare l'applicazione con il servizio token di sicurezza per lo sviluppo locale) e quindi fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="afac7-137">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
7.  <span data-ttu-id="afac7-138">Nel file *Default.aspx* sostituire il markup esistente con il seguente e quindi salvare il file:</span><span class="sxs-lookup"><span data-stu-id="afac7-138">In the *Default.aspx* file, replace the existing markup with the following, then save the file:</span></span>  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
          <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
    ```  
  
8.  <span data-ttu-id="afac7-139">Aprire il file code-behind denominato *Default.aspx.cs*.</span><span class="sxs-lookup"><span data-stu-id="afac7-139">Open the code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="afac7-140">Sostituire il codice esistente con il seguente e quindi salvare il file:</span><span class="sxs-lookup"><span data-stu-id="afac7-140">Replace the existing code with the following, then save the file:</span></span>  
  
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
  
## <a name="step-2--implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a><span data-ttu-id="afac7-141">Passaggio 2: implementare la trasformazione delle attestazioni con un ClaimsAuthenticationManager personalizzato</span><span class="sxs-lookup"><span data-stu-id="afac7-141">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
 <span data-ttu-id="afac7-142">In questo passaggio si eseguirà l'override di funzionalità predefinite nella classe <xref:System.Security.Claims.ClaimsAuthenticationManager> per aggiungere un ruolo di amministratore per l'entità di sicurezza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="afac7-142">In this step you will override default functionality in the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to add an Administrator role to the incoming Principal.</span></span>  
  
#### <a name="to-implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a><span data-ttu-id="afac7-143">Per implementare la trasformazione delle attestazioni con un ClaimsAuthenticationManager personalizzato</span><span class="sxs-lookup"><span data-stu-id="afac7-143">To implement claims transformation using a custom ClaimsAuthenticationManager</span></span>  
  
1.  <span data-ttu-id="afac7-144">In Visual Studio fare clic con il pulsante destro del mouse sulla soluzione, scegliere **Aggiungi** e quindi fare clic su **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="afac7-144">In Visual Studio, right-click the on the solution, click **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="afac7-145">Nella finestra **Aggiungi nuovo progetto** selezionare **Libreria di classi** nell'elenco dei modelli di **Visual C#**, immettere `ClaimsTransformation` e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="afac7-145">In the **Add New Project** window, select **Class Library** from the **Visual C#** templates list, enter `ClaimsTransformation`, and then press **OK**.</span></span> <span data-ttu-id="afac7-146">Il nuovo progetto verrà creato nella cartella della soluzione.</span><span class="sxs-lookup"><span data-stu-id="afac7-146">The new project will be created in your solution folder.</span></span>  
  
3.  <span data-ttu-id="afac7-147">Fare clic con il pulsante destro del mouse su **Riferimenti** nel progetto **ClaimsTransformation** e quindi scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="afac7-147">Right-click on **References** under the **ClaimsTransformation** project, and then click **Add Reference**.</span></span>  
  
4.  <span data-ttu-id="afac7-148">Nella finestra **Gestione riferimenti** selezionare **System.IdentityModel** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="afac7-148">In the **Reference Manager** window, select **System.IdentityModel**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="afac7-149">Aprire **Class1.cs** oppure, se non esiste, fare clic con il pulsante destro del mouse su **ClaimsTransformation**, scegliere **Aggiungi** e quindi fare clic su **Classe**.</span><span class="sxs-lookup"><span data-stu-id="afac7-149">Open **Class1.cs**, or if it doesn’t exist, right-click **ClaimsTransformation**, click **Add**, then click **Class…**</span></span>  
  
6.  <span data-ttu-id="afac7-150">Aggiungere le direttive using seguenti al file di codice:</span><span class="sxs-lookup"><span data-stu-id="afac7-150">Add the following using directives to the code file:</span></span>  
  
    ```csharp  
    using System.Security.Claims;  
    using System.Security.Principal;  
    ```  
  
7.  <span data-ttu-id="afac7-151">Aggiungere la classe e il metodo seguenti nel file di codice.</span><span class="sxs-lookup"><span data-stu-id="afac7-151">Add the following class and method in the code file.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="afac7-152">Il codice seguente è solo a scopo dimostrativo. Assicurarsi di verificare le autorizzazioni previste nel codice di produzione.</span><span class="sxs-lookup"><span data-stu-id="afac7-152">The following code is for demonstration purposes only; make sure that you verify your intended permissions in production code.</span></span>  
  
    ```csharp  
    public class ClaimsTransformationModule : ClaimsAuthenticationManager  
    {  
        public override ClaimsPrincipal Authenticate(string resourceName, ClaimsPrincipal incomingPrincipal)  
        {  
            if (incomingPrincipal != null && incomingPrincipal.Identity.IsAuthenticated == true)  
            {  
               ((ClaimsIdentity)incomingPrincipal.Identity).AddClaim(new Claim(ClaimTypes.Role, "Admin"));  
            }  
  
            return incomingPrincipal;  
        }  
    }  
    ```  
  
8.  <span data-ttu-id="afac7-153">Salvare il file e compilare il progetto **ClaimsTransformation**.</span><span class="sxs-lookup"><span data-stu-id="afac7-153">Save the file and build the **ClaimsTransformation** project.</span></span>  
  
9. <span data-ttu-id="afac7-154">Nel progetto ASP.NET **TestApp** fare clic con il pulsante destro del mouse su Riferimenti e quindi scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="afac7-154">In your **TestApp** ASP.NET project, right-click on References, and then click **Add Reference**.</span></span>  
  
10. <span data-ttu-id="afac7-155">Nella finestra **Gestione riferimenti** selezionare **Soluzione** nel menu a sinistra, selezionare **ClaimsTransformation** tra le opzioni compilate e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="afac7-155">In the **Reference Manager** window, select **Solution** from the left menu, select **ClaimsTransformation** from the populated options, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="afac7-156">Nel file **Web.config** radice passare alla voce **\<system.identityModel>**.</span><span class="sxs-lookup"><span data-stu-id="afac7-156">In the root **Web.config** file, navigate to the **\<system.identityModel>** entry.</span></span> <span data-ttu-id="afac7-157">Aggiungere la riga seguente negli elementi  **\<identityConfiguration >** e salvare il file:</span><span class="sxs-lookup"><span data-stu-id="afac7-157">Within the **\<identityConfiguration>** elements, add the following line and save the file:</span></span>  
  
    ```xml  
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />  
    ```  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="afac7-158">Passaggio 3: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="afac7-158">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="afac7-159">In questo passaggio verrà testata l'applicazione Web Form ASP.NET e si verificherà che le attestazioni vengano presentate quando un utente accede con l'autenticazione basata su form.</span><span class="sxs-lookup"><span data-stu-id="afac7-159">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Forms authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="afac7-160">Per testare le attestazioni con l'applicazione Web Form ASP.NET usando l'autenticazione basata su form</span><span class="sxs-lookup"><span data-stu-id="afac7-160">To test your ASP.NET Web Forms application for claims using Forms authentication</span></span>  
  
1.  <span data-ttu-id="afac7-161">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="afac7-161">Press **F5** to build and run the application.</span></span> <span data-ttu-id="afac7-162">Dovrebbe essere visualizzato il file *Default.aspx*.</span><span class="sxs-lookup"><span data-stu-id="afac7-162">You should be presented with *Default.aspx*.</span></span>  
  
2.  <span data-ttu-id="afac7-163">Nella pagina *Default.aspx* dovrebbe essere visualizzata una tabella sotto il titolo **Your Claims** che include le informazioni sulle attestazioni **Issuer**, **OriginalIssuer**, **Type**, **Value** e **ValueType** per l'account usato.</span><span class="sxs-lookup"><span data-stu-id="afac7-163">On the *Default.aspx* page, you should see a table beneath the **Your Claims** heading that includes the **Issuer**, **OriginalIssuer**, **Type**, **Value**, and **ValueType** claims information about your account.</span></span> <span data-ttu-id="afac7-164">L'ultima riga dovrebbe essere come la seguente:</span><span class="sxs-lookup"><span data-stu-id="afac7-164">The last row should be presented in the following way:</span></span>  
  
    ||||||  
    |-|-|-|-|-|  
    |<span data-ttu-id="afac7-165">LOCAL AUTHORITY</span><span class="sxs-lookup"><span data-stu-id="afac7-165">LOCAL AUTHORITY</span></span>|<span data-ttu-id="afac7-166">LOCAL AUTHORITY</span><span class="sxs-lookup"><span data-stu-id="afac7-166">LOCAL AUTHORITY</span></span>|http://schemas.microsoft.com/ws/2008/06/identity/claims/role|<span data-ttu-id="afac7-167">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="afac7-167">Admin</span></span>|http://www.w3.org/2001/XMLSchema#string|

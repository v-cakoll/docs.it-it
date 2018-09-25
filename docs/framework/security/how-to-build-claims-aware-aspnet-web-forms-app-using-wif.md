---
title: "Procedura: Compilare un'applicazione Web Form ASP.NET in grado di riconoscere attestazioni con WIF"
ms.date: 03/30/2017
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
author: BrucePerlerMS
ms.openlocfilehash: 83b5808ced1bc6243294b23d9784ec7993e3ba4a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47108130"
---
# <a name="how-to-build-claims-aware-aspnet-web-forms-application-using-wif"></a><span data-ttu-id="8792a-102">Procedura: Compilare un'applicazione Web Form ASP.NET in grado di riconoscere attestazioni con WIF</span><span class="sxs-lookup"><span data-stu-id="8792a-102">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="8792a-103">Si applica a</span><span class="sxs-lookup"><span data-stu-id="8792a-103">Applies To</span></span>  
  
-   <span data-ttu-id="8792a-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="8792a-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="8792a-105">Web Form ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="8792a-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="8792a-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="8792a-106">Summary</span></span>  
 <span data-ttu-id="8792a-107">Questo argomento include le procedure dettagliate per creare una semplice applicazione Web Form ASP.NET in grado di riconoscere attestazioni.</span><span class="sxs-lookup"><span data-stu-id="8792a-107">This How-To provides detailed step-by-step procedures for creating simple claims-aware ASP.NET Web Forms application.</span></span> <span data-ttu-id="8792a-108">Sono inoltre disponibili istruzioni su come testare la semplice applicazione Web Form ASP.NET in grado di riconoscere attestazioni per la corretta implementazione dell'autenticazione federata.</span><span class="sxs-lookup"><span data-stu-id="8792a-108">It also provides instructions for how to test the simple claims-aware ASP.NET Web Forms application for successful implementation of federated authentication.</span></span> <span data-ttu-id="8792a-109">La procedura decritta in questo argomento non include istruzioni dettagliate per la creazione di un servizio token di sicurezza e presuppone che il servizio sia già stato configurato.</span><span class="sxs-lookup"><span data-stu-id="8792a-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and assumes you have already configured an STS.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="8792a-110">Sommario</span><span class="sxs-lookup"><span data-stu-id="8792a-110">Contents</span></span>  
  
-   <span data-ttu-id="8792a-111">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="8792a-111">Objectives</span></span>  
  
-   <span data-ttu-id="8792a-112">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="8792a-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="8792a-113">Passaggio 1: creare una semplice applicazione Web Form ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8792a-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="8792a-114">Passaggio 2: configurare l'applicazione Web Form ASP.NET per l'autenticazione basata su attestazioni</span><span class="sxs-lookup"><span data-stu-id="8792a-114">Step 2 – Configure ASP.NET Web Forms Application for Claims-Based Authentication</span></span>  
  
-   <span data-ttu-id="8792a-115">Passaggio 3: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="8792a-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="8792a-116">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="8792a-116">Objectives</span></span>  
  
-   <span data-ttu-id="8792a-117">Configurare l'applicazione Web Form ASP.NET per l'autenticazione basata su attestazioni</span><span class="sxs-lookup"><span data-stu-id="8792a-117">Configure ASP.NET Web Forms application for claims-based authentication</span></span>  
  
-   <span data-ttu-id="8792a-118">Testare l'applicazione Web Form ASP.NET in grado di riconoscere attestazioni</span><span class="sxs-lookup"><span data-stu-id="8792a-118">Test successful claims-aware ASP.NET Web Forms application</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="8792a-119">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="8792a-119">Summary of Steps</span></span>  
  
-   <span data-ttu-id="8792a-120">Passaggio 1: creare una semplice applicazione Web Form ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8792a-120">Step 1 – Create Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="8792a-121">Passaggio 2: configurare l'applicazione Web Form ASP.NET per l'autenticazione federata</span><span class="sxs-lookup"><span data-stu-id="8792a-121">Step 2 – Configure ASP.NET Web Forms Application for Federated Authentication</span></span>  
  
-   <span data-ttu-id="8792a-122">Passaggio 3: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="8792a-122">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="8792a-123">Passaggio 1: creare una semplice applicazione Web Form ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8792a-123">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="8792a-124">In questo passaggio si creerà una nuova applicazione Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="8792a-124">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="8792a-125">Per creare un'applicazione ASP.NET semplice</span><span class="sxs-lookup"><span data-stu-id="8792a-125">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="8792a-126">Avviare Visual Studio e fare clic su **File**, **Nuovo** e **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="8792a-126">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="8792a-127">Nella finestra **Nuovo progetto** fare clic su **Applicazione Web Form ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="8792a-127">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="8792a-128">In **Nome** immettere `TestApp` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8792a-128">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-based-authentication"></a><span data-ttu-id="8792a-129">Passaggio 2: configurare l'applicazione Web Form ASP.NET per l'autenticazione basata su attestazioni</span><span class="sxs-lookup"><span data-stu-id="8792a-129">Step 2 – Configure ASP.NET Web Forms Application for Claims-Based Authentication</span></span>  
 <span data-ttu-id="8792a-130">In questo passaggio si aggiungeranno voci di configurazione al file di configurazione *Web.config* dell'applicazione Web Form ASP.NET per renderla in grado di riconoscere attestazioni.</span><span class="sxs-lookup"><span data-stu-id="8792a-130">In this step you will add configuration entries to the *Web.config* configuration file of your ASP.NET Web Forms application to make it claims-aware.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-based-authentication"></a><span data-ttu-id="8792a-131">Per configurare l'applicazione ASP.NET per l'autenticazione basata su attestazioni</span><span class="sxs-lookup"><span data-stu-id="8792a-131">To configure ASP.NET application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="8792a-132">Aggiungere le seguenti voci di sezione di configurazione al file di configurazione *Web.config* subito dopo l'elemento di apertura **\<configuration>**:</span><span class="sxs-lookup"><span data-stu-id="8792a-132">Add the following configuration section entries to the *Web.config* configuration file immediately after the **\<configuration>** opening element:</span></span>  
  
    ```xml  
    <configSections>  
      <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
      <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  <span data-ttu-id="8792a-133">Aggiungere un **elemento \<location>** che consente l'accesso ai metadati di federazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="8792a-133">Add a **\<location>** element that enables access to the application’s federation metadata:</span></span>  
  
    ```xml  
    <location path="FederationMetadata">  
      <system.web>  
        <authorization>  
          <allow users="*" />  
        </authorization>  
      </system.web>  
    </location>  
    ```  
  
3.  <span data-ttu-id="8792a-134">Aggiungere le seguenti voci di configurazione all'interno di elementi **\<system.web>** per negare le autorizzazioni agli utenti, disabilitare l'autenticazione nativa e abilitare WIF per gestire l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="8792a-134">Add the following configuration entries within the **\<system.web>** elements to deny users, disable native authentication, and enable WIF to manage authentication.</span></span>  
  
    ```xml  
    <authorization>  
      <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  <span data-ttu-id="8792a-135">Aggiungere un elemento **\<system.webServer>** che definisce i moduli per l'autenticazione federata.</span><span class="sxs-lookup"><span data-stu-id="8792a-135">Add a **\<system.webServer>** element that defines the modules for federated authentication.</span></span> <span data-ttu-id="8792a-136">Si noti che l'attributo *PublicKeyToken* deve essere uguale all'attributo *PublicKeyToken* per le voci **\<configSections>** aggiunte in precedenza:</span><span class="sxs-lookup"><span data-stu-id="8792a-136">Note that the *PublicKeyToken* attribute must be the same as the *PublicKeyToken* attribute for the **\<configSections>** entries added earlier:</span></span>  
  
    ```xml  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5.  <span data-ttu-id="8792a-137">Aggiungere le voci di configurazione correlate a Windows Identity Foundation seguenti e assicurarsi che l'URL e il numero di porta dell'applicazione ASP.NET corrispondano ai valori nella voce **\<audienceUris>**, all'attributo **realm** dell'elemento **\<wsFederation>** e all'attributo **reply** dell'elemento **\<wsFederation>**.</span><span class="sxs-lookup"><span data-stu-id="8792a-137">Add the following Windows Identity Foundation related configuration entries and ensure that your ASP.NET application’s URL and port number match the values in the **\<audienceUris>** entry, **realm** attribute of the **\<wsFederation>** element, and the **reply** attribute of the **\<wsFederation>** element.</span></span> <span data-ttu-id="8792a-138">Assicurarsi anche che il valore **issuer** sia appropriato per l'URL del servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8792a-138">Also ensure that the **issuer** value fits your Security Token Service (STS) URL.</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <audienceUris>  
                <add value="http://localhost:28503/" />  
            </audienceUris>  
            <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
                <trustedIssuers>  
                    <add thumbprint="1234567890ABCDEFGHIJKLMNOPQRSTUVWXYZ1234" name="YourSTSName" />  
                </trustedIssuers>   
            </issuerNameRegistry>  
            <certificateValidation certificateValidationMode="None" />  
        </identityConfiguration>  
    </system.identityModel>  
    <system.identityModel.services>  
        <federationConfiguration>  
            <cookieHandler requireSsl="true" />  
            <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:13922/wsFederationSTS/Issue" realm="http://localhost:28503/" reply="http://localhost:28503/" requireHttps="true" />  
        </federationConfiguration>  
    </system.identityModel.services>  
    ```  
  
6.  <span data-ttu-id="8792a-139">Aggiungere un riferimento all'assembly <xref:System.IdentityModel>.</span><span class="sxs-lookup"><span data-stu-id="8792a-139">Add reference to the <xref:System.IdentityModel> assembly.</span></span>  
  
7.  <span data-ttu-id="8792a-140">Compilare la soluzione e assicurarsi che non ci siano errori.</span><span class="sxs-lookup"><span data-stu-id="8792a-140">Compile the solution to make sure there are no errors.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="8792a-141">Passaggio 3: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="8792a-141">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="8792a-142">In questo passaggio si testerà l'applicazione Web Form ASP.NET configurata per l'autenticazione basata sulle attestazioni.</span><span class="sxs-lookup"><span data-stu-id="8792a-142">In this step you will test your ASP.NET Web Forms application configured for claims-based authentication.</span></span> <span data-ttu-id="8792a-143">Per eseguire un test di base, si aggiungerà codice che visualizza le attestazioni nel token rilasciato dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8792a-143">To perform a basic test, you will add code that displays claims in the token issued by the Security Token Service (STS).</span></span>  
  
#### <a name="to-test-your-aspnet-web-form-application-for-claims-based-authentication"></a><span data-ttu-id="8792a-144">Per testare l'applicazione Web Form ASP.NET per l'autenticazione basata su attestazioni</span><span class="sxs-lookup"><span data-stu-id="8792a-144">To test your ASP.NET Web Form application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="8792a-145">Aprire il file **Default.aspx** nel progetto **TestApp** e sostituire il markup esistente con quello seguente:</span><span class="sxs-lookup"><span data-stu-id="8792a-145">Open the **Default.aspx** file under the **TestApp** project and replace its existing markup with the following markup:</span></span>  
  
    ```  
    %@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head id="Head1" runat="server">  
        <title></title>  
    </head>  
    <body>  
        <h1><asp:label ID="signedIn" runat="server" /></h1>  
        <asp:label ID="claimType" runat="server" />  
        <asp:label ID="claimValue" runat="server" />  
        <asp:label ID="claimValueType" runat="server" />  
        <asp:label ID="claimSubjectName" runat="server" />  
        <asp:label ID="claimIssuer" runat="server" />  
    </body>  
    </html>  
    ```  
  
2.  <span data-ttu-id="8792a-146">Salvare **Default.aspx** e quindi aprire il file code-behind denominato **Default.aspx.cs**.</span><span class="sxs-lookup"><span data-stu-id="8792a-146">Save **Default.aspx**, and then open its code behind file named **Default.aspx.cs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8792a-147">Il file **Default.aspx.cs** potrebbe essere nascosto sotto **Default.aspx** in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="8792a-147">**Default.aspx.cs** may be hidden beneath **Default.aspx** in Solution Explorer.</span></span> <span data-ttu-id="8792a-148">Se **Default.aspx.cs** non è visibile, espandere **Default.aspx** facendo clic sul triangolo accanto.</span><span class="sxs-lookup"><span data-stu-id="8792a-148">If **Default.aspx.cs** is not visible, expand **Default.aspx** by clicking on the triangle next to it.</span></span>  
  
3.  <span data-ttu-id="8792a-149">Sostituire il codice esistente nel metodo **Page_Load** in **Default.aspx.cs** con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8792a-149">Replace the existing code in the **Page_Load** method of **Default.aspx.cs** with the following code:</span></span>  
  
    ```csharp  
    using System;  
    using System.IdentityModel;  
    using System.Security.Claims;  
    using System.Threading;  
    using System.Web.UI;  
  
    namespace TestApp  
    {  
        public partial class _Default : System.Web.UI.Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
                if (claimsPrincipal != null)  
                {  
                    signedIn.Text = "You are signed in.";  
  
                    foreach (Claim claim in claimsPrincipal.Claims)  
                    {  
                        claimType.Text = claim.Type;  
                        claimValue.Text = claim.Value;  
                        claimValueType.Text = claim.ValueType;  
                        claimSubjectName.Text = claim.Subject.Name;  
                        claimIssuer.Text = claim.Issuer;  
                    }  
                }  
                else  
                {  
                    signedIn.Text = "You are not signed in.";  
                }  
            }  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="8792a-150">Salvare **Default.aspx.cs** e compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="8792a-150">Save **Default.aspx.cs**, and build the solution.</span></span>  
  
5.  <span data-ttu-id="8792a-151">Eseguire la soluzione premendo **F5**.</span><span class="sxs-lookup"><span data-stu-id="8792a-151">Run the solution by pressing the **F5** key.</span></span>  
  
6.  <span data-ttu-id="8792a-152">Dovrebbe essere visualizzata la pagina che mostra le attestazioni nel token emesso dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8792a-152">You should be presented with the page that displays the claims in the token that was issued to you by the Security Token Service.</span></span>

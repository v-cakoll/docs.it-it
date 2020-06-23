---
title: 'Procedura: configurare un servizio WCF ospitato da IIS con SSL'
description: Informazioni su come configurare un servizio WCF ospitato da IIS per l'utilizzo della sicurezza del trasporto HTTP, che richiede un certificato registrato con IIS.
ms.date: 03/30/2017
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
ms.openlocfilehash: 8dc4692863d93e407a122c0ba93ae38323b8b213
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245258"
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a><span data-ttu-id="3f7d5-103">Procedura: configurare un servizio WCF ospitato da IIS con SSL</span><span class="sxs-lookup"><span data-stu-id="3f7d5-103">How to: Configure an IIS-hosted WCF service with SSL</span></span>
<span data-ttu-id="3f7d5-104">In questo argomento viene descritto come configurare l'uso della sicurezza del trasporto HTTP in un servizio WCF ospitato da IIS.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-104">This topic describes how to set up an IIS-hosted WCF service to use HTTP transport security.</span></span> <span data-ttu-id="3f7d5-105">La sicurezza del trasporto HTTP richiede che un certificato SSL sia registrato con IIS.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-105">HTTP transport security requires an SSL certificate to be registered with IIS.</span></span> <span data-ttu-id="3f7d5-106">Se non si dispone di un certificato SSL, è possibile usare IIS per generare un certificato di prova.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-106">If you do not have an SSL certificate you can use IIS to generate a test certificate.</span></span> <span data-ttu-id="3f7d5-107">Sarà quindi necessario aggiungere un'associazione SSL al sito Web e configurare le proprietà di autenticazione del sito Web.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-107">Next you must add an SSL binding to the web site and configure the web site’s authentication properties.</span></span> <span data-ttu-id="3f7d5-108">Infine sarà necessario configurare l'uso di HTTPS da parte del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-108">Finally you need to configure the WCF service to use HTTPS.</span></span>  
  
### <a name="creating-a-self-signed-certificate"></a><span data-ttu-id="3f7d5-109">Creazione di un certificato autofirmato</span><span class="sxs-lookup"><span data-stu-id="3f7d5-109">Creating a Self-Signed Certificate</span></span>  
  
1. <span data-ttu-id="3f7d5-110">Aprire Gestione Internet Information Services (inetmgr.exe) e selezionare il nome del computer nella visualizzazione albero a sinistra.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-110">Open Internet Information Services Manager (inetmgr.exe), and select your computer name in the left-hand tree view.</span></span> <span data-ttu-id="3f7d5-111">Sul lato destro della schermata selezionare Certificati server.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-111">On the right-hand side of the screen select Server Certificates</span></span>  
  
     <span data-ttu-id="3f7d5-112">![Schermata iniziale di Gestione IIS](media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span><span class="sxs-lookup"><span data-stu-id="3f7d5-112">![IIS Manager Home Screen](media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span></span>  
  
2. <span data-ttu-id="3f7d5-113">Nella finestra certificati server fare clic su **Crea certificato autofirmato....**</span><span class="sxs-lookup"><span data-stu-id="3f7d5-113">In the Server Certificates window click the **Create Self-Signed Certificate….**</span></span> <span data-ttu-id="3f7d5-114">.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-114">Link.</span></span>  
  
     <span data-ttu-id="3f7d5-115">![Creazione di un certificato auto&#45;firmato con IIS](media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span><span class="sxs-lookup"><span data-stu-id="3f7d5-115">![Creating a self&#45;signed certificate with IIS](media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span></span>  
  
3. <span data-ttu-id="3f7d5-116">Immettere un nome descrittivo per il certificato autofirmato e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-116">Enter a friendly name for the self-signed certificate and click **OK**.</span></span>  
  
     <span data-ttu-id="3f7d5-117">![Finestra di dialogo Crea certificato firmato autonomamente&#45;](media/mg-mycert.jpg "mg_MyCert")</span><span class="sxs-lookup"><span data-stu-id="3f7d5-117">![Create Self&#45;Signed Certificate Dialog](media/mg-mycert.jpg "mg_MyCert")</span></span>  
  
     <span data-ttu-id="3f7d5-118">I dettagli del certificato autofirmato appena creato vengono ora visualizzati nella finestra **certificati server** .</span><span class="sxs-lookup"><span data-stu-id="3f7d5-118">The newly created self-signed certificate details are now shown in the **Server Certificates** window.</span></span>  
  
     <span data-ttu-id="3f7d5-119">![Finestra Certificati del server](media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span><span class="sxs-lookup"><span data-stu-id="3f7d5-119">![Server Certificate Window](media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span></span>  
  
     <span data-ttu-id="3f7d5-120">Il certificato generato viene installato nell'archivio Autorità di certificazione radice disponibile nell'elenco locale.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-120">The generated certificate is installed in the Trusted Root Certification Authorities store.</span></span>  
  
### <a name="add-ssl-binding"></a><span data-ttu-id="3f7d5-121">Aggiungere l'associazione SSL</span><span class="sxs-lookup"><span data-stu-id="3f7d5-121">Add SSL Binding</span></span>  
  
1. <span data-ttu-id="3f7d5-122">Sempre in Gestione Internet Information Services espandere la cartella **siti** , quindi la cartella **sito Web predefinito** nella visualizzazione albero sul lato sinistro della schermata.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-122">Still in Internet Information Services Manager, expand the **Sites** folder and then the **Default Web Site** folder in the tree view on the left-hand side of the screen.</span></span>  
  
2. <span data-ttu-id="3f7d5-123">Fare clic sui **Binding....**</span><span class="sxs-lookup"><span data-stu-id="3f7d5-123">Click the **Bindings….**</span></span> <span data-ttu-id="3f7d5-124">Collegamento nella sezione **azioni** nella parte superiore destra della finestra.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-124">Link in the **Actions** section in the upper right hand portion of the window.</span></span>  
  
     <span data-ttu-id="3f7d5-125">![Aggiunta di un'associazione SSL](media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span><span class="sxs-lookup"><span data-stu-id="3f7d5-125">![Adding an SSL binding](media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span></span>  
  
3. <span data-ttu-id="3f7d5-126">Nella finestra Binding sito fare clic sul pulsante **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="3f7d5-126">In the Site Bindings window click the **Add** button.</span></span>  
  
     <span data-ttu-id="3f7d5-127">![Finestra di dialogo Binding del sito](media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span><span class="sxs-lookup"><span data-stu-id="3f7d5-127">![Site Bindings Dialog](media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span></span>  
  
4. <span data-ttu-id="3f7d5-128">Nella finestra di dialogo **Aggiungi binding sito** selezionare HTTPS per il tipo e il nome descrittivo del certificato autofirmato appena creato.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-128">In the **Add Site Binding** dialog, select https for the type and the friendly name of the self-signed certificate you just created.</span></span>  
  
     <span data-ttu-id="3f7d5-129">![Esempio di associazione sito](media/mg-mycertbinding.jpg "mg_MyCertBinding")</span><span class="sxs-lookup"><span data-stu-id="3f7d5-129">![Site binding example](media/mg-mycertbinding.jpg "mg_MyCertBinding")</span></span>  
  
### <a name="configure-virtual-directory-for-ssl"></a><span data-ttu-id="3f7d5-130">Configurare la directory virtuale per SSL</span><span class="sxs-lookup"><span data-stu-id="3f7d5-130">Configure Virtual Directory for SSL</span></span>  
  
1. <span data-ttu-id="3f7d5-131">In Gestione Internet Information Services selezionare la directory virtuale contenente il servizio protetto WCF.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-131">Still in Internet Information Services Manager, select the virtual directory that contains your WCF secure service.</span></span>  
  
2. <span data-ttu-id="3f7d5-132">Nel riquadro centrale della finestra selezionare **Impostazioni SSL** nella sezione IIS.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-132">In the center pane of the window, select **SSL Settings** in the IIS section.</span></span>  
  
     <span data-ttu-id="3f7d5-133">![Impostazioni SSL per la directory virtuale](media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span><span class="sxs-lookup"><span data-stu-id="3f7d5-133">![SSL Settings for virtual directory](media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span></span>  
  
3. <span data-ttu-id="3f7d5-134">Nel riquadro Impostazioni SSL selezionare la casella di controllo **Richiedi SSL** e fare clic sul collegamento **applica** nella sezione **azioni** sul lato destro dello schermo.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-134">In the SSL Settings pane, select the **Require SSL** checkbox and click the **Apply** link in the **Actions** section on the right hand side of the screen.</span></span>  
  
     <span data-ttu-id="3f7d5-135">![Impostazioni SSL della directory virtuale](media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span><span class="sxs-lookup"><span data-stu-id="3f7d5-135">![Virtual directory SSL settings](media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span></span>  
  
### <a name="configure-wcf-service-for-http-transport-security"></a><span data-ttu-id="3f7d5-136">Configurare il servizio WCF per la sicurezza del trasporto HTTP</span><span class="sxs-lookup"><span data-stu-id="3f7d5-136">Configure WCF Service for HTTP Transport Security</span></span>  
  
1. <span data-ttu-id="3f7d5-137">Nel file web.config del servizio WCF configurare l'uso della sicurezza del trasporto da parte dell'associazione HTTP come illustrato nel codice XML seguente.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-137">In the WCF service’s web.config configure the HTTP binding to use transport security as shown in the following XML.</span></span>  
  
    ```xml  
    <bindings>  
          <basicHttpBinding>  
            <binding name="secureHttpBinding">  
              <security mode="Transport">  
                <transport clientCredentialType="None"/>  
              </security>  
            </binding>  
          </basicHttpBinding>  
    </bindings>  
    ```  
  
2. <span data-ttu-id="3f7d5-138">Specificare il servizio e il relativo endpoint come illustrato nel codice XML seguente.</span><span class="sxs-lookup"><span data-stu-id="3f7d5-138">Specify your service and service endpoint as shown in the following XML.</span></span>  
  
    ```xml  
    <services>  
          <service name="MySecureWCFService.Service1">  
            <endpoint address=""  
                      binding="basicHttpBinding"  
                      bindingConfiguration="secureHttpBinding"  
                      contract="MySecureWCFService.IService1"/>  
  
            <endpoint address="mex"  
                      binding="mexHttpsBinding"  
                      contract="IMetadataExchange" />  
          </service>  
    </services>  
    ```  
  
## <a name="example"></a><span data-ttu-id="3f7d5-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="3f7d5-139">Example</span></span>  
 <span data-ttu-id="3f7d5-140">Di seguito è riportato un esempio completo di un file web.config per un servizio WCF in cui è usata la sicurezza del trasporto HTTP</span><span class="sxs-lookup"><span data-stu-id="3f7d5-140">The following is a complete example of a web.config file for a WCF service using HTTP transport security</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <services>  
      <service name="MySecureWCFService.Service1">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="secureHttpBinding"  
                  contract="MySecureWCFService.IService1"/>  
  
        <endpoint address="mex"  
                  binding="mexHttpsBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="secureHttpBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <!-- To avoid disclosing metadata information, set the value below to false and remove the metadata endpoint above before deployment -->  
          <serviceMetadata httpsGetEnabled="true"/>  
          <!-- To receive exception details in faults for debugging purposes, set the value below to true.  Set to false before deployment to avoid disclosing exception information -->  
          <serviceDebug includeExceptionDetailInFaults="false"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
  </system.serviceModel>  
  <system.webServer>  
    <modules runAllManagedModulesForAllRequests="true"/>  
  </system.webServer>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f7d5-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f7d5-141">See also</span></span>

- [<span data-ttu-id="3f7d5-142">Host in Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="3f7d5-142">Hosting in Internet Information Services</span></span>](hosting-in-internet-information-services.md)
- [<span data-ttu-id="3f7d5-143">Istruzioni per l'hosting su IIS (Internet Information Services)</span><span class="sxs-lookup"><span data-stu-id="3f7d5-143">Internet Information Service Hosting Instructions</span></span>](../samples/internet-information-service-hosting-instructions.md)
- [<span data-ttu-id="3f7d5-144">Procedure consigliate per l'hosting in Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="3f7d5-144">Internet Information Services Hosting Best Practices</span></span>](internet-information-services-hosting-best-practices.md)
- [<span data-ttu-id="3f7d5-145">Hosting IIS mediante il codice inline</span><span class="sxs-lookup"><span data-stu-id="3f7d5-145">IIS Hosting Using Inline Code</span></span>](../samples/iis-hosting-using-inline-code.md)

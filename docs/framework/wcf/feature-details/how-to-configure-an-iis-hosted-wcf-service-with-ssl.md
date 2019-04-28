---
title: 'Procedura: Configurare un servizio WCF ospitato da IIS con SSL'
ms.date: 03/30/2017
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
ms.openlocfilehash: 8d3bbb1ceab8a3bc7e5e209fda29fd574110b4f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699997"
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a><span data-ttu-id="62420-102">Procedura: Configurare un servizio WCF ospitato da IIS con SSL</span><span class="sxs-lookup"><span data-stu-id="62420-102">How to: Configure an IIS-hosted WCF service with SSL</span></span>
<span data-ttu-id="62420-103">In questo argomento viene descritto come configurare l'uso della sicurezza del trasporto HTTP in un servizio WCF ospitato da IIS.</span><span class="sxs-lookup"><span data-stu-id="62420-103">This topic describes how to set up an IIS-hosted WCF service to use HTTP transport security.</span></span> <span data-ttu-id="62420-104">La sicurezza del trasporto HTTP richiede che un certificato SSL sia registrato con IIS.</span><span class="sxs-lookup"><span data-stu-id="62420-104">HTTP transport security requires an SSL certificate to be registered with IIS.</span></span> <span data-ttu-id="62420-105">Se non si dispone di un certificato SSL, è possibile usare IIS per generare un certificato di prova.</span><span class="sxs-lookup"><span data-stu-id="62420-105">If you do not have an SSL certificate you can use IIS to generate a test certificate.</span></span> <span data-ttu-id="62420-106">Sarà quindi necessario aggiungere un'associazione SSL al sito Web e configurare le proprietà di autenticazione del sito Web.</span><span class="sxs-lookup"><span data-stu-id="62420-106">Next you must add an SSL binding to the web site and configure the web site’s authentication properties.</span></span> <span data-ttu-id="62420-107">Infine sarà necessario configurare l'uso di HTTPS da parte del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="62420-107">Finally you need to configure the WCF service to use HTTPS.</span></span>  
  
### <a name="creating-a-self-signed-certificate"></a><span data-ttu-id="62420-108">Creazione di un certificato autofirmato</span><span class="sxs-lookup"><span data-stu-id="62420-108">Creating a Self-Signed Certificate</span></span>  
  
1. <span data-ttu-id="62420-109">Aprire Gestione Internet Information Services (inetmgr.exe) e selezionare il nome del computer nella visualizzazione albero a sinistra.</span><span class="sxs-lookup"><span data-stu-id="62420-109">Open Internet Information Services Manager (inetmgr.exe), and select your computer name in the left-hand tree view.</span></span> <span data-ttu-id="62420-110">Sul lato destro della schermata selezionare Certificati server.</span><span class="sxs-lookup"><span data-stu-id="62420-110">On the right-hand side of the screen select Server Certificates</span></span>  
  
     <span data-ttu-id="62420-111">![Schermata iniziale di gestione IIS](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span><span class="sxs-lookup"><span data-stu-id="62420-111">![IIS Manager Home Screen](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span></span>  
  
2. <span data-ttu-id="62420-112">Nella finestra certificati Server fare clic su di **Crea certificato autofirmato...**</span><span class="sxs-lookup"><span data-stu-id="62420-112">In the Server Certificates window click the **Create Self-Signed Certificate….**</span></span> <span data-ttu-id="62420-113">.</span><span class="sxs-lookup"><span data-stu-id="62420-113">Link.</span></span>  
  
     <span data-ttu-id="62420-114">![Creazione di un self&#45;firmati certificati con IIS](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span><span class="sxs-lookup"><span data-stu-id="62420-114">![Creating a self&#45;signed certificate with IIS](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span></span>  
  
3. <span data-ttu-id="62420-115">Immettere un nome descrittivo per il certificato autofirmato e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="62420-115">Enter a friendly name for the self-signed certificate and click **OK**.</span></span>  
  
     <span data-ttu-id="62420-116">![Creare Self&#45;finestra di dialogo certificato firmato](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "mg_MyCert")</span><span class="sxs-lookup"><span data-stu-id="62420-116">![Create Self&#45;Signed Certificate Dialog](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "mg_MyCert")</span></span>  
  
     <span data-ttu-id="62420-117">I dettagli del certificato autofirmato appena creato vengono ora visualizzati nel **certificati Server** finestra.</span><span class="sxs-lookup"><span data-stu-id="62420-117">The newly created self-signed certificate details are now shown in the **Server Certificates** window.</span></span>  
  
     <span data-ttu-id="62420-118">![Finestra certificati del server](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span><span class="sxs-lookup"><span data-stu-id="62420-118">![Server Certificate Window](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span></span>  
  
     <span data-ttu-id="62420-119">Il certificato generato viene installato nell'archivio Autorità di certificazione radice disponibile nell'elenco locale.</span><span class="sxs-lookup"><span data-stu-id="62420-119">The generated certificate is installed in the Trusted Root Certification Authorities store.</span></span>  
  
### <a name="add-ssl-binding"></a><span data-ttu-id="62420-120">Aggiungere l'associazione SSL</span><span class="sxs-lookup"><span data-stu-id="62420-120">Add SSL Binding</span></span>  
  
1. <span data-ttu-id="62420-121">Ancora in Gestione Internet Information Services, espandere la **siti** cartella e quindi la **sito Web predefinito** cartella nella visualizzazione albero sul lato sinistro della schermata.</span><span class="sxs-lookup"><span data-stu-id="62420-121">Still in Internet Information Services Manager, expand the **Sites** folder and then the **Default Web Site** folder in the tree view on the left-hand side of the screen.</span></span>  
  
2. <span data-ttu-id="62420-122">Fare clic su di **associazioni...**</span><span class="sxs-lookup"><span data-stu-id="62420-122">Click the **Bindings….**</span></span> <span data-ttu-id="62420-123">Collegare il **azioni** sezione nella parte superiore destra della finestra.</span><span class="sxs-lookup"><span data-stu-id="62420-123">Link in the **Actions** section in the upper right hand portion of the window.</span></span>  
  
     <span data-ttu-id="62420-124">![Aggiunta di un'associazione SSL](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span><span class="sxs-lookup"><span data-stu-id="62420-124">![Adding an SSL binding](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span></span>  
  
3. <span data-ttu-id="62420-125">Nella finestra binding del sito selezionare la **Add** pulsante.</span><span class="sxs-lookup"><span data-stu-id="62420-125">In the Site Bindings window click the **Add** button.</span></span>  
  
     <span data-ttu-id="62420-126">![Finestra di dialogo binding sito](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span><span class="sxs-lookup"><span data-stu-id="62420-126">![Site Bindings Dialog](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span></span>  
  
4. <span data-ttu-id="62420-127">Nel **Aggiungi Binding sito** finestra di dialogo selezionare https per il tipo e il nome descrittivo del certificato autofirmato appena creato.</span><span class="sxs-lookup"><span data-stu-id="62420-127">In the **Add Site Binding** dialog, select https for the type and the friendly name of the self-signed certificate you just created.</span></span>  
  
     <span data-ttu-id="62420-128">![Esempio di associazione del sito](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "mg_MyCertBinding")</span><span class="sxs-lookup"><span data-stu-id="62420-128">![Site binding example](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "mg_MyCertBinding")</span></span>  
  
### <a name="configure-virtual-directory-for-ssl"></a><span data-ttu-id="62420-129">Configurare la directory virtuale per SSL</span><span class="sxs-lookup"><span data-stu-id="62420-129">Configure Virtual Directory for SSL</span></span>  
  
1. <span data-ttu-id="62420-130">In Gestione Internet Information Services selezionare la directory virtuale contenente il servizio protetto WCF.</span><span class="sxs-lookup"><span data-stu-id="62420-130">Still in Internet Information Services Manager, select the virtual directory that contains your WCF secure service.</span></span>  
  
2. <span data-ttu-id="62420-131">Nel riquadro centrale della finestra, selezionare **impostazioni SSL** nella sezione IIS.</span><span class="sxs-lookup"><span data-stu-id="62420-131">In the center pane of the window, select **SSL Settings** in the IIS section.</span></span>  
  
     <span data-ttu-id="62420-132">![Impostazioni SSL per la directory virtuale](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span><span class="sxs-lookup"><span data-stu-id="62420-132">![SSL Settings for virtual directory](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span></span>  
  
3. <span data-ttu-id="62420-133">Nel riquadro impostazioni SSL selezionare la **Richiedi SSL** casella di controllo e fare clic sul **Apply** clic sul collegamento nel **azioni** sezione sul lato destro della schermata.</span><span class="sxs-lookup"><span data-stu-id="62420-133">In the SSL Settings pane, select the **Require SSL** checkbox and click the **Apply** link in the **Actions** section on the right hand side of the screen.</span></span>  
  
     <span data-ttu-id="62420-134">![Impostazioni SSL della directory virtuale](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span><span class="sxs-lookup"><span data-stu-id="62420-134">![Virtual directory SSL settings](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span></span>  
  
### <a name="configure-wcf-service-for-http-transport-security"></a><span data-ttu-id="62420-135">Configurare il servizio WCF per la sicurezza del trasporto HTTP</span><span class="sxs-lookup"><span data-stu-id="62420-135">Configure WCF Service for HTTP Transport Security</span></span>  
  
1. <span data-ttu-id="62420-136">Nel file web.config del servizio WCF configurare l'uso della sicurezza del trasporto da parte dell'associazione HTTP come illustrato nel codice XML seguente.</span><span class="sxs-lookup"><span data-stu-id="62420-136">In the WCF service’s web.config configure the HTTP binding to use transport security as shown in the following XML.</span></span>  
  
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
  
2. <span data-ttu-id="62420-137">Specificare il servizio e il relativo endpoint come illustrato nel codice XML seguente.</span><span class="sxs-lookup"><span data-stu-id="62420-137">Specify your service and service endpoint as shown in the following XML.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="62420-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="62420-138">Example</span></span>  
 <span data-ttu-id="62420-139">Di seguito è riportato un esempio completo di un file web.config per un servizio WCF in cui è usata la sicurezza del trasporto HTTP</span><span class="sxs-lookup"><span data-stu-id="62420-139">The following is a complete example of a web.config file for a WCF service using HTTP transport security</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="62420-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62420-140">See also</span></span>

- [<span data-ttu-id="62420-141">Hosting in Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="62420-141">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)
- [<span data-ttu-id="62420-142">Istruzioni per l'hosting su Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="62420-142">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
- [<span data-ttu-id="62420-143">Procedure consigliate per l'hosting in Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="62420-143">Internet Information Services Hosting Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
- [<span data-ttu-id="62420-144">Hosting IIS mediante il codice inline</span><span class="sxs-lookup"><span data-stu-id="62420-144">IIS Hosting Using Inline Code</span></span>](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)

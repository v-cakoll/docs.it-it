---
title: 'Procedura: configurare un servizio WCF ospitato da IIS con SSL'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cb6a0b7913434be70efdc5af780980b971b5bc6f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a><span data-ttu-id="4d7aa-102">Procedura: configurare un servizio WCF ospitato da IIS con SSL</span><span class="sxs-lookup"><span data-stu-id="4d7aa-102">How to: Configure an IIS-hosted WCF service with SSL</span></span>
<span data-ttu-id="4d7aa-103">In questo argomento viene descritto come configurare l'uso della sicurezza del trasporto HTTP in un servizio WCF ospitato da IIS.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-103">This topic describes how to set up an IIS-hosted WCF service to use HTTP transport security.</span></span> <span data-ttu-id="4d7aa-104">La sicurezza del trasporto HTTP richiede che un certificato SSL sia registrato con IIS.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-104">HTTP transport security requires an SSL certificate to be registered with IIS.</span></span> <span data-ttu-id="4d7aa-105">Se non si dispone di un certificato SSL, è possibile usare IIS per generare un certificato di prova.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-105">If you do not have an SSL certificate you can use IIS to generate a test certificate.</span></span> <span data-ttu-id="4d7aa-106">Sarà quindi necessario aggiungere un binding SSL al sito Web e configurare le proprietà di autenticazione del sito Web.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-106">Next you must add an SSL binding to the web site and configure the web site’s authentication properties.</span></span> <span data-ttu-id="4d7aa-107">Infine sarà necessario configurare l'uso di HTTPS da parte del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-107">Finally you need to configure the WCF service to use HTTPS.</span></span>  
  
### <a name="creating-a-self-signed-certificate"></a><span data-ttu-id="4d7aa-108">Creazione di un certificato autofirmato</span><span class="sxs-lookup"><span data-stu-id="4d7aa-108">Creating a Self-Signed Certificate</span></span>  
  
1.  <span data-ttu-id="4d7aa-109">Aprire Gestione Internet Information Services (inetmgr.exe) e selezionare il nome del computer nella visualizzazione albero a sinistra.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-109">Open Internet Information Services Manager (inetmgr.exe), and select your computer name in the left-hand tree view.</span></span> <span data-ttu-id="4d7aa-110">Sul lato destro della schermata selezionare Certificati server.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-110">On the right-hand side of the screen select Server Certificates</span></span>  
  
     <span data-ttu-id="4d7aa-111">![Schermata iniziale di gestione IIS](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span><span class="sxs-lookup"><span data-stu-id="4d7aa-111">![IIS Manager Home Screen](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span></span>  
  
2.  <span data-ttu-id="4d7aa-112">Nella finestra certificati Server fare clic su di **Crea certificato autofirmato...**</span><span class="sxs-lookup"><span data-stu-id="4d7aa-112">In the Server Certificates window click the **Create Self-Signed Certificate….**</span></span> <span data-ttu-id="4d7aa-113">.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-113">Link.</span></span>  
  
     <span data-ttu-id="4d7aa-114">![Creazione automatica &#45; firma certificato con IIS](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span><span class="sxs-lookup"><span data-stu-id="4d7aa-114">![Creating a self&#45;signed certificate with IIS](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span></span>  
  
3.  <span data-ttu-id="4d7aa-115">Immettere un nome descrittivo per il certificato autofirmato e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-115">Enter a friendly name for the self-signed certificate and click **OK**.</span></span>  
  
     <span data-ttu-id="4d7aa-116">![Creare Self &#45; Finestra di dialogo certificato firmato](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "mg_MyCert")</span><span class="sxs-lookup"><span data-stu-id="4d7aa-116">![Create Self&#45;Signed Certificate Dialog](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "mg_MyCert")</span></span>  
  
     <span data-ttu-id="4d7aa-117">I dettagli del certificato autofirmato appena creato vengono ora visualizzati di **certificati Server** finestra.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-117">The newly created self-signed certificate details are now shown in the **Server Certificates** window.</span></span>  
  
     <span data-ttu-id="4d7aa-118">![Finestra certificati del server](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span><span class="sxs-lookup"><span data-stu-id="4d7aa-118">![Server Certificate Window](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span></span>  
  
     <span data-ttu-id="4d7aa-119">Il certificato generato viene installato nell'archivio Autorità di certificazione radice disponibile nell'elenco locale.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-119">The generated certificate is installed in the Trusted Root Certification Authorities store.</span></span>  
  
### <a name="add-ssl-binding"></a><span data-ttu-id="4d7aa-120">Aggiungere l'associazione SSL</span><span class="sxs-lookup"><span data-stu-id="4d7aa-120">Add SSL Binding</span></span>  
  
1.  <span data-ttu-id="4d7aa-121">In Gestione Internet Information Services espandere la **siti** cartella e quindi la **sito Web predefinito** cartella nella visualizzazione albero sul lato sinistro della schermata.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-121">Still in Internet Information Services Manager, expand the **Sites** folder and then the **Default Web Site** folder in the tree view on the left-hand side of the screen.</span></span>  
  
2.  <span data-ttu-id="4d7aa-122">Fare clic su di **associazioni...**</span><span class="sxs-lookup"><span data-stu-id="4d7aa-122">Click the **Bindings….**</span></span> <span data-ttu-id="4d7aa-123">Collegare il **azioni** sezione nella parte superiore destra della finestra.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-123">Link in the **Actions** section in the upper right hand portion of the window.</span></span>  
  
     <span data-ttu-id="4d7aa-124">![Aggiunta di un'associazione SSL](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span><span class="sxs-lookup"><span data-stu-id="4d7aa-124">![Adding an SSL binding](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span></span>  
  
3.  <span data-ttu-id="4d7aa-125">Nella finestra binding sito fare clic su di **Aggiungi** pulsante.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-125">In the Site Bindings window click the **Add** button.</span></span>  
  
     <span data-ttu-id="4d7aa-126">![Finestra di dialogo binding sito](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span><span class="sxs-lookup"><span data-stu-id="4d7aa-126">![Site Bindings Dialog](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span></span>  
  
4.  <span data-ttu-id="4d7aa-127">Nel **Aggiungi Binding sito** finestra di dialogo, selezionare https per il tipo e il nome descrittivo del certificato autofirmato appena creato.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-127">In the **Add Site Binding** dialog, select https for the type and the friendly name of the self-signed certificate you just created.</span></span>  
  
     <span data-ttu-id="4d7aa-128">![Esempio di associazione sito](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "mg_MyCertBinding")</span><span class="sxs-lookup"><span data-stu-id="4d7aa-128">![Site binding example](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "mg_MyCertBinding")</span></span>  
  
### <a name="configure-virtual-directory-for-ssl"></a><span data-ttu-id="4d7aa-129">Configurare la directory virtuale per SSL</span><span class="sxs-lookup"><span data-stu-id="4d7aa-129">Configure Virtual Directory for SSL</span></span>  
  
1.  <span data-ttu-id="4d7aa-130">In Gestione Internet Information Services selezionare la directory virtuale contenente il servizio protetto WCF.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-130">Still in Internet Information Services Manager, select the virtual directory that contains your WCF secure service.</span></span>  
  
2.  <span data-ttu-id="4d7aa-131">Nel riquadro centrale della finestra, selezionare **impostazioni SSL** nella sezione di IIS.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-131">In the center pane of the window, select **SSL Settings** in the IIS section.</span></span>  
  
     <span data-ttu-id="4d7aa-132">![Le impostazioni SSL per la directory virtuale](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span><span class="sxs-lookup"><span data-stu-id="4d7aa-132">![SSL Settings for virtual directory](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span></span>  
  
3.  <span data-ttu-id="4d7aa-133">Nel riquadro impostazioni SSL, selezionare il **Richiedi SSL** casella di controllo e fare clic sul **applica** collegare il **azioni** sezione sul lato destro dello schermo.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-133">In the SSL Settings pane, select the **Require SSL** checkbox and click the **Apply** link in the **Actions** section on the right hand side of the screen.</span></span>  
  
     <span data-ttu-id="4d7aa-134">![Impostazioni SSL della directory virtuale](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span><span class="sxs-lookup"><span data-stu-id="4d7aa-134">![Virtual directory SSL settings](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span></span>  
  
### <a name="configure-wcf-service-for-http-transport-security"></a><span data-ttu-id="4d7aa-135">Configurare il servizio WCF per la sicurezza del trasporto HTTP</span><span class="sxs-lookup"><span data-stu-id="4d7aa-135">Configure WCF Service for HTTP Transport Security</span></span>  
  
1.  <span data-ttu-id="4d7aa-136">Nel file web.config del servizio WCF configurare l'uso della sicurezza del trasporto da parte del binding HTTP come illustrato nel codice XML seguente.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-136">In the WCF service’s web.config configure the HTTP binding to use transport security as shown in the following XML.</span></span>  
  
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
  
2.  <span data-ttu-id="4d7aa-137">Specificare il servizio e il relativo endpoint come illustrato nel codice XML seguente.</span><span class="sxs-lookup"><span data-stu-id="4d7aa-137">Specify your service and service endpoint as shown in the following XML.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="4d7aa-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d7aa-138">Example</span></span>  
 <span data-ttu-id="4d7aa-139">Di seguito è riportato un esempio completo di un file web.config per un servizio WCF in cui è usata la sicurezza del trasporto HTTP</span><span class="sxs-lookup"><span data-stu-id="4d7aa-139">The following is a complete example of a web.config file for a WCF service using HTTP transport security</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4d7aa-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d7aa-140">See Also</span></span>  
 [<span data-ttu-id="4d7aa-141">Hosting in Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="4d7aa-141">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [<span data-ttu-id="4d7aa-142">Istruzioni di Hosting Internet Information Service</span><span class="sxs-lookup"><span data-stu-id="4d7aa-142">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)  
 [<span data-ttu-id="4d7aa-143">Hosting di procedure consigliate di Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="4d7aa-143">Internet Information Services Hosting Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [<span data-ttu-id="4d7aa-144">Hosting IIS mediante il codice Inline</span><span class="sxs-lookup"><span data-stu-id="4d7aa-144">IIS Hosting Using Inline Code</span></span>](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)

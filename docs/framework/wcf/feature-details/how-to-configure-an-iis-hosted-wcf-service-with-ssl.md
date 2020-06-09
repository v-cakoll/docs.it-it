---
title: 'Procedura: configurare un servizio WCF ospitato da IIS con SSL'
ms.date: 03/30/2017
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
ms.openlocfilehash: fb3e87021c3dce1172250f33fd302916920af74d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597228"
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a><span data-ttu-id="dbe90-102">Procedura: configurare un servizio WCF ospitato da IIS con SSL</span><span class="sxs-lookup"><span data-stu-id="dbe90-102">How to: Configure an IIS-hosted WCF service with SSL</span></span>
<span data-ttu-id="dbe90-103">In questo argomento viene descritto come configurare l'uso della sicurezza del trasporto HTTP in un servizio WCF ospitato da IIS.</span><span class="sxs-lookup"><span data-stu-id="dbe90-103">This topic describes how to set up an IIS-hosted WCF service to use HTTP transport security.</span></span> <span data-ttu-id="dbe90-104">La sicurezza del trasporto HTTP richiede che un certificato SSL sia registrato con IIS.</span><span class="sxs-lookup"><span data-stu-id="dbe90-104">HTTP transport security requires an SSL certificate to be registered with IIS.</span></span> <span data-ttu-id="dbe90-105">Se non si dispone di un certificato SSL, è possibile usare IIS per generare un certificato di prova.</span><span class="sxs-lookup"><span data-stu-id="dbe90-105">If you do not have an SSL certificate you can use IIS to generate a test certificate.</span></span> <span data-ttu-id="dbe90-106">Sarà quindi necessario aggiungere un'associazione SSL al sito Web e configurare le proprietà di autenticazione del sito Web.</span><span class="sxs-lookup"><span data-stu-id="dbe90-106">Next you must add an SSL binding to the web site and configure the web site’s authentication properties.</span></span> <span data-ttu-id="dbe90-107">Infine sarà necessario configurare l'uso di HTTPS da parte del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="dbe90-107">Finally you need to configure the WCF service to use HTTPS.</span></span>  
  
### <a name="creating-a-self-signed-certificate"></a><span data-ttu-id="dbe90-108">Creazione di un certificato autofirmato</span><span class="sxs-lookup"><span data-stu-id="dbe90-108">Creating a Self-Signed Certificate</span></span>  
  
1. <span data-ttu-id="dbe90-109">Aprire Gestione Internet Information Services (inetmgr.exe) e selezionare il nome del computer nella visualizzazione albero a sinistra.</span><span class="sxs-lookup"><span data-stu-id="dbe90-109">Open Internet Information Services Manager (inetmgr.exe), and select your computer name in the left-hand tree view.</span></span> <span data-ttu-id="dbe90-110">Sul lato destro della schermata selezionare Certificati server.</span><span class="sxs-lookup"><span data-stu-id="dbe90-110">On the right-hand side of the screen select Server Certificates</span></span>  
  
     <span data-ttu-id="dbe90-111">![Schermata iniziale di Gestione IIS](media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span><span class="sxs-lookup"><span data-stu-id="dbe90-111">![IIS Manager Home Screen](media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span></span>  
  
2. <span data-ttu-id="dbe90-112">Nella finestra certificati server fare clic su **Crea certificato autofirmato....**</span><span class="sxs-lookup"><span data-stu-id="dbe90-112">In the Server Certificates window click the **Create Self-Signed Certificate….**</span></span> <span data-ttu-id="dbe90-113">.</span><span class="sxs-lookup"><span data-stu-id="dbe90-113">Link.</span></span>  
  
     <span data-ttu-id="dbe90-114">![Creazione di un certificato auto&#45;firmato con IIS](media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span><span class="sxs-lookup"><span data-stu-id="dbe90-114">![Creating a self&#45;signed certificate with IIS](media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span></span>  
  
3. <span data-ttu-id="dbe90-115">Immettere un nome descrittivo per il certificato autofirmato e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbe90-115">Enter a friendly name for the self-signed certificate and click **OK**.</span></span>  
  
     <span data-ttu-id="dbe90-116">![Finestra di dialogo Crea certificato firmato autonomamente&#45;](media/mg-mycert.jpg "mg_MyCert")</span><span class="sxs-lookup"><span data-stu-id="dbe90-116">![Create Self&#45;Signed Certificate Dialog](media/mg-mycert.jpg "mg_MyCert")</span></span>  
  
     <span data-ttu-id="dbe90-117">I dettagli del certificato autofirmato appena creato vengono ora visualizzati nella finestra **certificati server** .</span><span class="sxs-lookup"><span data-stu-id="dbe90-117">The newly created self-signed certificate details are now shown in the **Server Certificates** window.</span></span>  
  
     <span data-ttu-id="dbe90-118">![Finestra Certificati del server](media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span><span class="sxs-lookup"><span data-stu-id="dbe90-118">![Server Certificate Window](media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span></span>  
  
     <span data-ttu-id="dbe90-119">Il certificato generato viene installato nell'archivio Autorità di certificazione radice disponibile nell'elenco locale.</span><span class="sxs-lookup"><span data-stu-id="dbe90-119">The generated certificate is installed in the Trusted Root Certification Authorities store.</span></span>  
  
### <a name="add-ssl-binding"></a><span data-ttu-id="dbe90-120">Aggiungere l'associazione SSL</span><span class="sxs-lookup"><span data-stu-id="dbe90-120">Add SSL Binding</span></span>  
  
1. <span data-ttu-id="dbe90-121">Sempre in Gestione Internet Information Services espandere la cartella **siti** , quindi la cartella **sito Web predefinito** nella visualizzazione albero sul lato sinistro della schermata.</span><span class="sxs-lookup"><span data-stu-id="dbe90-121">Still in Internet Information Services Manager, expand the **Sites** folder and then the **Default Web Site** folder in the tree view on the left-hand side of the screen.</span></span>  
  
2. <span data-ttu-id="dbe90-122">Fare clic sui **Binding....**</span><span class="sxs-lookup"><span data-stu-id="dbe90-122">Click the **Bindings….**</span></span> <span data-ttu-id="dbe90-123">Collegamento nella sezione **azioni** nella parte superiore destra della finestra.</span><span class="sxs-lookup"><span data-stu-id="dbe90-123">Link in the **Actions** section in the upper right hand portion of the window.</span></span>  
  
     <span data-ttu-id="dbe90-124">![Aggiunta di un'associazione SSL](media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span><span class="sxs-lookup"><span data-stu-id="dbe90-124">![Adding an SSL binding](media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span></span>  
  
3. <span data-ttu-id="dbe90-125">Nella finestra Binding sito fare clic sul pulsante **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="dbe90-125">In the Site Bindings window click the **Add** button.</span></span>  
  
     <span data-ttu-id="dbe90-126">![Finestra di dialogo Binding del sito](media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span><span class="sxs-lookup"><span data-stu-id="dbe90-126">![Site Bindings Dialog](media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span></span>  
  
4. <span data-ttu-id="dbe90-127">Nella finestra di dialogo **Aggiungi binding sito** selezionare HTTPS per il tipo e il nome descrittivo del certificato autofirmato appena creato.</span><span class="sxs-lookup"><span data-stu-id="dbe90-127">In the **Add Site Binding** dialog, select https for the type and the friendly name of the self-signed certificate you just created.</span></span>  
  
     <span data-ttu-id="dbe90-128">![Esempio di associazione sito](media/mg-mycertbinding.jpg "mg_MyCertBinding")</span><span class="sxs-lookup"><span data-stu-id="dbe90-128">![Site binding example](media/mg-mycertbinding.jpg "mg_MyCertBinding")</span></span>  
  
### <a name="configure-virtual-directory-for-ssl"></a><span data-ttu-id="dbe90-129">Configurare la directory virtuale per SSL</span><span class="sxs-lookup"><span data-stu-id="dbe90-129">Configure Virtual Directory for SSL</span></span>  
  
1. <span data-ttu-id="dbe90-130">In Gestione Internet Information Services selezionare la directory virtuale contenente il servizio protetto WCF.</span><span class="sxs-lookup"><span data-stu-id="dbe90-130">Still in Internet Information Services Manager, select the virtual directory that contains your WCF secure service.</span></span>  
  
2. <span data-ttu-id="dbe90-131">Nel riquadro centrale della finestra selezionare **Impostazioni SSL** nella sezione IIS.</span><span class="sxs-lookup"><span data-stu-id="dbe90-131">In the center pane of the window, select **SSL Settings** in the IIS section.</span></span>  
  
     <span data-ttu-id="dbe90-132">![Impostazioni SSL per la directory virtuale](media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span><span class="sxs-lookup"><span data-stu-id="dbe90-132">![SSL Settings for virtual directory](media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span></span>  
  
3. <span data-ttu-id="dbe90-133">Nel riquadro Impostazioni SSL selezionare la casella di controllo **Richiedi SSL** e fare clic sul collegamento **applica** nella sezione **azioni** sul lato destro dello schermo.</span><span class="sxs-lookup"><span data-stu-id="dbe90-133">In the SSL Settings pane, select the **Require SSL** checkbox and click the **Apply** link in the **Actions** section on the right hand side of the screen.</span></span>  
  
     <span data-ttu-id="dbe90-134">![Impostazioni SSL della directory virtuale](media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span><span class="sxs-lookup"><span data-stu-id="dbe90-134">![Virtual directory SSL settings](media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span></span>  
  
### <a name="configure-wcf-service-for-http-transport-security"></a><span data-ttu-id="dbe90-135">Configurare il servizio WCF per la sicurezza del trasporto HTTP</span><span class="sxs-lookup"><span data-stu-id="dbe90-135">Configure WCF Service for HTTP Transport Security</span></span>  
  
1. <span data-ttu-id="dbe90-136">Nel file web.config del servizio WCF configurare l'uso della sicurezza del trasporto da parte dell'associazione HTTP come illustrato nel codice XML seguente.</span><span class="sxs-lookup"><span data-stu-id="dbe90-136">In the WCF service’s web.config configure the HTTP binding to use transport security as shown in the following XML.</span></span>  
  
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
  
2. <span data-ttu-id="dbe90-137">Specificare il servizio e il relativo endpoint come illustrato nel codice XML seguente.</span><span class="sxs-lookup"><span data-stu-id="dbe90-137">Specify your service and service endpoint as shown in the following XML.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="dbe90-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="dbe90-138">Example</span></span>  
 <span data-ttu-id="dbe90-139">Di seguito è riportato un esempio completo di un file web.config per un servizio WCF in cui è usata la sicurezza del trasporto HTTP</span><span class="sxs-lookup"><span data-stu-id="dbe90-139">The following is a complete example of a web.config file for a WCF service using HTTP transport security</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dbe90-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbe90-140">See also</span></span>

- [<span data-ttu-id="dbe90-141">Host in Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="dbe90-141">Hosting in Internet Information Services</span></span>](hosting-in-internet-information-services.md)
- [<span data-ttu-id="dbe90-142">Istruzioni per l'hosting su IIS (Internet Information Services)</span><span class="sxs-lookup"><span data-stu-id="dbe90-142">Internet Information Service Hosting Instructions</span></span>](../samples/internet-information-service-hosting-instructions.md)
- [<span data-ttu-id="dbe90-143">Procedure consigliate per l'hosting in Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="dbe90-143">Internet Information Services Hosting Best Practices</span></span>](internet-information-services-hosting-best-practices.md)
- [<span data-ttu-id="dbe90-144">Hosting IIS mediante il codice inline</span><span class="sxs-lookup"><span data-stu-id="dbe90-144">IIS Hosting Using Inline Code</span></span>](../samples/iis-hosting-using-inline-code.md)

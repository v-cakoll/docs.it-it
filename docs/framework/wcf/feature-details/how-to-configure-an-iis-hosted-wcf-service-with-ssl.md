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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b16ca5b4cfe615eedd9e532b12f61394806829bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a>Procedura: configurare un servizio WCF ospitato da IIS con SSL
In questo argomento viene descritto come configurare l'uso della sicurezza del trasporto HTTP in un servizio WCF ospitato da IIS. La sicurezza del trasporto HTTP richiede che un certificato SSL sia registrato con IIS. Se non si dispone di un certificato SSL, è possibile usare IIS per generare un certificato di prova. Sarà quindi necessario aggiungere un binding SSL al sito Web e configurare le proprietà di autenticazione del sito Web. Infine sarà necessario configurare l'uso di HTTPS da parte del servizio WCF.  
  
### <a name="creating-a-self-signed-certificate"></a>Creazione di un certificato autofirmato  
  
1.  Aprire Gestione Internet Information Services (inetmgr.exe) e selezionare il nome del computer nella visualizzazione albero a sinistra. Sul lato destro della schermata selezionare Certificati server.  
  
     ![Schermata iniziale di gestione IIS](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg_INetMgrHome")  
  
2.  Nella finestra certificati Server fare clic su di **Crea certificato autofirmato...** .  
  
     ![Creazione automatica &#45; firma certificato con IIS](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")  
  
3.  Immettere un nome descrittivo per il certificato autofirmato e fare clic su **OK**.  
  
     ![Creare Self &#45; Finestra di dialogo certificato firmato](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "mg_MyCert")  
  
     I dettagli del certificato autofirmato appena creato vengono ora visualizzati di **certificati Server** finestra.  
  
     ![Finestra certificati del server](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")  
  
     Il certificato generato viene installato nell'archivio Autorità di certificazione radice disponibile nell'elenco locale.  
  
### <a name="add-ssl-binding"></a>Aggiungere l'associazione SSL  
  
1.  In Gestione Internet Information Services espandere la **siti** cartella e quindi la **sito Web predefinito** cartella nella visualizzazione albero sul lato sinistro della schermata.  
  
2.  Fare clic su di **associazioni...** Collegare il **azioni** sezione nella parte superiore destra della finestra.  
  
     ![Aggiunta di un'associazione SSL](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "mg_AddSSLBinding")  
  
3.  Nella finestra binding sito fare clic su di **Aggiungi** pulsante.  
  
     ![Finestra di dialogo binding sito](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")  
  
4.  Nel **Aggiungi Binding sito** finestra di dialogo, selezionare https per il tipo e il nome descrittivo del certificato autofirmato appena creato.  
  
     ![Esempio di associazione sito](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "mg_MyCertBinding")  
  
### <a name="configure-virtual-directory-for-ssl"></a>Configurare la directory virtuale per SSL  
  
1.  In Gestione Internet Information Services selezionare la directory virtuale contenente il servizio protetto WCF.  
  
2.  Nel riquadro centrale della finestra, selezionare **impostazioni SSL** nella sezione di IIS.  
  
     ![Le impostazioni SSL per la directory virtuale](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")  
  
3.  Nel riquadro impostazioni SSL, selezionare il **Richiedi SSL** casella di controllo e fare clic sul **applica** collegare il **azioni** sezione sul lato destro dello schermo.  
  
     ![Impostazioni SSL della directory virtuale](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")  
  
### <a name="configure-wcf-service-for-http-transport-security"></a>Configurare il servizio WCF per la sicurezza del trasporto HTTP  
  
1.  Nel file web.config del servizio WCF configurare l'uso della sicurezza del trasporto da parte del binding HTTP come illustrato nel codice XML seguente.  
  
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
  
2.  Specificare il servizio e il relativo endpoint come illustrato nel codice XML seguente.  
  
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
  
## <a name="example"></a>Esempio  
 Di seguito è riportato un esempio completo di un file web.config per un servizio WCF in cui è usata la sicurezza del trasporto HTTP  
  
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
  
## <a name="see-also"></a>Vedere anche  
 [Hosting in Internet Information Services](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [Istruzioni per l'hosting su Internet Information Services](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)  
 [Procedure consigliate per l'hosting in Internet Information Services (IIS)](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Hosting IIS mediante il codice inline](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)

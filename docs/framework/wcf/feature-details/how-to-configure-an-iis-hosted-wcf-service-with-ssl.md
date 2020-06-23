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
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a>Procedura: configurare un servizio WCF ospitato da IIS con SSL
In questo argomento viene descritto come configurare l'uso della sicurezza del trasporto HTTP in un servizio WCF ospitato da IIS. La sicurezza del trasporto HTTP richiede che un certificato SSL sia registrato con IIS. Se non si dispone di un certificato SSL, è possibile usare IIS per generare un certificato di prova. Sarà quindi necessario aggiungere un'associazione SSL al sito Web e configurare le proprietà di autenticazione del sito Web. Infine sarà necessario configurare l'uso di HTTPS da parte del servizio WCF.  
  
### <a name="creating-a-self-signed-certificate"></a>Creazione di un certificato autofirmato  
  
1. Aprire Gestione Internet Information Services (inetmgr.exe) e selezionare il nome del computer nella visualizzazione albero a sinistra. Sul lato destro della schermata selezionare Certificati server.  
  
     ![Schermata iniziale di Gestione IIS](media/mg-inetmgrhome.jpg "mg_INetMgrHome")  
  
2. Nella finestra certificati server fare clic su **Crea certificato autofirmato....** .  
  
     ![Creazione di un certificato auto&#45;firmato con IIS](media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")  
  
3. Immettere un nome descrittivo per il certificato autofirmato e fare clic su **OK**.  
  
     ![Finestra di dialogo Crea certificato firmato autonomamente&#45;](media/mg-mycert.jpg "mg_MyCert")  
  
     I dettagli del certificato autofirmato appena creato vengono ora visualizzati nella finestra **certificati server** .  
  
     ![Finestra Certificati del server](media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")  
  
     Il certificato generato viene installato nell'archivio Autorità di certificazione radice disponibile nell'elenco locale.  
  
### <a name="add-ssl-binding"></a>Aggiungere l'associazione SSL  
  
1. Sempre in Gestione Internet Information Services espandere la cartella **siti** , quindi la cartella **sito Web predefinito** nella visualizzazione albero sul lato sinistro della schermata.  
  
2. Fare clic sui **Binding....** Collegamento nella sezione **azioni** nella parte superiore destra della finestra.  
  
     ![Aggiunta di un'associazione SSL](media/mg-addsslbinding.jpg "mg_AddSSLBinding")  
  
3. Nella finestra Binding sito fare clic sul pulsante **Aggiungi** .  
  
     ![Finestra di dialogo Binding del sito](media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")  
  
4. Nella finestra di dialogo **Aggiungi binding sito** selezionare HTTPS per il tipo e il nome descrittivo del certificato autofirmato appena creato.  
  
     ![Esempio di associazione sito](media/mg-mycertbinding.jpg "mg_MyCertBinding")  
  
### <a name="configure-virtual-directory-for-ssl"></a>Configurare la directory virtuale per SSL  
  
1. In Gestione Internet Information Services selezionare la directory virtuale contenente il servizio protetto WCF.  
  
2. Nel riquadro centrale della finestra selezionare **Impostazioni SSL** nella sezione IIS.  
  
     ![Impostazioni SSL per la directory virtuale](media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")  
  
3. Nel riquadro Impostazioni SSL selezionare la casella di controllo **Richiedi SSL** e fare clic sul collegamento **applica** nella sezione **azioni** sul lato destro dello schermo.  
  
     ![Impostazioni SSL della directory virtuale](media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")  
  
### <a name="configure-wcf-service-for-http-transport-security"></a>Configurare il servizio WCF per la sicurezza del trasporto HTTP  
  
1. Nel file web.config del servizio WCF configurare l'uso della sicurezza del trasporto da parte dell'associazione HTTP come illustrato nel codice XML seguente.  
  
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
  
2. Specificare il servizio e il relativo endpoint come illustrato nel codice XML seguente.  
  
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

- [Host in Internet Information Services](hosting-in-internet-information-services.md)
- [Istruzioni per l'hosting su IIS (Internet Information Services)](../samples/internet-information-service-hosting-instructions.md)
- [Procedure consigliate per l'hosting in Internet Information Services (IIS)](internet-information-services-hosting-best-practices.md)
- [Hosting IIS mediante il codice inline](../samples/iis-hosting-using-inline-code.md)

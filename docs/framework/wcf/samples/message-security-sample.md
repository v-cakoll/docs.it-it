---
title: Esempio sulla sicurezza dei messaggi
ms.date: 03/30/2017
ms.assetid: 82444166-6288-493a-85d4-85f43f134d19
ms.openlocfilehash: 43e1a9104bdd44509d86bd198559c5e7477a9964
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183522"
---
# <a name="message-security-sample"></a>Esempio sulla sicurezza dei messaggi
In questo esempio viene illustrato come implementare un'applicazione che utilizza `basicHttpBinding` e la sicurezza del messaggio. Questo esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 La modalità di sicurezza di `basicHttpBinding` può essere impostata sui valori seguenti: `Message`, `Transport`, `TransportWithMessageCredential`, `TransportCredentialOnly` e `None`. Nell'esempio seguente il file App.config, la definizione dell'endpoint specifica l'`basicHttpBinding` e fa riferimento a una configurazione di associazione denominata `Binding1`, come mostra la configurazione di esempio seguente:  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- This endpoint is exposed at the base address provided by -->  
     <!-- host: http://localhost:8000/ServiceModelSamples/service.-->  
     <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  ...  
</system.serviceModel>  
```  
  
 La configurazione di `mode` associazione imposta `Message` l'attributo [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) della sicurezza `Certificate`>e imposta l'attributo `clientCredentialType` del>del [ \<messaggio,](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md) come illustrato nella configurazione di esempio seguente:  
  
```xml  
<bindings>  
  <basicHttpBinding>  
    <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
    <binding name="Binding1" >  
      <security mode = "Message">  
        <message clientCredentialType="Certificate"/>  
      </security>  
    </binding>  
  </basicHttpBinding>  
</bindings>  
```  
  
 Il certificato utilizzato dal servizio per l'autenticazione con il client è impostato nella sezione comportamenti del file di configurazione sotto l'elemento `serviceCredentials`. Anche la modalità di convalida applicata al certificato utilizzato dal servizio per l'autenticazione con il client è impostata nella sezione comportamenti del file di configurazione sotto l'elemento `clientCertificate`.  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
      <!--The serviceCredentials behavior allows one to define a -->  
      <!--service certificate. A service certificate is used by a -->  
      <!--client to authenticate the service and provide message -->  
      <!-- protection. This configuration references the "localhost"-->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate findValue="localhost"  
               storeLocation="LocalMachine"
               storeName="My" x509FindType="FindBySubjectName" />  
        <clientCertificate>  
          <!-- Setting the certificateValidationMode to -->  
          <!-- PeerOrChainTrust means that if the certificate -->  
          <!--is in the user's Trusted People store, then it is -->  
          <!-- trusted without performing a validation of the -->  
          <!-- certificate's issuer chain. This setting is used -->  
          <!-- here for convenience so that the sample can be run -->  
          <!-- without having to have certificates issued by a -->  
          <!-- certification authority (CA). -->  
          <!-- This setting is less secure than the default, -->  
          <!-- ChainTrust. The security implications of this -->  
          <!-- setting should be carefully considered before using -->  
          <!-- PeerOrChainTrust in production code. -->  
          <authentication
                       certificateValidationMode="PeerOrChainTrust" />  
        </clientCertificate>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Gli stessi dettagli sull'associazione e la sicurezza sono specificati nel file di configurazione del client.  
  
 L'identità del chiamante viene visualizzata nella finestra della console del servizio utilizzando il codice seguente:  

```csharp
Console.WriteLine("Called by {0}", ServiceSecurityContext.Current.PrimaryIdentity.Name);  
```

 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.  
  
```console
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-and-build-the-sample"></a>Per impostare e compilare l'esempio  
  
1. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
### <a name="to-run-the-sample-on-the-same-machine"></a>Per eseguire l'esempio sullo stesso computer  
  
1. Eseguire Setup.bat dalla cartella di installazione dell'esempio. In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.  
  
    > [!NOTE]
    > Il file batch Setup.bat è progettato per essere eseguito da un prompt dei comandi di SDK di Windows. e richiede che la variabile di ambiente MSSDK punti alla directory in cui è installato SDK. Questa variabile di ambiente viene impostata automaticamente all'interno di un prompt dei comandi di SDK di Windows.  
  
2. Eseguire l'applicazione di servizio da \service\bin.  
  
3. Eseguire l'applicazione client da \client\bin. L'attività del client viene visualizzata nella finestra dell'applicazione console.  
  
4. Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
5. Rimuovere i certificati eseguendo Cleanup.bat una volta completato l'esempio. Negli altri esempi relativi alla sicurezza vengono usati gli stessi certificati.  
  
### <a name="to-run-the-sample-across-machines"></a>Per eseguire l'esempio tra più computer  
  
1. Creare una directory sul computer del servizio per i file binari del servizio.  
  
2. Copiare i file di programma del servizio nella directory del server. Copiare anche i file Setup.bat, Cleanup.bat e ImportClientCert.bat nel server.  
  
3. Creare una directory sul client del servizio per i file binari del client.  
  
4. Copiare i file di programma del client nella directory del client sul computer del client e i file Setup.bat, Cleanup.bat e ImportServiceCert.bat nel client.  
  
5. Eseguire `setup.bat service` sul server. In `setup.bat` esecuzione `service` con l'argomento crea un certificato del servizio con il nome di dominio completo del computer e lo esporta in un file denominato Service.cer.  
  
6. Modificare Service.exe.config per riflettere il nuovo `findValue` nome del certificato (nell'attributo nell'elemento [ \<serviceCertificate>)](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) che corrisponde al nome di dominio completo del computer. Modificare anche il valore dell'indirizzo di base e specificare un nome di computer completo anziché localhost`.`  
  
7. Copiare il file Service.cer dalla directory del servizio alla directory del client sul computer client.  
  
8. Eseguire `setup.bat client` sul client. Quando si esegue `setup.bat` con l'argomento `client` viene creato un certificato client denominato client.com che viene esportato in un file denominato Client.cer.  
  
9. Nel file Client.exe.config nel computer client, modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio. Tale operazione viene eseguita sostituendo localhost con il nome di dominio completo del server. Modificare inoltre `findValue` l'attributo dell'>[ \<defaultCertificate](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md) con il nome del nuovo certificato del servizio, ovvero il nome di dominio completo del server.  
  
10. Copiare il file Client.cer dalla directory del client nella directory del servizio sul server.  
  
11. Nel client, eseguire ImportServiceCert.bat. In questo modo viene importato il certificato del servizio dal file Service.cer nell'archivio CurrentUser - TrustedPeople.  
  
12. Eseguire sul server ImportClientCert.bat. In questo modo il certificato client viene importato dal file Client.cer nell'archivio LocalMachine - TrustedPeople.  
  
13. Sul computer del servizio, eseguire Service.exe da un prompt dei comandi.  
  
14. Sul computer client, avviare Client.exe da una finestra del prompt dei comandi.  
  
    1. Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-clean-up-after-the-sample"></a>Per eseguire la pulizia dopo l'esempio  
  
- Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.  
  
    > [!NOTE]
    > Questo script non rimuove i certificati del servizio su un client quando si esegue questo esempio tra più computer. Se sono stati eseguiti esempi di Windows Communication Foundation (WCF) che usano i certificati tra computer, assicurarsi di cancellare i certificati del servizio installati nell'archivio CurrentUser - TrustedPeople. Per eseguire questa operazione, usare il seguente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Ad esempio: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\MessageSecurity`  

---
title: Servizio facciata attendibile
ms.date: 03/30/2017
ms.assetid: c34d1a8f-e45e-440b-a201-d143abdbac38
ms.openlocfilehash: e7aa5e96fb8104c8140a8cebc6be45d2000821aa
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591319"
---
# <a name="trusted-facade-service"></a>Servizio facciata attendibile
In questo scenario di esempio viene illustrato come eseguire il flusso delle informazioni di identità del chiamante da un servizio a un altro utilizzando l'infrastruttura di sicurezza Windows Communication Foundation (WCF).  
  
 Si tratta di un modello di progettazione comune per esporre la funzionalità fornita da un servizio alla rete pubblica usando un servizio di facciata. Il servizio di facciata risiede in genere nella rete perimetrale e comunica con un servizio back-end che implementa la regola business e ha accesso ai dati interni. Il canale di comunicazione tra il servizio di facciata e il servizio back-end passa attraverso un firewall e in genere è limitato a un solo obiettivo.  
  
 L'esempio è costituito dai componenti seguenti:  
  
- Client calcolatrice  
  
- Servizio di facciata calcolatrice  
  
- Servizio back-end calcolatrice  
  
 Il servizio di facciata ha la responsabilità di convalidare la richiesta e autenticare il chiamante. Una volta completate correttamente l'autenticazione e la convalida, inoltra la richiesta al servizio back-end usando il canale di comunicazione controllato dalla rete perimetrale alla rete interna. I servizio di facciata include come parte della richiesta inoltrata informazioni sull'identità del chiamante, in modo che il servizio back-end possa usare queste informazioni nell'elaborazione. L'identità del chiamante viene trasmessa usando un token di sicurezza `Username` all'interno dell'intestazione di `Security` del messaggio. Nell'esempio viene utilizzata l'infrastruttura di sicurezza WCF per trasmettere ed estrarre queste informazioni dall' `Security` intestazione.  
  
> [!IMPORTANT]
> Il servizio back-end considera attendibile il servizio di facciata per autenticare il chiamante. Di conseguenza il servizio back-end non autentica nuovamente il chiamante, ma usa le informazioni di identità fornite dal servizio di facciata nella richiesta inoltrata. A causa di questa relazione di trust, il servizio back-end deve autenticare il servizio di facciata in modo da assicurare che il messaggio inoltrato provenga da una fonte attendibile, in questo caso, dal servizio di facciata.  
  
## <a name="implementation"></a>Implementazione  
 In questo esempio vengono riportati due percorsi di comunicazione. Il primo è tra il client e il servizio di facciata, il secondo è tra il servizio di facciata e il servizio back-end.  
  
### <a name="communication-path-between-client-and-faade-service"></a>Percorso di comunicazione tra il client e il servizio di facciata  
 Il percorso di comunicazione dal client al servizio di facciata usa `wsHttpBinding` con un tipo di credenziale `UserName` . Questo significa che il client usa il nome utente e la password per autenticare al servizio di facciata e il servizio di facciata usa il certificato X.509 per autenticare il client. L'aspetto della configurazione dell'associazione è analogo al seguente:  
  
```xml  
<bindings>  
  <wsHttpBinding>  
    <binding name="Binding1">  
      <security mode="Message">  
        <message clientCredentialType="UserName"/>  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
```  
  
 Il servizio di facciata autentica il chiamante usando l'implementazione `UserNamePasswordValidator` personalizzata. A scopo dimostrativo, l'autenticazione assicura solo che il nome utente del chiamante corrisponda alla password presentata. Nella situazione del mondo reale l'utente viene probabilmente autenticato usando Active Directory o un provider di appartenenze ASP.NET personalizzato. L'implementazione del validator si trova nel file `FacadeService.cs` .  
  
```csharp  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // check that username matches password  
        if (null == userName || userName != password)  
        {  
            Console.WriteLine("Invalid username or password");  
            throw new SecurityTokenValidationException(  
                       "Invalid username or password");  
        }  
    }  
}  
```  
  
 Il validator personalizzato viene configurato per essere usato nel comportamento `serviceCredentials` nel file di configurazione del servizio di facciata. Questo comportamento viene inoltre usato per configurare il certificato X.509 del servizio.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="FacadeServiceBehavior">  
      <!--The serviceCredentials behavior allows you to define -->  
      <!--a service certificate. -->  
      <!--A service certificate is used by the service to  -->  
      <!--authenticate itself to its clients and to provide  -->  
      <!--message protection. -->  
      <!--This configuration references the "localhost"  -->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate
               findValue="localhost"
               storeLocation="LocalMachine"
               storeName="My"
               x509FindType="FindBySubjectName" />  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
            customUserNamePasswordValidatorType=  
           "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,  
            FacadeService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
### <a name="communication-path-between-faade-service-and-backend-service"></a>Percorso di comunicazione tra il servizio di facciata e il servizio back-end  
 Il percorso di comunicazione dal servizio di facciata al servizio back-end usa un `customBinding` costituito da molti elementi di associazione. Questa associazione consente di raggiungere due obiettivi. Autentica il servizio di facciata e il servizio back-end per assicurare che la comunicazione sia protetta e che provenga da una fonte attendibile. Trasmette inoltre l'identità del chiamante iniziale all'interno del token di sicurezza `Username` . In questo caso, solo il nome utente del chiamante iniziale viene trasmesso al servizio back-end, la password non viene inclusa nel messaggio. Questo è dovuto al fatto che il servizio back-end considera attendibile il servizio di facciata per autenticare il chiamante prima di inoltrargli la richiesta. Poiché il servizio di facciata si autentica con il servizio back-end, il servizio back-end può considerare le informazioni contenute nella richiesta inoltrata attendibili.  
  
 Di seguito è riportata la configurazione di associazione per questo percorso di comunicazione.  
  
```xml  
<bindings>  
  <customBinding>  
    <binding name="ClientBinding">  
      <security authenticationMode="UserNameOverTransport"/>  
      <windowsStreamSecurity/>  
      <tcpTransport/>  
    </binding>  
  </customBinding>  
</bindings>  
```  
  
 L' [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento di associazione si occupa della trasmissione e dell'estrazione del nome utente del chiamante iniziale. E si occupano [\<windowsStreamSecurity>](../../configure-apps/file-schema/wcf/windowsstreamsecurity.md) [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) dell'autenticazione dei servizi di facciata e back-end e della protezione dei messaggi.  
  
 Per inviare la richiesta, l'implementazione del servizio di facciata deve fornire il nome utente del chiamante iniziale, in modo che l'infrastruttura di sicurezza di WCF possa inserire questo oggetto nel messaggio trasmesso. Il nome utente del chiamante iniziale viene fornito nell'implementazione del servizio di facciata impostandolo nella proprietà `ClientCredentials` sull'istanza del proxy client che il servizio di facciata usa per comunicare con il servizio back-end.  
  
 Nel codice seguente viene illustrata l'implementazione del metodo `GetCallerIdentity` nel servizio di facciata. Gli altri metodi usano lo stesso modello.  
  
```csharp  
public string GetCallerIdentity()  
{  
    CalculatorClient client = new CalculatorClient();  
    client.ClientCredentials.UserName.UserName = ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    string result = client.GetCallerIdentity();  
    client.Close();  
    return result;  
}  
```  
  
 Come illustrato nel codice precedente, la password non viene impostata nella proprietà `ClientCredentials` . Viene impostato solo il nome utente. L'infrastruttura di sicurezza di WCF crea un token di sicurezza del nome utente senza una password in questo caso, che è esattamente ciò che è necessario in questo scenario.  
  
 Nel servizio back-end, le informazioni contenute nel token di sicurezza del nome utente devono essere autenticate. Per impostazione predefinita, la sicurezza WCF tenta di eseguire il mapping dell'utente a un account di Windows usando la password fornita. In questo caso non è stata fornita una password e non è necessario che il servizio back-end autentichi il nome utente, visto che l'autenticazione è già stata eseguita dal servizio di facciata. Per implementare questa funzionalità in WCF, `UserNamePasswordValidator` viene fornito un personalizzato che impone solo che venga specificato un nome utente nel token e non esegua alcuna autenticazione aggiuntiva.  
  
```csharp  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // Ignore the password because it is empty,
        // we trust the facade service to authenticate the client.  
        // Accept the username information here so that the
        // application gets access to it.  
        if (null == userName)  
        {  
            Console.WriteLine("Invalid username");  
            throw new
             SecurityTokenValidationException("Invalid username");  
        }  
    }  
}  
```  
  
 Il validator personalizzato viene configurato per essere usato nel comportamento `serviceCredentials` nel file di configurazione del servizio di facciata.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="BackendServiceBehavior">  
      <serviceCredentials>  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
           customUserNamePasswordValidatorType=  
          "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,
           BackendService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Per estrarre le informazioni relative al nome utente e all'account del servizio di facciata attendibile, l'implementazione del servizio back-end usa la classe `ServiceSecurityContext` . Nel codice seguente viene illustrato come implementare il metodo `GetCallerIdentity` .  
  
```csharp  
public string GetCallerIdentity()  
{  
    // Facade service is authenticated using Windows authentication.  
    //Its identity is accessible.  
    // On ServiceSecurityContext.Current.WindowsIdentity.  
    string facadeServiceIdentityName =
          ServiceSecurityContext.Current.WindowsIdentity.Name;  
  
    // The client name is transmitted using Username authentication on
    //the message level without the password  
    // using a supporting encrypted UserNameToken.  
    // Claims extracted from this supporting token are available in
    // ServiceSecurityContext.Current.AuthorizationContext.ClaimSets
    // collection.  
    string clientName = null;  
    foreach (ClaimSet claimSet in
        ServiceSecurityContext.Current.AuthorizationContext.ClaimSets)  
    {  
        foreach (Claim claim in claimSet)  
        {  
            if (claim.ClaimType == ClaimTypes.Name &&
                                   claim.Right == Rights.Identity)  
            {  
                clientName = (string)claim.Resource;  
                break;  
            }  
        }  
    }  
    if (clientName == null)  
    {  
        // In case there was no UserNameToken attached to the request.  
        // In the real world implementation the service should reject
        // this request.  
        return "Anonymous caller via " + facadeServiceIdentityName;  
    }  
  
    return clientName + " via " + facadeServiceIdentityName;  
}  
```  
  
 Le informazioni relative all'account del servizio di facciata vengono estratte usando la proprietà `ServiceSecurityContext.Current.WindowsIdentity` . Per accedere alle informazioni relative al chiamante iniziale, il servizio back-end usa la proprietà `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` . Cerca un'attestazione di `Identity` di tipo `Name`. Questa attestazione viene generata automaticamente dall'infrastruttura di sicurezza WCF dalle informazioni contenute nel `Username` token di sicurezza.  
  
## <a name="running-the-sample"></a>Esecuzione dell'esempio  
 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client. È possibile premere INVIO nelle finestre della console del servizio di facciata e del servizio back-end per arrestare i servizi.  
  
```console  
Username authentication required.  
Provide a valid machine or domain ac  
   Enter username:  
user  
   Enter password:  
****  
user via MyMachine\testaccount  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 Il file batch Setup.bat incluso nell'esempio relativo allo scenario della Facciata attendibile consente di configurare il server con un certificato attinente per eseguire il servizio di facciata che richiede sicurezza server basata su certificato per autenticarsi sul client. Per altre informazioni, vedere la procedura di configurazione alla fine di questo argomento.  
  
 Di seguito viene presentata una breve panoramica delle diverse sezioni dei file batch.  
  
- Creazione del certificato server.  
  
     Le righe seguenti del file batch Setup.bat creano il certificato server da usare.  
  
    ```console  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     La variabile `%SERVER_NAME%` specifica il nome del server. Il valore predefinito è localhost. Il certificato viene archiviato nell'archivio LocalMachine.  
  
- Installazione del servizio di facciata nell'archivio certificati attendibili del client.  
  
     La riga seguente copia il servizio di facciata nell'archivio Persone attendibili del client. Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client. Se è già disponibile un certificato impostato come radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il popolamento dell'archivio certificati client con il certificato server non è necessario.  
  
    ```console  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a>Per eseguire l'esempio sullo stesso computer  
  
1. Assicurarsi che il percorso includa la cartella in cui è situato Makecert.exe.  
  
2. Eseguire Setup.bat dalla cartella di installazione dell'esempio. In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.  
  
3. Avviare BackendService.exe dalla directory \BackendService\bin in una finestra della console separata  
  
4. Avviare FacadeService.exe dalla directory \FacadeService\bin in una finestra della console separata  
  
5. Avviare Client.exe da \client\bin. L'attività del client viene visualizzata nella finestra dell'applicazione console.  
  
6. Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-clean-up-after-the-sample"></a>Per eseguire la pulizia dopo l'esempio  
  
1. Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\TrustedFacade`  

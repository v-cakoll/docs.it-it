---
title: Provider di appartenenza e di ruoli
ms.date: 03/30/2017
ms.assetid: 0d11a31c-e75f-4fcf-9cf4-b7f26e056bcd
ms.openlocfilehash: e77e353fba194cb25b466387cf9def6773635e00
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591761"
---
# <a name="membership-and-role-provider"></a>Provider di appartenenza e di ruoli
Nell'esempio relativo a appartenenza e provider di ruoli viene illustrato come un servizio può utilizzare i provider di appartenenze e ruoli di ASP.NET per autenticare e autorizzare i client.  
  
 In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 In questo esempio viene illustrato come eseguire le seguenti operazioni:  
  
- Un client può eseguire l'autenticazione utilizzando una combinazione nome utente-password.  
  
- Il server può convalidare le credenziali client rispetto al provider di appartenenze ASP.NET.  
  
- Il server può essere autenticato tramite il certificato X.509 del server.  
  
- Il server può eseguire il mapping del client autenticato a un ruolo utilizzando il provider di ruoli ASP.NET.  
  
- Il server può utilizzare `PrincipalPermissionAttribute` per controllare l'accesso a determinati metodi esposti dal servizio.  
  
 I provider di appartenenza e di ruoli sono configurati per utilizzare un archivio supportato da SQL Server. Una stringa di connessione e varie opzioni sono specificate nel file di configurazione del servizio. Al provider di appartenenza viene assegnato il nome `SqlMembershipProvider` mentre al provider di ruoli viene assegnato il nome `SqlRoleProvider`.  
  
```xml  
<!-- Set the connection string for SQL Server -->  
<connectionStrings>  
  <add name="SqlConn"
       connectionString="Data Source=localhost;Integrated Security=SSPI;Initial Catalog=aspnetdb;" />  
</connectionStrings>  
  
<system.web>  
  <!-- Configure the Sql Membership Provider -->  
  <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
    <providers>  
      <clear />  
      <add
        name="SqlMembershipProvider"
        type="System.Web.Security.SqlMembershipProvider"
        connectionStringName="SqlConn"  
        applicationName="MembershipAndRoleProviderSample"  
        enablePasswordRetrieval="false"  
        enablePasswordReset="false"  
        requiresQuestionAndAnswer="false"  
        requiresUniqueEmail="true"  
        passwordFormat="Hashed" />  
    </providers>  
  </membership>  
  
  <!-- Configure the Sql Role Provider -->  
  <roleManager enabled ="true"
               defaultProvider ="SqlRoleProvider" >  
    <providers>  
      <add name ="SqlRoleProvider"
           type="System.Web.Security.SqlRoleProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipAndRoleProviderSample"/>  
    </providers>  
  </roleManager>  
</system.web>  
```  
  
 Il servizio espone un solo endpoint per la comunicazione con il servizio, che viene definito mediante il file di configurazione Web.config. L'endpoint è costituito da un indirizzo, un'associazione e un contratto. L'associazione viene configurata con una classe standard `wsHttpBinding`, per la quale è impostata l'autenticazione Windows come predefinita. In questo esempio viene impostata la classe `wsHttpBinding` standard per utilizzare l'autenticazione del nome utente. Il comportamento specifica che il certificato server deve essere utilizzato per autenticare il servizio. Il certificato server deve contenere lo stesso valore per l' `SubjectName` `findValue` attributo nell' [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) elemento di configurazione. Il comportamento specifica inoltre che l'autenticazione delle coppie nome utente-password viene eseguita dal provider di appartenenze ASP.NET e il mapping dei ruoli viene eseguito dal provider di ruoli ASP.NET specificando i nomi definiti per i due provider.  
  
```xml  
<system.serviceModel>  
  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- Set up a binding that uses Username as the client credential type -->  
      <binding>  
        <security mode ="Message">  
          <message clientCredentialType ="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <behaviors>  
    <serviceBehaviors>  
      <behavior>  
        <!-- Configure role based authorization to use the Role Provider -->  
        <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                              roleProviderName ="SqlRoleProvider" />  
        <serviceCredentials>  
          <!-- Configure user name authentication to use the Membership Provider -->  
          <userNameAuthentication userNamePasswordValidationMode ="MembershipProvider"
                                  membershipProviderName ="SqlMembershipProvider"/>  
          <!-- Configure the service certificate -->  
          <serviceCertificate storeLocation ="LocalMachine"
                              storeName ="My"
                              x509FindType ="FindBySubjectName"  
                              findValue ="localhost" />  
        </serviceCredentials>  
        <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
        <serviceDebug includeExceptionDetailInFaults="false" />  
        <serviceMetadata httpGetEnabled="true"/>  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 Quando si esegue l'esempio, il client chiama le varie operazioni del servizio con tre account utente diversi: Alice, Bob e Charlie. Le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Tutte le 4 chiamate eseguite con l'account utente "Alice" hanno esito positivo. L'utente "Bob" ottiene un errore di accesso negato nel tentativo di chiamare il metodo Divide. L'utente "Charlie" ottiene un errore di accesso negato nel tentativo di chiamare il metodo Multiply. Premere INVIO nella finestra del client per arrestare il client.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Per compilare l'edizione C# o Visual Basic .NET della soluzione, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
2. Assicurarsi di aver configurato il [Database servizi per le applicazioni di ASP.NET](https://go.microsoft.com/fwlink/?LinkId=94997).  
  
    > [!NOTE]
    > Se si sta eseguendo SQL Server Express Edition, il nome del server è .\SQLEXPRESS. Questo server deve essere utilizzato durante la configurazione del database di Servizi per le applicazioni ASP.NET e nella stringa di connessione di Web. config.  
  
    > [!NOTE]
    > L'account del processo di lavoro di ASP.NET deve disporre delle autorizzazioni per il database creato in questo passaggio. Utilizzare l'utilità sqlcmd o SQL Server Management Studio per questo scopo.  
  
3. Per eseguire l'esempio su un solo computer o tra computer diversi, seguire le istruzioni indicate di seguito.  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>Per eseguire l'esempio nello stesso computer  
  
1. Verificare che il percorso includa la cartella in cui si trova Makecert.exe.  
  
2. Eseguire Setup. bat dalla cartella di installazione dell'esempio in un Prompt dei comandi per gli sviluppatori per l'esecuzione di Visual Studio con privilegi di amministratore. In questo modo vengono installati i certificati dei servizi necessari per l'esecuzione dell'esempio.  
  
3. Avviare Client.exe da \client\bin. L'attività del client viene visualizzata nella finestra dell'applicazione console.  
  
4. Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-run-the-sample-across-computers"></a>Per eseguire l'esempio tra più computer  
  
1. Creare una directory sul computer del servizio. Creare un'applicazione virtuale denominata servicemodelsamples per questa directory usando lo strumento di gestione di Internet Information Services (IIS).  
  
2. Copiare i file del programma del servizio da \inetpub\wwwroot\servicemodelsamples nella directory virtuale sul computer del servizio. Assicurarsi di copiare i file nella sottodirectory \bin e i file Setup.bat, GetComputerName.vbs e Cleanup.bat nel computer del servizio.  
  
3. Creare una directory sul client del servizio per i file binari del client.  
  
4. Copiare i file di programma del client nella directory del client sul computer relativo e i file Setup.bat, Cleanup.bat e ImportServiceCert.bat nel client.  
  
5. Sul server aprire un Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi amministrativi ed eseguire `setup.bat service` . Quando `setup.bat` si esegue con l' `service` argomento viene creato un certificato del servizio con il nome di dominio completo del computer e il certificato del servizio viene esportato in un file denominato Service. cer.  
  
6. Modificare Web. config per riflettere il nuovo nome del certificato (nell' `findValue` attributo in [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ), che corrisponde al nome di dominio completo del computer.  
  
7. Copiare il file Service.cer dalla directory del servizio nella directory del client sul computer relativo.  
  
8. Nel file Client.exe.config presente nel computer client modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio.  
  
9. Sul client aprire un Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi amministrativi ed eseguire ImportServiceCert. bat. In questo modo viene importato il certificato del servizio dal file Service.cer nell'archivio CurrentUser - TrustedPeople.  
  
10. Sul computer client avviare Client.exe da un prompt dei comandi. Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-clean-up-after-the-sample"></a>Per eseguire la pulizia dopo l'esempio  
  
- Eseguire Cleanup.bat nella cartella degli esempi dopo che l'esempio è stato completato.  
  
> [!NOTE]
> Questo script non rimuove i certificati del servizio da un client quando si esegue l'esempio tra più computer. Se sono stati eseguiti esempi Windows Communication Foundation (WCF) che usano certificati tra computer, assicurarsi di cancellare i certificati del servizio installati nell'archivio CurrentUser-TrustedPeople. Per eseguire questa operazione, usare il seguente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Ad esempio: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
## <a name="the-setup-batch-file"></a>File batch di installazione  
 Il file batch Setup.bat incluso in questo esempio consente di configurare il server con i certificati attinenti per eseguire un'applicazione indipendente che richiede la sicurezza server basata su certificato. Questo file batch deve essere modificato per funzionare tra computer diversi o nel caso in cui non sia ospitato.  
  
 Di seguito viene fornita una breve panoramica delle varie sezioni dei file batch in modo che possano essere modificate per l'esecuzione nella configurazione appropriata.  
  
- Creazione del certificato server.  
  
     Le righe seguenti del file batch Setup.bat creano il certificato server da usare. La variabile %SERVER_NAME% specifica il nome del server. Modificare questa variabile per specificare nome del server. Il valore predefinito di questo file batch è localhost.  
  
     Il certificato viene memorizzato nell'archivio personale nel percorso di archivio LocalMachine.  
  
    ```console
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
- Installazione del certificato server nell'archivio certificati attendibili del client.  
  
     Le righe seguenti nel file batch Setup.bat copiano il certificato server nell'archivio di persone attendibile del client. Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client. Se è già disponibile un certificato impostato come radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il popolamento dell'archivio certificati client con il certificato server non è necessario.  
  
    ```bat  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  

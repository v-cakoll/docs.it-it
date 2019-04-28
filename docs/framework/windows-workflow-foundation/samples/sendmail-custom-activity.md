---
title: Attività personalizzata SendMail
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: 89252098402deee991ea01b8e76082a5f4b8c389
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785944"
---
# <a name="sendmail-custom-activity"></a>Attività personalizzata SendMail
In questo esempio viene illustrato come creare un'attività personalizzata che deriva da <xref:System.Activities.AsyncCodeActivity> per inviare messaggi di posta elettronica tramite il protocollo SMTP da usare in un'applicazione flusso di lavoro. L'attività personalizzata Usa le funzionalità di <xref:System.Net.Mail.SmtpClient> per inviare posta elettronica in modo asincrono e per inviare posta elettronica con l'autenticazione. Nell'attività sono inoltre disponibili funzionalità per l'utente finale, ad esempio la modalità test, la sostituzione dei token, i modelli di file e il percorso di rilascio di prova.  
  
 Nella tabella seguente vengono indicati in dettaglio gli argomenti per l'attività `SendMail`.  
  
|Nome|Tipo|Descrizione|  
|-|-|-|  
|Host|Stringa|Indirizzo dell'host del server SMTP.|  
|Porta|Stringa|Porta del servizio SMTP nell'host.|  
|EnableSsl|bool|Specifica se la classe <xref:System.Net.Mail.SmtpClient> usa il protocollo SSL (Secure Sockets Layer) per crittografare la connessione.|  
|UserName|Stringa|Nome utente per configurare le credenziali per l'autenticazione della proprietà <xref:System.Net.Mail.SmtpClient.Credentials%2A> del mittente.|  
|Password|Stringa|Password per configurare le credenziali per l'autenticazione della proprietà <xref:System.Net.Mail.SmtpClient.Credentials%2A> del mittente.|  
|Oggetto|<xref:System.Activities.InArgument%601>\<string>|Oggetto del messaggio.|  
|Body|<xref:System.Activities.InArgument%601>\<string>|Corpo del messaggio.|  
|Allegati|<xref:System.Activities.InArgument%601>\<string>|Insieme di allegati utilizzato per archiviare i dati allegati al messaggio di posta elettronica.|  
|Da|<xref:System.Net.Mail.MailAddress>|Indirizzo del mittente per questo messaggio di posta elettronica.|  
|A|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Raccolta di indirizzi contenente i destinatari del messaggio di posta elettronica.|  
|CC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Raccolta contenente i destinatari della copia per conoscenza (CC) per questo messaggio di posta elettronica di indirizzi.|  
|BCC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Raccolta di indirizzi contenente i destinatari della copia per conoscenza nascosta (Ccn) per questo messaggio di posta elettronica.|  
|token|<xref:System.Activities.InArgument%601><IDictionary\<string, string>>|Token da sostituire nel corpo del messaggio. Questa funzionalità consente agli utenti di specificare alcuni valori nel corpo del messaggio che possono essere sostituiti in un secondo momento dai token specificati usando questa proprietà.|  
|BodyTemplateFilePath|Stringa|Percorso di un modello per il corpo del messaggio. L'attività `SendMail` copia il contenuto di questo file nella relativa proprietà del corpo.<br /><br /> Il modello può contenere token sostituiti dal contenuto della proprietà Token.|  
|TestMailTo|<xref:System.Net.Mail.MailAddress>|Quando questa proprietà è impostata, tutti i messaggi di posta elettronica vengono inviati all'indirizzo specificato in esso.<br /><br /> Questa proprietà deve essere usata quando si esegue il test di flussi di lavoro, Ad esempio, quando si desidera assicurarsi che tutti i messaggi di posta elettronica vengono inviati senza inviarli ai destinatari effettivi.|  
|TestDropPath|Stringa|Quando questa proprietà è impostata, tutti i messaggi di posta elettronica vengono salvati nel file specificato.<br /><br /> Questa proprietà dovrà essere utilizzato quando si esegue il test o il debug dei flussi di lavoro, assicurarsi che il formato e il contenuto dei messaggi di posta elettronica in uscita sia appropriato.|  
  
## <a name="solution-contents"></a>Contenuto della soluzione  
 Nella soluzione sono contenuti due progetti.  
  
|Progetto|Descrizione|File importanti|  
|-------------|-----------------|---------------------|  
|SendMail|Attività SendMail|1.  SendMail.cs: implementazione dell'attività principale<br />2.  SendMailDesigner.xaml e SendMailDesigner.xaml.cs: finestra di progettazione per l'attività SendMail<br />3.  MailTemplateBody.htm: modello per il messaggio di posta elettronica da inviare.|  
|SendMailTestClient|Client in cui eseguire il test dell'attività SendMail.  In questo progetto l'attività viene richiamata in due modi diversi, ovvero in modo dichiarativo e a livello di codice.|1.  Sequence1.xaml: flusso di lavoro che richiama l'attività SendMail.<br />2.  Program.cs: richiama Sequence1 e crea un flusso di lavoro a livello di codice che usa SendMail.|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a>Ulteriore configurazione dell'attività SendMail  
 Sebbene non illustrato nell'esempio, gli utenti possono configurare ulteriormente l'attività SendMail. Nelle tre sezioni successive viene illustrato come eseguire questa operazione.  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a>Invio di un messaggio di posta elettronica usando token specificati nel corpo del messaggio  
 In questo frammento di codice viene illustrato come è possibile inviare messaggi di posta elettronica nel cui corpo sono presenti token. Si noti il modo in cui i token vengono specificati nella proprietà Body. I valori per tali token vengono specificati nella proprietà Token.  
  
```html  
IDictionary<string, string> tokens = new Dictionary<string, string>();  
tokens.Add("@name", "John Doe");  
tokens.Add("@date", DateTime.Now.ToString());  
tokens.Add("@server", "localhost");  
  
new SendMail  
{  
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Body = "Hello @name. This is a test email sent from @server. Current date is @date",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens)  
};  
```  
  
### <a name="sending-an-email-using-a-template"></a>Invio di un messaggio di posta elettronica tramite un modello  
 In questo frammento di codice viene illustrato come inviare un messaggio di posta elettronica usando un token del modello nel corpo. Si noti che quando si imposta la proprietà `BodyTemplateFilePath` non è necessario specificare il valore per la proprietà Body (il contenuto del file modello verrà copiato nel corpo).  
  
```  
new SendMail  
{    
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
    BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",   
};  
```  
  
### <a name="sending-mails-in-testing-mode"></a>Invio di messaggi di posta elettronica in modalità test  
 Questo frammento di codice viene illustrato come impostare le due proprietà di test: impostando `TestMailTo` a tutti i messaggi verranno inviati a `john.doe@contoso.con` (senza tenere conto dei valori di a, Cc, Ccn). Se si imposta TestDropPath, tutti i messaggi di posta elettronica in uscita verranno inoltre salvati nel percorso specificato. È possibile impostare queste proprietà in modo indipendente l'una dall'altra perché non sono correlate.  
  
```  
new SendMail  
{    
   From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
   Subject = "Test email",  
   Host = "localhost",  
   Port = 25,  
   Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
   BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",  
   TestMailTo= new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   TestDropPath = @"c:\Samples\SendMail\TestDropPath\",  
};  
```  
  
## <a name="set-up-instructions"></a>Istruzioni di configurazione  
 Per eseguire l'esempio, è necessario disporre dell'accesso a un server SMTP.  
  
 Per altre informazioni sulla configurazione di un server SMTP, vedere i collegamenti seguenti.  
  
- [Microsoft Technet](https://go.microsoft.com/fwlink/?LinkId=166060)  
  
- [Configurazione del servizio SMTP (IIS 6.0)](https://go.microsoft.com/fwlink/?LinkId=150456)  
  
- [IIS 7.0: Configurare la posta elettronica SMTP](https://go.microsoft.com/fwlink/?LinkId=150457)  
  
- [Come installare il servizio SMTP](https://go.microsoft.com/fwlink/?LinkId=150458)  
  
 Per eseguire il download, sono disponibili emulatori SMTP forniti da terze parti.  
  
##### <a name="to-run-this-sample"></a>Per eseguire l'esempio  
  
1. Con Visual Studio 2010, aprire il file della soluzione SendMail.  
  
2. Verificare di disporre dell'accesso a un server SMTP valido. Vedere le istruzioni di configurazione.  
  
3. Configurare il programma con l'indirizzo del server e da e a indirizzi di posta elettronica.  
  
     Per eseguire correttamente questo esempio, si potrebbe essere necessario configurare il valore di dal e indirizzi di posta elettronica e l'indirizzo del server SMTP in Program.cs e in Sequence. Poiché i messaggi di posta elettronica vengono inviati in due modalità diverse, sarà necessario modificare l'indirizzo in entrambi i percorsi.  
  
4. Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
5. Per eseguire la soluzione, premere CTRL+F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
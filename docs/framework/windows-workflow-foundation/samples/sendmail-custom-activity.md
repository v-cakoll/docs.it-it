---
title: Attività personalizzata SendMail
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: b1e2d58a09362569d4d408f6e1c9e589aa6bda76
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715572"
---
# <a name="sendmail-custom-activity"></a><span data-ttu-id="5d3da-102">Attività personalizzata SendMail</span><span class="sxs-lookup"><span data-stu-id="5d3da-102">SendMail Custom Activity</span></span>
<span data-ttu-id="5d3da-103">In questo esempio viene illustrato come creare un'attività personalizzata che deriva da <xref:System.Activities.AsyncCodeActivity> per inviare messaggi di posta elettronica tramite il protocollo SMTP da usare in un'applicazione flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5d3da-103">This sample demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span> <span data-ttu-id="5d3da-104">L'attività personalizzata usa le funzionalità di <xref:System.Net.Mail.SmtpClient> per inviare messaggi di posta elettronica in modo asincrono e per inviare messaggi di posta elettronica con l'autenticazione di.</span><span class="sxs-lookup"><span data-stu-id="5d3da-104">The custom activity uses the capabilities of <xref:System.Net.Mail.SmtpClient> to send email asynchronously and to send mail with authentication.</span></span> <span data-ttu-id="5d3da-105">Nell'attività sono inoltre disponibili funzionalità per l'utente finale, ad esempio la modalità test, la sostituzione dei token, i modelli di file e il percorso di rilascio di prova.</span><span class="sxs-lookup"><span data-stu-id="5d3da-105">It also provides some end-user features like test mode, token replacement, file templates, and test drop path.</span></span>  
  
 <span data-ttu-id="5d3da-106">Nella tabella seguente vengono indicati in dettaglio gli argomenti per l'attività `SendMail`.</span><span class="sxs-lookup"><span data-stu-id="5d3da-106">The following table details the arguments for the `SendMail` activity.</span></span>  
  
|<span data-ttu-id="5d3da-107">Name</span><span class="sxs-lookup"><span data-stu-id="5d3da-107">Name</span></span>|<span data-ttu-id="5d3da-108">Tipo di</span><span class="sxs-lookup"><span data-stu-id="5d3da-108">Type</span></span>|<span data-ttu-id="5d3da-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d3da-109">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5d3da-110">Host</span><span class="sxs-lookup"><span data-stu-id="5d3da-110">Host</span></span>|<span data-ttu-id="5d3da-111">Stringa</span><span class="sxs-lookup"><span data-stu-id="5d3da-111">String</span></span>|<span data-ttu-id="5d3da-112">Indirizzo dell'host del server SMTP.</span><span class="sxs-lookup"><span data-stu-id="5d3da-112">Address of the SMTP server host.</span></span>|  
|<span data-ttu-id="5d3da-113">Port</span><span class="sxs-lookup"><span data-stu-id="5d3da-113">Port</span></span>|<span data-ttu-id="5d3da-114">Stringa</span><span class="sxs-lookup"><span data-stu-id="5d3da-114">String</span></span>|<span data-ttu-id="5d3da-115">Porta del servizio SMTP nell'host.</span><span class="sxs-lookup"><span data-stu-id="5d3da-115">Port of the SMTP service in the host.</span></span>|  
|<span data-ttu-id="5d3da-116">EnableSsl</span><span class="sxs-lookup"><span data-stu-id="5d3da-116">EnableSsl</span></span>|<span data-ttu-id="5d3da-117">bool</span><span class="sxs-lookup"><span data-stu-id="5d3da-117">bool</span></span>|<span data-ttu-id="5d3da-118">Specifica se la classe <xref:System.Net.Mail.SmtpClient> usa il protocollo SSL (Secure Sockets Layer) per crittografare la connessione.</span><span class="sxs-lookup"><span data-stu-id="5d3da-118">Specifies whether the <xref:System.Net.Mail.SmtpClient> uses Secure Sockets Layer (SSL) to encrypt the connection.</span></span>|  
|<span data-ttu-id="5d3da-119">Nome utente</span><span class="sxs-lookup"><span data-stu-id="5d3da-119">UserName</span></span>|<span data-ttu-id="5d3da-120">Stringa</span><span class="sxs-lookup"><span data-stu-id="5d3da-120">String</span></span>|<span data-ttu-id="5d3da-121">Nome utente per configurare le credenziali per l'autenticazione della proprietà <xref:System.Net.Mail.SmtpClient.Credentials%2A> del mittente.</span><span class="sxs-lookup"><span data-stu-id="5d3da-121">Username to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="5d3da-122">Password</span><span class="sxs-lookup"><span data-stu-id="5d3da-122">Password</span></span>|<span data-ttu-id="5d3da-123">Stringa</span><span class="sxs-lookup"><span data-stu-id="5d3da-123">String</span></span>|<span data-ttu-id="5d3da-124">Password per configurare le credenziali per l'autenticazione della proprietà <xref:System.Net.Mail.SmtpClient.Credentials%2A> del mittente.</span><span class="sxs-lookup"><span data-stu-id="5d3da-124">Password to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="5d3da-125">Subject</span><span class="sxs-lookup"><span data-stu-id="5d3da-125">Subject</span></span>|<span data-ttu-id="5d3da-126"><xref:System.Activities.InArgument%601>stringa \<</span><span class="sxs-lookup"><span data-stu-id="5d3da-126"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="5d3da-127">Oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="5d3da-127">Subject of the message.</span></span>|  
|<span data-ttu-id="5d3da-128">Body</span><span class="sxs-lookup"><span data-stu-id="5d3da-128">Body</span></span>|<span data-ttu-id="5d3da-129"><xref:System.Activities.InArgument%601>stringa \<</span><span class="sxs-lookup"><span data-stu-id="5d3da-129"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="5d3da-130">Corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="5d3da-130">Body of the message.</span></span>|  
|<span data-ttu-id="5d3da-131">Allegati</span><span class="sxs-lookup"><span data-stu-id="5d3da-131">Attachments</span></span>|<span data-ttu-id="5d3da-132"><xref:System.Activities.InArgument%601>stringa \<</span><span class="sxs-lookup"><span data-stu-id="5d3da-132"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="5d3da-133">Raccolta di allegati utilizzata per archiviare i dati allegati a questo messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5d3da-133">Attachment collection used to store data attached to this email message.</span></span>|  
|<span data-ttu-id="5d3da-134">Da</span><span class="sxs-lookup"><span data-stu-id="5d3da-134">From</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="5d3da-135">Indirizzo mittente per questo messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5d3da-135">From address for this email message.</span></span>|  
|<span data-ttu-id="5d3da-136">Per</span><span class="sxs-lookup"><span data-stu-id="5d3da-136">To</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="5d3da-137">Raccolta di indirizzi contenente i destinatari di questo messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5d3da-137">Address collection that contains the recipients of this email message.</span></span>|  
|<span data-ttu-id="5d3da-138">CC</span><span class="sxs-lookup"><span data-stu-id="5d3da-138">CC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="5d3da-139">Raccolta di indirizzi contenente i destinatari della copia a carboni (CC) per questo messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5d3da-139">Address collection that contains the carbon copy (CC) recipients for this email message.</span></span>|  
|<span data-ttu-id="5d3da-140">BCC</span><span class="sxs-lookup"><span data-stu-id="5d3da-140">BCC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="5d3da-141">Raccolta di indirizzi contenente i destinatari della copia per conoscenza nascosta (Ccn) per questo messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5d3da-141">Address collection that contains the blind carbon copy (BCC) recipients for this email message.</span></span>|  
|<span data-ttu-id="5d3da-142">token</span><span class="sxs-lookup"><span data-stu-id="5d3da-142">Tokens</span></span>|<span data-ttu-id="5d3da-143"><xref:System.Activities.InArgument%601>< IDictionary\<stringa, stringa > ></span><span class="sxs-lookup"><span data-stu-id="5d3da-143"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span></span>|<span data-ttu-id="5d3da-144">Token da sostituire nel corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="5d3da-144">Tokens to replace in the body.</span></span> <span data-ttu-id="5d3da-145">Questa funzionalità consente agli utenti di specificare alcuni valori nel corpo del messaggio che possono essere sostituiti in un secondo momento dai token specificati usando questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="5d3da-145">This feature allows users to specify some values in the body than can be replaced later by the tokens provided using this property.</span></span>|  
|<span data-ttu-id="5d3da-146">BodyTemplateFilePath</span><span class="sxs-lookup"><span data-stu-id="5d3da-146">BodyTemplateFilePath</span></span>|<span data-ttu-id="5d3da-147">Stringa</span><span class="sxs-lookup"><span data-stu-id="5d3da-147">String</span></span>|<span data-ttu-id="5d3da-148">Percorso di un modello per il corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="5d3da-148">Path of a template for the body.</span></span> <span data-ttu-id="5d3da-149">L'attività `SendMail` copia il contenuto di questo file nella relativa proprietà del corpo.</span><span class="sxs-lookup"><span data-stu-id="5d3da-149">The `SendMail` activity copies the contents of this file to its body property.</span></span><br /><br /> <span data-ttu-id="5d3da-150">Il modello può contenere token sostituiti dal contenuto della proprietà Token.</span><span class="sxs-lookup"><span data-stu-id="5d3da-150">The template can contain tokens that are replaced by the contents of the tokens property.</span></span>|  
|<span data-ttu-id="5d3da-151">TestMailTo</span><span class="sxs-lookup"><span data-stu-id="5d3da-151">TestMailTo</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="5d3da-152">Quando questa proprietà è impostata, tutti i messaggi di posta elettronica vengono inviati all'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="5d3da-152">When this property is set, all emails are sent to the address specified in it.</span></span><br /><br /> <span data-ttu-id="5d3da-153">Questa proprietà deve essere usata quando si esegue il test di flussi di lavoro,</span><span class="sxs-lookup"><span data-stu-id="5d3da-153">This property is intended to be used when testing workflows.</span></span> <span data-ttu-id="5d3da-154">Ad esempio, quando si desidera assicurarsi che tutti i messaggi di posta elettronica vengano inviati senza inviarli ai destinatari effettivi.</span><span class="sxs-lookup"><span data-stu-id="5d3da-154">For example, when you want to make sure that all emails are sent without sending them to the actual recipients.</span></span>|  
|<span data-ttu-id="5d3da-155">TestDropPath</span><span class="sxs-lookup"><span data-stu-id="5d3da-155">TestDropPath</span></span>|<span data-ttu-id="5d3da-156">Stringa</span><span class="sxs-lookup"><span data-stu-id="5d3da-156">String</span></span>|<span data-ttu-id="5d3da-157">Quando questa proprietà è impostata, anche tutti i messaggi di posta elettronica vengono salvati nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="5d3da-157">When this property is set, all emails are also saved in the specified file.</span></span><br /><br /> <span data-ttu-id="5d3da-158">Questa proprietà deve essere usata quando si esegue il test o il debug di flussi di lavoro, per assicurarsi che il formato e il contenuto dei messaggi di posta elettronica in uscita siano appropriati.</span><span class="sxs-lookup"><span data-stu-id="5d3da-158">This property is intended to be used when you are testing or debugging workflows, to make sure that the format and contents of the outgoing emails is appropriate.</span></span>|  
  
## <a name="solution-contents"></a><span data-ttu-id="5d3da-159">Contenuto della soluzione</span><span class="sxs-lookup"><span data-stu-id="5d3da-159">Solution Contents</span></span>  
 <span data-ttu-id="5d3da-160">Nella soluzione sono contenuti due progetti.</span><span class="sxs-lookup"><span data-stu-id="5d3da-160">The solution contains two projects.</span></span>  
  
|<span data-ttu-id="5d3da-161">Progetto di</span><span class="sxs-lookup"><span data-stu-id="5d3da-161">Project</span></span>|<span data-ttu-id="5d3da-162">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d3da-162">Description</span></span>|<span data-ttu-id="5d3da-163">File importanti</span><span class="sxs-lookup"><span data-stu-id="5d3da-163">Important Files</span></span>|  
|-------------|-----------------|---------------------|  
|<span data-ttu-id="5d3da-164">SendMail</span><span class="sxs-lookup"><span data-stu-id="5d3da-164">SendMail</span></span>|<span data-ttu-id="5d3da-165">Attività SendMail</span><span class="sxs-lookup"><span data-stu-id="5d3da-165">The SendMail activity</span></span>|<span data-ttu-id="5d3da-166">1. SendMail.cs: implementazione per l'attività principale</span><span class="sxs-lookup"><span data-stu-id="5d3da-166">1.  SendMail.cs: implementation for the main activity</span></span><br /><span data-ttu-id="5d3da-167">2. SendMailDesigner. XAML e SendMailDesigner.xaml.cs: finestra di progettazione per l'attività SendMail</span><span class="sxs-lookup"><span data-stu-id="5d3da-167">2.  SendMailDesigner.xaml and SendMailDesigner.xaml.cs: designer for the SendMail activity</span></span><br /><span data-ttu-id="5d3da-168">3. MailTemplateBody. htm: modello per il messaggio di posta elettronica da inviare.</span><span class="sxs-lookup"><span data-stu-id="5d3da-168">3.  MailTemplateBody.htm: template for the email to be sent out.</span></span>|  
|<span data-ttu-id="5d3da-169">SendMailTestClient</span><span class="sxs-lookup"><span data-stu-id="5d3da-169">SendMailTestClient</span></span>|<span data-ttu-id="5d3da-170">Client in cui eseguire il test dell'attività SendMail.</span><span class="sxs-lookup"><span data-stu-id="5d3da-170">Client to test the SendMail activity.</span></span>  <span data-ttu-id="5d3da-171">In questo progetto l'attività viene richiamata in due modi diversi, ovvero in modo dichiarativo e a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="5d3da-171">This project demonstrates two ways of invoking the SendMail activity: declaratively, and programmatically.</span></span>|<span data-ttu-id="5d3da-172">1. Sequence1. XAML: flusso di lavoro che richiama l'attività SendMail.</span><span class="sxs-lookup"><span data-stu-id="5d3da-172">1.  Sequence1.xaml: workflow that invokes the SendMail activity.</span></span><br /><span data-ttu-id="5d3da-173">2. Program.cs: richiama Sequence1 e crea anche un flusso di lavoro a livello di codice che usa SendMail.</span><span class="sxs-lookup"><span data-stu-id="5d3da-173">2.  Program.cs: invokes Sequence1 and also creates a workflow programmatically that uses SendMail.</span></span>|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a><span data-ttu-id="5d3da-174">Ulteriore configurazione dell'attività SendMail</span><span class="sxs-lookup"><span data-stu-id="5d3da-174">Further configuration of the SendMail activity</span></span>  
 <span data-ttu-id="5d3da-175">Sebbene non illustrato nell'esempio, gli utenti possono configurare ulteriormente l'attività SendMail.</span><span class="sxs-lookup"><span data-stu-id="5d3da-175">Although not shown in the sample, users can perform addition configuration of the SendMail activity.</span></span> <span data-ttu-id="5d3da-176">Nelle tre sezioni successive viene illustrato come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="5d3da-176">The next three sections demonstrate how this is done.</span></span>  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a><span data-ttu-id="5d3da-177">Invio di un messaggio di posta elettronica usando token specificati nel corpo del messaggio</span><span class="sxs-lookup"><span data-stu-id="5d3da-177">Sending an email using tokens specified in the body</span></span>  
 <span data-ttu-id="5d3da-178">In questo frammento di codice viene illustrato come è possibile inviare messaggi di posta elettronica nel cui corpo sono presenti token.</span><span class="sxs-lookup"><span data-stu-id="5d3da-178">This code snippet demonstrates how you can send email with tokens in the body.</span></span> <span data-ttu-id="5d3da-179">Si noti il modo in cui i token vengono specificati nella proprietà Body.</span><span class="sxs-lookup"><span data-stu-id="5d3da-179">Notice how the tokens are provided in the body property.</span></span> <span data-ttu-id="5d3da-180">I valori per tali token vengono specificati nella proprietà Token.</span><span class="sxs-lookup"><span data-stu-id="5d3da-180">Values for those tokens are provided to the tokens property.</span></span>  
  
```csharp  
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
  
### <a name="sending-an-email-using-a-template"></a><span data-ttu-id="5d3da-181">Invio di un messaggio di posta elettronica tramite un modello</span><span class="sxs-lookup"><span data-stu-id="5d3da-181">Sending an email using a template</span></span>  
 <span data-ttu-id="5d3da-182">In questo frammento di codice viene illustrato come inviare un messaggio di posta elettronica usando un token del modello nel corpo.</span><span class="sxs-lookup"><span data-stu-id="5d3da-182">This snippet shows how to send an email using a template tokens in the body.</span></span> <span data-ttu-id="5d3da-183">Si noti che quando si imposta la proprietà `BodyTemplateFilePath` non è necessario specificare il valore per la proprietà Body (il contenuto del file modello verrà copiato nel corpo).</span><span class="sxs-lookup"><span data-stu-id="5d3da-183">Notice that when setting the `BodyTemplateFilePath` property we don’t need to provide the value for Body property (the contents of the template file will be copied to the body).</span></span>  
  
```csharp  
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
  
### <a name="sending-mails-in-testing-mode"></a><span data-ttu-id="5d3da-184">Invio di messaggi di posta elettronica in modalità test</span><span class="sxs-lookup"><span data-stu-id="5d3da-184">Sending Mails in Testing Mode</span></span>  
 <span data-ttu-id="5d3da-185">Questo frammento di codice Mostra come impostare le due proprietà di test: impostando `TestMailTo` su tutti i messaggi verranno inviati a `john.doe@contoso.con` (senza considerare i valori di a, CC, Ccn).</span><span class="sxs-lookup"><span data-stu-id="5d3da-185">This code snippet shows how to set the two testing properties: by setting `TestMailTo` to all messages will be sent to `john.doe@contoso.con` (without regard of the values of To, Cc, Bcc).</span></span> <span data-ttu-id="5d3da-186">Se si imposta TestDropPath, tutti i messaggi di posta elettronica in uscita verranno inoltre salvati nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="5d3da-186">By setting TestDropPath all outgoing emails will be also recorded in the provided path.</span></span> <span data-ttu-id="5d3da-187">È possibile impostare queste proprietà in modo indipendente l'una dall'altra perché non sono correlate.</span><span class="sxs-lookup"><span data-stu-id="5d3da-187">These properties can be set independently (they are not related).</span></span>  
  
```csharp  
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
  
## <a name="set-up-instructions"></a><span data-ttu-id="5d3da-188">Istruzioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="5d3da-188">Set-Up Instructions</span></span>  
 <span data-ttu-id="5d3da-189">Per eseguire l'esempio, è necessario disporre dell'accesso a un server SMTP.</span><span class="sxs-lookup"><span data-stu-id="5d3da-189">Access to a SMTP server is required for this sample.</span></span>  
  
 <span data-ttu-id="5d3da-190">Per ulteriori informazioni sulla configurazione di un server SMTP, vedere i collegamenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="5d3da-190">For more information about setting up a SMTP server, see the following links.</span></span>  
  
- [<span data-ttu-id="5d3da-191">Microsoft TechNet</span><span class="sxs-lookup"><span data-stu-id="5d3da-191">Microsoft Technet</span></span>](https://go.microsoft.com/fwlink/?LinkId=166060)  
  
- [<span data-ttu-id="5d3da-192">Configurazione del servizio SMTP (IIS 6,0)</span><span class="sxs-lookup"><span data-stu-id="5d3da-192">Configuring the SMTP Service (IIS 6.0)</span></span>](https://go.microsoft.com/fwlink/?LinkId=150456)  
  
- [<span data-ttu-id="5d3da-193">IIS 7,0: configurare la posta elettronica SMTP</span><span class="sxs-lookup"><span data-stu-id="5d3da-193">IIS 7.0: Configure SMTP E-Mail</span></span>](https://go.microsoft.com/fwlink/?LinkId=150457)  
  
- [<span data-ttu-id="5d3da-194">Come installare il servizio SMTP</span><span class="sxs-lookup"><span data-stu-id="5d3da-194">How to Install the SMTP Service</span></span>](https://go.microsoft.com/fwlink/?LinkId=150458)  
  
 <span data-ttu-id="5d3da-195">Per eseguire il download, sono disponibili emulatori SMTP forniti da terze parti.</span><span class="sxs-lookup"><span data-stu-id="5d3da-195">SMTP emulators provided by third parties are available for download.</span></span>  
  
##### <a name="to-run-this-sample"></a><span data-ttu-id="5d3da-196">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="5d3da-196">To run this sample</span></span>  
  
1. <span data-ttu-id="5d3da-197">Con Visual Studio 2010 aprire il file della soluzione SendMail. sln.</span><span class="sxs-lookup"><span data-stu-id="5d3da-197">Using Visual Studio 2010, open the SendMail.sln solution file.</span></span>  
  
2. <span data-ttu-id="5d3da-198">Verificare di disporre dell'accesso a un server SMTP valido.</span><span class="sxs-lookup"><span data-stu-id="5d3da-198">Ensure that you have access to a valid SMTP server.</span></span> <span data-ttu-id="5d3da-199">Vedere le istruzioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="5d3da-199">See the set-up instructions.</span></span>  
  
3. <span data-ttu-id="5d3da-200">Configurare il programma con l'indirizzo del server e da e verso gli indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5d3da-200">Configure the program with your server address, and From and To email addresses.</span></span>  
  
     <span data-ttu-id="5d3da-201">Per eseguire correttamente questo esempio, potrebbe essere necessario configurare il valore di da e in indirizzi di posta elettronica e l'indirizzo del server SMTP in Program.cs e in Sequence. XAML.</span><span class="sxs-lookup"><span data-stu-id="5d3da-201">To correctly run this sample, you may need to configure the value of From and To email addresses and the address of the SMTP server in  Program.cs and in Sequence.xaml.</span></span> <span data-ttu-id="5d3da-202">Poiché i messaggi di posta elettronica vengono inviati in due modalità diverse, sarà necessario modificare l'indirizzo in entrambi i percorsi.</span><span class="sxs-lookup"><span data-stu-id="5d3da-202">You will need to change the address in both locations since the program sends mail in two different ways</span></span>  
  
4. <span data-ttu-id="5d3da-203">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="5d3da-203">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5. <span data-ttu-id="5d3da-204">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="5d3da-204">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5d3da-205">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="5d3da-205">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5d3da-206">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="5d3da-206">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="5d3da-207">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="5d3da-207">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5d3da-208">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="5d3da-208">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`

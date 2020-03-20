---
title: Integrated Windows Authentication with Extended Protection
ms.date: 03/30/2017
ms.assetid: 81731998-d5e7-49e4-ad38-c8e6d01689d0
ms.openlocfilehash: c4afc008f600c9be0040f8d7623f5e20623dfd7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74444237"
---
# <a name="integrated-windows-authentication-with-extended-protection"></a>Integrated Windows Authentication with Extended Protection
Sono stati apportati alcuni miglioramenti che influiscono sul modo in cui l'autenticazione integrata di Windows viene gestita da <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpListener>, <xref:System.Net.Mail.SmtpClient>, <xref:System.Net.Security.SslStream>, <xref:System.Net.Security.NegotiateStream> e dalle classi correlate in <xref:System.Net> e negli spazi dei nomi correlati. È stato aggiunto il supporto per la protezione estesa per migliorare la sicurezza.  
  
 Queste modifiche possono influire sulle applicazioni che usano queste classi per effettuare richieste Web e ricevere risposte in cui viene usata l'autenticazione integrata di Windows. Questa modifica può anche influire sulle applicazioni client e sui server Web configurati per l'uso dell'autenticazione integrata di Windows.  
  
 Queste modifiche possono influire anche sulle applicazioni che usano queste classi per effettuare altri tipi di richieste e ricevere risposte in cui viene usata l'autenticazione integrata di Windows.  
  
 Le modifiche per supportare la protezione estesa sono disponibili solo per le applicazioni in esecuzione su Windows 7 e Windows Server 2008 R2. Le funzionalità di protezione estesa non sono disponibili nelle versioni precedenti di Windows.  
  
## <a name="overview"></a>Panoramica  
 La progettazione dell'autenticazione integrata di Windows fa sì che alcune risposte con richiesta di verifica delle credenziali siano universali, ovvero possano essere riutilizzate o inoltrate. Le risposte con richiesta di verifica devono essere costruite almeno con informazioni specifiche sulla destinazione e preferibilmente anche con alcune informazioni specifiche sul canale. I servizi possono quindi fornire protezione estesa per garantire che le risposte con richiesta di verifica delle credenziali contengano informazioni specifiche sui servizi, ad esempio un nome dell'entità servizio (SPN). Con queste informazioni nello scambio di credenziali, i servizi possono offrire protezione migliore contro l'uso dannoso di risposte con richiesta di verifica di credenziali usate in modo improprio.  
  
 La progettazione con protezione estesa è un miglioramento per i protocolli di autenticazione sviluppati per prevenire gli attacchi di inoltro autenticato. Questo tipo di progettazione è basato sul concetto di informazioni sull'associazione di canali e servizi.  
  
 Gli obiettivi complessivi sono i seguenti:  
  
1. Se il client viene aggiornato per supportare la protezione estesa, le applicazioni devono fornire informazioni sull'associazione di canali e sull'associazione di servizi a tutti i protocolli di autenticazione supportati. Le informazioni sull'associazione di canali possono essere fornite solo quando è presente un canale (TLS) a cui eseguire l'associazione. Le informazioni sull'associazione di servizi devono essere fornite sempre.  
  
2. I server aggiornati configurati correttamente possono verificare le informazioni sull'associazione di canali e servizi quando queste sono presenti nel token di autenticazione client e rifiutare il tentativo di autenticazione se le associazioni di canali non corrispondono. A seconda dello scenario di distribuzione, i server possono verificare l'associazione di canali, l'associazione di servizi o entrambe.  
  
3. I server aggiornati possono accettare o rifiutare richieste client di livello inferiore che non contengono le informazioni sull'associazione di canali basate sui criteri.  
  
 Le informazioni usate dalla protezione estesa sono costituite da uno o entrambi gli elementi seguenti:  
  
1. Token di associazione del canale.  
  
2. Informazioni sull'associazione di servizi sotto forma di nome dell'entità servizio o SPN.  
  
 Le informazioni sull'associazione di servizi indicano l'intenzione di un client di eseguire l'autenticazione in un endpoint servizio specifico. Queste informazioni vengono comunicate dal client al server con le proprietà seguenti:  
  
- Il valore SPN deve essere disponibile al server che esegue l'autenticazione client in formato testo non crittografato.  
  
- Il valore dell'SPN è pubblico.  
  
- L'SPN deve essere protetto con crittografia durante il transito, in modo che un attacco man-in-the-middle non possa inserirne, rimuoverne o modificarne il valore.  
  
 Un token di associazione del canale è una proprietà del canale sicuro esterno, ad esempio TLS, usata per associarlo a una conversazione tramite un canale autenticato dal client. Il token di associazione del canale deve avere le proprietà seguenti, definite anche dal documento IETF RFC 5056:  
  
- Quando è presente un canale esterno, il valore del token di associazione del canale deve essere una proprietà che identifica il canale esterno o l'endpoint servizio, cui arrivano in modo indipendente sia il lato client sia il lato server di una conversazione.  
  
- Il valore del token di associazione del canale inviato dal client non deve poter essere danneggiato da un utente malintenzionato.  
  
- La segretezza del valore del token di associazione del canale non è garantita. Tuttavia, questo non significa che il valore delle informazioni sull'associazione di servizi e di canali possa essere sempre esaminato da altri componenti oltre al server che esegue l'autenticazione, in quanto può essere crittografato dal protocollo usato per trasmettere il token di associazione del canale.  
  
- L'integrità del token di associazione del canale deve essere protetta con crittografia durante il transito, in modo che un utente malintenzionato non possa inserirne, rimuoverne o modificarne il valore.  
  
 L'associazione di canali viene eseguita dal client che trasferisce l'SPN e il token di associazione del canale al server in modo a prova di manomissione. Il server convalida le informazioni sull'associazione di canali in base ai criteri e rifiuta i tentativi di autenticazione per cui determina di non essere la destinazione prevista. In questo modo, i due canali vengono associati con crittografia.  
  
 Per mantenere la compatibilità con client e applicazioni esistenti, un server può essere configurato per consentire i tentativi di autenticazione da parte dei client che non supportano ancora la protezione estesa. Questa è definita una configurazione "parzialmente avanzata", diversa da una configurazione "completamente avanzata".  
  
 Più componenti negli spazi dei nomi <xref:System.Net> e <xref:System.Net.Security> eseguono l'autenticazione integrata di Windows per conto di un'applicazione chiamante. Questa sezione descrive le modifiche apportate ai componenti System.Net per aggiungere la protezione estesa quando usano l'autenticazione integrata di Windows.  
  
 La protezione estesa è attualmente supportata in Windows 7. Viene fornito un meccanismo in base al quale un'applicazione può determinare se il sistema operativo supporta la protezione estesa.  
  
## <a name="changes-to-support-extended-protection"></a>Modifiche apportate per supportare la protezione estesa  
 A seconda del protocollo di autenticazione in uso, il processo di autenticazione usato con l'autenticazione integrata di Windows include spesso una richiesta di verifica inviata dal computer di destinazione e quindi ritrasmessa al computer client. La protezione estesa aggiunge nuove funzionalità a questo processo di autenticazione.  
  
 Lo spazio dei nomi <xref:System.Security.Authentication.ExtendedProtection> fornisce il supporto per l'autenticazione con protezione estesa per le applicazioni. La classe <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding> in questo spazio dei nomi rappresenta un'associazione di canali. La classe <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> in questo spazio dei nomi rappresenta i criteri di protezione estesa usati dal server per convalidare le connessioni client in ingresso. Altri membri della classe vengono usati con la protezione estesa.  
  
 Per le applicazioni server, queste classi includono gli oggetti seguenti:  
  
 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> che include gli elementi seguenti:  
  
- Proprietà <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.OSSupportsExtendedProtection%2A> che indica se il sistema operativo supporta l'autenticazione integrata di Windows con protezione estesa.  
  
- Valore di <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> che indica quando i criteri di protezione estesa devono essere applicati.  
  
- Valore di <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> che indica lo scenario di distribuzione. Questo valore influisce sul modo in cui viene verificata la protezione estesa.  
  
- Oggetto <xref:System.Security.Authentication.ExtendedProtection.ServiceNameCollection> facoltativo che contiene l'elenco di SPN personalizzati, usato per verificare la corrispondenza rispetto all'SPN fornito dal client come destinazione prevista dell'autenticazione.  
  
- Oggetto <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding> facoltativo che contiene un'associazione di canali personalizzata da usare per la convalida. Questo scenario non rappresenta un caso comune  
  
 Lo spazio dei nomi <xref:System.Security.Authentication.ExtendedProtection.Configuration> fornisce il supporto per la configurazione dell'autenticazione con protezione estesa per le applicazioni.  
  
 Sono state apportate alcune modifiche alle funzionalità per supportare la protezione estesa nello spazio dei nomi <xref:System.Net> esistente. Queste modifiche includono, ad esempio:  
  
- Nuova classe <xref:System.Net.TransportContext> aggiunta allo spazio dei nomi <xref:System.Net> che rappresenta un contesto di trasporto.  
  
- Nuovi metodi di overload <xref:System.Net.HttpWebRequest.EndGetRequestStream%2A> e <xref:System.Net.HttpWebRequest.GetRequestStream%2A> nella classe <xref:System.Net.HttpWebRequest> che permettono il recupero di <xref:System.Net.TransportContext> per supportare la protezione estesa per le applicazioni client.  
  
- Aggiunte alle classi <xref:System.Net.HttpListener> e <xref:System.Net.HttpListenerRequest> per supportare le applicazioni server.  
  
 È stata apportata una modifica per supportare la protezione estesa per le applicazioni client SMTP nello spazio dei nomi <xref:System.Net.Mail> esistente:  
  
- Proprietà <xref:System.Net.Mail.SmtpClient.TargetName%2A> nella classe <xref:System.Net.Mail.SmtpClient> che rappresenta l'SPN da usare per l'autenticazione quando si usa la protezione estesa per applicazioni client SMTP.  
  
 Sono state apportate alcune modifiche alle funzionalità per supportare la protezione estesa nello spazio dei nomi <xref:System.Net.Security> esistente. Queste modifiche includono, ad esempio:  
  
- Nuovi metodi di overload <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A> e <xref:System.Net.Security.NegotiateStream.AuthenticateAsClient%2A> nella classe <xref:System.Net.Security.NegotiateStream> che permettono il passaggio di un token di associazione del canale per supportare la protezione estesa per le applicazioni client.  
  
- Nuovi metodi di overload <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A> e <xref:System.Net.Security.NegotiateStream.AuthenticateAsServer%2A> nella classe <xref:System.Net.Security.NegotiateStream> che permettono il passaggio di un oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> per supportare la protezione estesa per le applicazioni server.  
  
- Nuova proprietà <xref:System.Net.Security.SslStream.TransportContext%2A> nella classe <xref:System.Net.Security.SslStream> per supportare la protezione estesa per le applicazioni client e server.  
  
 Proprietà <xref:System.Net.Configuration.SmtpNetworkElement> aggiunta per supportare la configurazione della protezione estesa per client SMTP nello spazio dei nomi <xref:System.Net.Security>.  
  
## <a name="extended-protection-for-client-applications"></a>Protezione estesa per applicazioni client  
 Il supporto della protezione estesa per la maggior parte delle applicazioni client viene applicato automaticamente. Le classi <xref:System.Net.HttpWebRequest> e <xref:System.Net.Mail.SmtpClient> supportano la protezione estesa ogni volta che la versione sottostante di Windows supporta la protezione estesa. Un'istanza <xref:System.Net.HttpWebRequest> invia un SPN costruito da <xref:System.Uri>. Per impostazione predefinita, un'istanza <xref:System.Net.Mail.SmtpClient> invia un SPN costruito dal nome host del server di posta SMTP.  
  
 Per l'autenticazione personalizzata, le applicazioni client possono usare i metodi <xref:System.Net.HttpWebRequest.EndGetRequestStream%28System.IAsyncResult%2CSystem.Net.TransportContext%40%29?displayProperty=nameWithType> e <xref:System.Net.HttpWebRequest.GetRequestStream%28System.Net.TransportContext%40%29?displayProperty=nameWithType> nella classe <xref:System.Net.HttpWebRequest>, che permettono il recupero di <xref:System.Net.TransportContext> e del token di associazione del canale con il metodo <xref:System.Net.TransportContext.GetChannelBinding%2A>.  
  
 L'SPN da usare per l'autenticazione integrata di Windows inviato da un'istanza <xref:System.Net.HttpWebRequest> a un servizio specifico può essere sostituito impostando la proprietà <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A>.  
  
 La proprietà <xref:System.Net.Mail.SmtpClient.TargetName%2A> può essere usata per impostare un SPN personalizzato da usare per l'autenticazione integrata di Windows per la connessione SMTP.  
  
## <a name="extended-protection-for-server-applications"></a>Protezione estesa per applicazioni server  
 <xref:System.Net.HttpListener> fornisce automaticamente i meccanismi per la convalida delle associazioni di servizi durante l'autenticazione HTTP.  
  
 Lo scenario più sicuro consiste nell'abilitare la protezione estesa per i prefissi HTTPS://. In questo caso, impostare <xref:System.Net.HttpListener.ExtendedProtectionPolicy%2A?displayProperty=nameWithType> su <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> con <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> impostato su <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported> o <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always> e <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> impostato su <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario.TransportSelected>. Il valore <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported> attiva la modalità parzialmente avanzata per <xref:System.Net.HttpListener>, mentre <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always> corrisponde alla modalità completamente avanzata.  
  
 Quando in questa configurazione viene effettuata una richiesta al server tramite un canale sicuro esterno, viene eseguita una query sul canale esterno per ottenere un'associazione di canali. Questa associazione di canali viene passata alle chiamate SSPI di autenticazione, che convalidano la corrispondenza dell'associazione di canali nel BLOB di autenticazione. I risultati possono essere tre:  
  
1. Il sistema operativo sottostante del server non supporta la protezione estesa. La richiesta non viene esposta all'applicazione e viene restituita una risposta di mancata autorizzazione (401) al client. Viene registrato un messaggio nell'origine di traccia <xref:System.Net.HttpListener> che specifica il motivo dell'errore.  
  
2. La chiamata SSPI non riesce, indicando che il client ha specificato un'associazione di canali che non corrisponde al valore previsto recuperato dal canale esterno oppure che il client non è riuscito a fornire l'associazione di canali quando sono stati configurati i criteri di protezione estesa nel server per <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always>. In entrambi i casi, la richiesta non viene esposta all'applicazione e viene restituita una risposta di mancata autorizzazione (401) al client. Viene registrato un messaggio nell'origine di traccia <xref:System.Net.HttpListener> che specifica il motivo dell'errore.  
  
3. Il client specifica l'associazione di canali corretta o viene autorizzato a connettersi senza specificare alcuna associazione, in quanto i criteri di protezione estesa nel server sono configurati con <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported>. La richiesta viene restituita all'applicazione per l'elaborazione. Non viene eseguito automaticamente alcun controllo del nome di servizio. Un'applicazione può scegliere di eseguire la propria convalida del nome di servizio usando la proprietà <xref:System.Net.HttpListenerRequest.ServiceName%2A>, ma in questo caso il controllo è superfluo.  
  
 Se un'applicazione effettua le proprie chiamate SSPI per eseguire l'autenticazione in base a BLOB scambiati all'interno del corpo di una richiesta HTTP e vuole supportare l'associazione di canali, deve recuperare l'associazione di canali prevista dal canale sicuro esterno usando <xref:System.Net.HttpListener> per passarla alla funzione [AcceptSecurityContext](/windows/win32/api/sspi/nf-sspi-acceptsecuritycontext) Win32 nativa. A questo scopo, usare la proprietà <xref:System.Net.HttpListenerRequest.TransportContext%2A> e chiamare il metodo <xref:System.Net.TransportContext.GetChannelBinding%2A> per recuperare il token di associazione del canale. Sono supportate solo le associazioni di endpoint. Se si specifica altro rispetto a <xref:System.Security.Authentication.ExtendedProtection.ChannelBindingKind.Endpoint>, viene generata un'eccezione <xref:System.NotSupportedException>. Se il sistema operativo sottostante <xref:System.Net.TransportContext.GetChannelBinding%2A> supporta l'associazione di canale, il metodo restituirà <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding> <xref:System.Runtime.InteropServices.SafeHandle> un ritorno a capo di un puntatore a un'associazione di canale adatta per passare alla funzione [AcceptSecurityContext](/windows/win32/api/sspi/nf-sspi-acceptsecuritycontext) come membro pvBuffer di una struttura SecBuffer passata nel `pInput` parametro. La proprietà <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding.Size%2A> contiene la lunghezza in byte dell'associazione di canali. Se il sistema operativo sottostante non supporta le associazioni di canali, la funzione restituisce `null`.  
  
 Un altro possibile scenario consiste nell'abilitare la protezione estesa per i prefissi HTTP:// quando non si usano proxy. In questo caso, impostare <xref:System.Net.HttpListener.ExtendedProtectionPolicy%2A?displayProperty=nameWithType> su <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> con <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> impostato su <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported> o <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always> e <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> impostato su <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario.TransportSelected>. Il valore <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported> attiva la modalità parzialmente avanzata per <xref:System.Net.HttpListener>, mentre <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always> corrisponde alla modalità completamente avanzata.  
  
 Viene creato un elenco predefinito dei nomi di servizio consentiti in base ai prefissi registrati con <xref:System.Net.HttpListener>. Questo elenco predefinito può essere esaminato tramite la proprietà <xref:System.Net.HttpListener.DefaultServiceNames%2A>. Se questo elenco non è completo, un'applicazione può specificare una raccolta di nomi di servizio personalizzata nel costruttore per la classe <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>, da usare al posto dell'elenco dei nomi di servizio predefinito.  
  
 Quando in questa configurazione viene effettuata una richiesta al server tramite un canale sicuro esterno, l'autenticazione procede normalmente senza alcun controllo dell'associazione di canali. Se l'autenticazione riesce, viene eseguita una query sul contesto per ottenere il nome di servizio fornito dal client e convalidato rispetto all'elenco dei nomi di servizio accettabili. I risultati possono essere quattro:  
  
1. Il sistema operativo sottostante del server non supporta la protezione estesa. La richiesta non viene esposta all'applicazione e viene restituita una risposta di mancata autorizzazione (401) al client. Viene registrato un messaggio nell'origine di traccia <xref:System.Net.HttpListener> che specifica il motivo dell'errore.  
  
2. Il sistema operativo sottostante del client non supporta la protezione estesa. Nella configurazione <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported> il tentativo di autenticazione riesce e la richiesta viene restituita all'applicazione. Nella configurazione <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always> il tentativo di autenticazione non riesce. La richiesta non viene esposta all'applicazione e viene restituita una risposta di mancata autorizzazione (401) al client. Viene registrato un messaggio nell'origine di traccia <xref:System.Net.HttpListener> che specifica il motivo dell'errore.  
  
3. Il sistema operativo sottostante del client supporta la protezione estesa, ma l'applicazione non ha specificato un'associazione di servizi. La richiesta non viene esposta all'applicazione e viene restituita una risposta di mancata autorizzazione (401) al client. Viene registrato un messaggio nell'origine di traccia <xref:System.Net.HttpListener> che specifica il motivo dell'errore.  
  
4. Il client ha specificato un'associazione di servizi. L'associazione di servizi viene confrontata con l'elenco delle associazioni consentite. Se corrisponde, la richiesta viene restituita all'applicazione. In caso contrario, la richiesta non viene esposta all'applicazione e viene automaticamente restituita una risposta di mancata autorizzazione (401) al client. Viene registrato un messaggio nell'origine di traccia <xref:System.Net.HttpListener> che specifica il motivo dell'errore.  
  
 Se questo semplice approccio tramite un elenco di nomi di servizio accettabili è insufficiente, un'applicazione può fornire la propria convalida del nome di servizio eseguendo una query sulla proprietà <xref:System.Net.HttpListenerRequest.ServiceName%2A>. Nei casi 1 e 2 descritti sopra la proprietà restituisce `null`. Nel caso 3 la proprietà restituisce una stringa vuota. Nel caso 4 viene restituito il nome di servizio specificato dal client.  
  
 Queste funzionalità di protezione estesa possono essere usate dalle applicazioni server anche per l'autenticazione con altri tipi di richieste e quando si usano proxy attendibili.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Authentication.ExtendedProtection>
- <xref:System.Security.Authentication.ExtendedProtection.Configuration>

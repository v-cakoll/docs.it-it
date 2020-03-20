---
title: Selezione e convalida dei certificati
ms.date: 03/30/2017
ms.assetid: c933aca2-4cd0-4ff1-9df9-267143f25a6f
ms.openlocfilehash: aea47360ab1bb9dad446a5a7b19a91ea688953c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048753"
---
# <a name="certificate-selection-and-validation"></a>Selezione e convalida dei certificati
Le classi <xref:System.Net> supportano diversi modi per selezionare e convalidare <xref:System.Security.Cryptography.X509Certificates> per le connessioni SSL (Secure Socket Layer). Un client può selezionare uno o più certificati per autenticarsi a un server, mentre un server può richiedere che un certificato client abbia uno o più attributi specifici per l'autenticazione.  
  
## <a name="definition"></a>Definizione  
 Un certificato è un flusso di byte ASCII che contiene una chiave pubblica, attributi (ad esempio, numero di versione, numero di serie e data di scadenza) e una firma digitale di un'autorità di certificazione. I certificati vengono usati per stabilire una connessione crittografata oppure per autenticare un client a un server.  
  
## <a name="client-certificate-selection-and-validation"></a>Selezione e convalida dei certificati client  
 Un client può selezionare uno o più certificati per una specifica connessione SSL. I certificati client possono essere associati alla connessione SSL a un server Web o a un server di posta elettronica SMTP. Un client aggiunge i certificati a una raccolta di oggetti della classe <xref:System.Security.Cryptography.X509Certificates.X509Certificate> o <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>. Per la posta elettronica, ad esempio, la raccolta di certificati è un'istanza di <xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection> associata alla proprietà <xref:System.Net.Mail.SmtpClient.ClientCertificates%2A> della classe <xref:System.Net.Mail.SmtpClient>. La classe <xref:System.Net.HttpWebRequest> ha una proprietà <xref:System.Net.HttpWebRequest.ClientCertificates%2A> simile.  
  
 La differenza principale tra la classe <xref:System.Security.Cryptography.X509Certificates.X509Certificate> e la classe <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> è data dal fatto che la chiave privata deve trovarsi nell'archivio certificati per la classe <xref:System.Security.Cryptography.X509Certificates.X509Certificate>.  
  
 Anche se i certificati vengono aggiunti a una raccolta e sono associati a una connessione SSL specifica, nessun certificato verrà inviato al server a meno che non sia richiesto dal server. Se su una connessione sono impostati più certificati client, verrà usato il migliore in base a un algoritmo che valuta la corrispondenza tra l'elenco di autorità di certificazione fornito dal server e il nome dell'autorità emittente del certificato client.  
  
 La classe <xref:System.Net.Security.SslStream> fornisce anche maggiore controllo sull'handshake SSL. Un client può specificare un delegato per selezionare il certificato client da usare.  
  
 Un server remoto può verificare se un certificato client è valido, corrente e firmato dall'autorità di certificazione appropriata. È possibile aggiungere un delegato alla proprietà <xref:System.Net.ServicePointManager.ServerCertificateValidationCallback%2A> per imporre la convalida dei certificati.  
  
## <a name="client-certificate-selection"></a>Selezione del certificato client  
 In .NET Framework viene usata la procedura seguente per selezionare il certificato client da presentare al server:  
  
1. Un certificato già presentato al server viene memorizzato nella cache alla prima presentazione e quindi riusato per le successive richieste di certificato client.  
  
2. Se è presente un delegato, usare sempre il risultato restituito dal delegato come certificato client da selezionare. Provare a usare un certificato memorizzato nella cache, quando possibile, ma non usare credenziali anonime memorizzate nella cache se il delegato ha restituito null e la raccolta di certificati non è vuota.  
  
3. Se si tratta della prima verifica di un certificato client, .NET Framework enumera i certificati negli oggetti della classe <xref:System.Security.Cryptography.X509Certificates.X509Certificate> o <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> associati alla connessione, cercando una corrispondenza tra l'elenco di autorità di certificazione fornito dal server e il nome dell'autorità emittente del certificato client. Il primo certificato corrispondente viene inviato al server. Se non viene trovata alcuna corrispondenza o la raccolta di certificati è vuota, al server vengono inviate credenziali anonime.  
  
## <a name="tools-for-certificate-configuration"></a>Strumenti per la configurazione dei certificati  
 Per la configurazione dei certificati client e server è disponibile una serie di strumenti.  
  
 Per configurare i certificati client è possibile usare *Winhttpcertcfg.exe*. Lo strumento *Winhttpcertcfg.exe* è incluso in Windows Server 2003 Resource Kit ed è anche disponibile come download in Windows Server 2003 Resource Kit Tools sul sito [www.microsoft.com](https://www.microsoft.com).  
  
Lo strumento *HttpCfg.exe* può essere utilizzato <xref:System.Net.HttpListener> per configurare i certificati server per la classe. Lo strumento *HttpCfg.exe* è incluso tra gli strumenti di supporto per Windows Server 2003 e Windows XP Service Pack 2. *HttpCfg.exe* e gli altri strumenti di supporto non vengono installati per impostazione predefinita in Windows Server 2003 o Windows XP. Per Windows Server 2003 gli strumenti di supporto vengono installati separatamente dalla cartella e dal file seguenti sul CD del sistema operativo:  
  
 \Support\Tools\Suptools.msi  
  
 Per Windows XP Service Pack 2, gli strumenti di supporto di Windows XP sono disponibili come download sul sito [www.microsoft.com](https://www.microsoft.com).  
  
 Il codice sorgente di una versione di *HttpCfg.exe* è inoltre disponibile come esempio in Windows Server SDK. Il codice sorgente dell'esempio *HttpCfg.exe* viene installato per impostazione predefinita con gli esempi di rete, come parte di Windows SDK, nella cartella seguente:  
  
 *C:\Programmi\Microsoft SDKs\Windows\v1.0\Samples\NetDS\http\serviceconfig*  
  
 Oltre a questi strumenti, le classi <xref:System.Security.Cryptography.X509Certificates.X509Certificate> e <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> offrono metodi per caricare un certificato dal file system.  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza nella programmazione di rete](security-in-network-programming.md)
- [Programmazione di rete in .NET Framework](index.md)

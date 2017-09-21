---
title: Informazioni su problemi ed eccezioni di WebRequest
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 74a361a5-e912-42d3-8f2e-8e9a96880a2b
caps.latest.revision: 6
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 918528e99396bd71f8c44dadcef7f6dfa6a7a47e
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="understanding-webrequest-problems-and-exceptions"></a>Informazioni su problemi ed eccezioni di WebRequest
<xref:System.Net.WebRequest> e le relative classi derivate (<xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, e <xref:System.Net.FileWebRequest>) generano eccezioni per segnalare una condizione anomala. In alcuni casi la risoluzione di questi problemi non è scontata.  
  
## <a name="solutions"></a>Soluzioni  
 Esaminare la proprietà <xref:System.Net.WebException.Status%2A> di <xref:System.Net.WebException> per determinare il problema. La tabella seguente illustra i diversi valori di stato e alcune possibili soluzioni.  
  
|Status|Dettagli|Soluzione|  
|------------|-------------|--------------|  
|<xref:System.Net.WebExceptionStatus.SendFailure><br /><br /> -oppure-<br /><br /> <xref:System.Net.WebExceptionStatus.ReceiveFailure>|Si è verificato un problema con il socket sottostante. La connessione potrebbe essere stata reimpostata.|Riconnettersi e inviare nuovamente la richiesta.<br /><br /> Verificare che sia installato il Service Pack più recente.<br /><br /> Aumentare il valore della proprietà <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A?displayProperty=fullName>.<br /><br /> Impostare <xref:System.Net.HttpWebRequest.KeepAlive%2A?displayProperty=fullName> su `false`.<br /><br /> Aumentare il numero massimo di connessioni con la proprietà <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A>.<br /><br /> Controllare la configurazione del proxy.<br /><br /> Se si usa SSL, verificare che il processo server disponga dell'autorizzazione per accedere all'archivio certificati.<br /><br /> Per l'invio di una grande quantità di dati, impostare <xref:System.Net.HttpWebRequest.AllowWriteStreamBuffering%2A> su `false`.|  
|<xref:System.Net.WebExceptionStatus.TrustFailure>|Impossibile convalidare il certificato del server.|Provare ad aprire l'URI con Internet Explorer. Risolvere eventuali avvisi di sicurezza visualizzati da Internet Explorer. Se non è possibile risolvere l'avviso di sicurezza, è possibile creare una classe dei criteri dei certificati che implementa <xref:System.Net.ICertificatePolicy> che restituisce `true` e passarla a <xref:System.Net.ServicePointManager.CertificatePolicy%2A>.<br /><br /> Fare riferimento a [http://support.microsoft.com/?id=823177](http://go.microsoft.com/fwlink/?LinkID=179653).<br /><br /> Assicurarsi che il certificato dell'Autorità di certificazione che ha firmato il certificato del server venga aggiunto all'elenco delle autorità di certificazione attendibili in Internet Explorer.<br /><br /> Assicurarsi che il nome host nell'URL corrisponda al nome comune nel certificato del server.|  
|<xref:System.Net.WebExceptionStatus.SecureChannelFailure>|Si è verificato un errore nella transazione SSL o è presente un problema con il certificato.|.NET Framework versione 1.1 supporta solo SSL versione 3.0. Se il server usa solo TLS versione 1.0 o SSL versione 2.0, viene generata l'eccezione. Eseguire l'aggiornamento a .NET Framework versione 2.0 e impostare <xref:System.Net.ServicePointManager.SecurityProtocol%2A> in modo che corrisponda al server.<br /><br /> Il certificato client è stato firmato da un'Autorità di certificazione (CA) non attendibile per il server. Installare il certificato della CA nel server. Vedere [http://support.microsoft.com/?id=332077](http://go.microsoft.com/fwlink/?LinkID=179654).<br /><br /> Assicurarsi di avere installato il Service Pack più recente.|  
|<xref:System.Net.WebExceptionStatus.ConnectFailure>|Connessione non riuscita.|La connessione è bloccata da un firewall o proxy. Modificare il firewall o proxy per consentire la connessione.<br /><br /> Impostare in modo esplicito un <xref:System.Net.WebProxy> nell'applicazione client chiamando il costruttore <xref:System.Net.WebProxy> (WebServiceProxyClass.Proxy = new WebProxy([http://server:80](http://server/), true)).<br /><br /> Eseguire Filemon o Regmon per assicurarsi che l'identità del processo di lavoro disponga delle autorizzazioni necessarie per accedere a WSPWSP.dll, HKLM\System\CurrentControlSet\Services\DnsCache o HKLM\System\CurrentControlSet\Services\WinSock2.|  
|<xref:System.Net.WebExceptionStatus.NameResolutionFailure>|Il servizio DNS (Domain Name Service) non è riuscito a risolvere il nome host.|Configurare il proxy in modo corretto. Vedere [http://support.microsoft.com/?id=318140](http://go.microsoft.com/fwlink/?LinkID=179655).<br /><br /> Assicurarsi che il software antivirus installato o il firewall non blocchi la connessione.|  
|<xref:System.Net.WebExceptionStatus.RequestCanceled>|È stato chiamato <xref:System.Net.WebRequest.Abort%2A> o si è verificato un errore.|Questo problema potrebbe essere causato da un carico eccessivo sul client o sul server. Ridurre il carico.<br /><br /> Aumentare l'impostazione <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A>.<br /><br /> Vedere [http://support.microsoft.com/?id=821268](http://go.microsoft.com/fwlink/?LinkID=179656) per modificare le impostazioni delle prestazioni del servizio Web.|  
|<xref:System.Net.WebExceptionStatus.ConnectionClosed>|L'applicazione ha tentato di scrivere in un socket già chiuso.|Il client o il server è sovraccarico. Ridurre il carico.<br /><br /> Aumentare l'impostazione <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A>.<br /><br /> Vedere [http://support.microsoft.com/?id=821268](http://go.microsoft.com/fwlink/?LinkID=179656) per modificare le impostazioni delle prestazioni del servizio Web.|  
|<xref:System.Net.WebExceptionStatus.MessageLengthLimitExceeded>|È stato superato il limite impostato (<xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>) per la lunghezza del messaggio.|Aumentare il valore della proprietà <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>.|  
|<xref:System.Net.WebExceptionStatus.ProxyNameResolutionFailure>|Il servizio DNS (Domain Name Service) non è riuscito a risolvere il nome host del proxy.|Configurare il proxy in modo corretto. Vedere [http://support.microsoft.com/?id=318140](http://go.microsoft.com/fwlink/?LinkID=179655).<br /><br /> Forzare <xref:System.Net.HttpWebRequest> a non usare alcun proxy impostando la proprietà <xref:System.Net.HttpWebRequest.Proxy%2A> su `null`.|  
|<xref:System.Net.WebExceptionStatus.ServerProtocolViolation>|La risposta dal server non è una risposta HTTP valida. Questo problema si verifica quando .NET Framework rileva che la risposta del server non è conforme alla specifica RFC per HTTP 1.1. Questo problema può verificarsi quando la risposta contiene intestazioni non corrette o delimitatori dell'intestazione non corretti. Il documento RFC 2616 definisce HTTP 1.1 e il formato valido per la risposta dal server. Per altre informazioni, vedere [http://www.ietf.org](http://go.microsoft.com/fwlink/?LinkID=147388).|Ottenere una traccia di rete della transazione ed esaminare le intestazioni nella risposta.<br /><br /> Se l'applicazione richiede la risposta del server senza analisi (potrebbe rappresentare un problema per la sicurezza), impostare `useUnsafeHeaderParsing` su `true` nel file di configurazione. Vedere [Elemento \<httpWebRequest> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md).|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Net.HttpWebRequest>   
 <xref:System.Net.HttpWebResponse>   
 <xref:System.Net.Dns>


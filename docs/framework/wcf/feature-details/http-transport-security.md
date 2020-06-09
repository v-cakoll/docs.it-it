---
title: Protezione del trasporto HTTP
ms.date: 03/30/2017
ms.assetid: d3439262-c58e-4d30-9f2b-a160170582bb
ms.openlocfilehash: 28d0ac164022f585f25b44b16c68994b592ef041
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592723"
---
# <a name="http-transport-security"></a>Protezione del trasporto HTTP
Quando si usa HTTP come trasporto, la protezione viene fornita da un'implementazione SSL (Secure Sockets Layer). SSL viene ampiamente usato in Internet per autenticare un servizio presso un client e quindi garantire la riservatezza (crittografia) sul canale. In questo argomento viene illustrato il funzionamento di SSL e il modo in cui viene implementato in Windows Communication Foundation (WCF).  
  
## <a name="basic-ssl"></a>SSL di base  
 Per illustrare la modalità di funzionamento di SSL è preferibile usare uno scenario tipico, in questo caso il sito Web di una banca. Il sito consente a un cliente di accedere al sistema con un nome utente e una password. Dopo l'autenticazione, l'utente può eseguire transazioni, come, ad esempio, visualizzare i saldi dei conti, pagare bollette e spostare denaro da un conto all'altro.  
  
 Quando un utente visita il sito per la prima volta, il meccanismo SSL avvia una serie di negoziazioni, denominate *handshake*, con il client dell'utente (in questo caso Internet Explorer). SSL prima autentica il sito della banca presso il cliente. Questo è un passaggio essenziale, perché i clienti devono innanzitutto sapere che stanno comunicando con il sito effettivo e non sono invece vittime di una truffa mirata far digitare loro nome utente e password. SSL esegue questa autenticazione usando un certificato SSL fornito da un'autorità attendibile, ad esempio VeriSign. La logica è la seguente: VeriSign attesta l'identità del sito della banca. Poiché Internet Explorer considera VeriSign attendibile, il sito viene a sua volta considerato attendibile. Se si desidera eseguire il controllo con VeriSign, è possibile fare clic sul logo VeriSign. Verrà visualizzata una dichiarazione di autenticità con la data di scadenza e il nome dell'organizzazione a cui è stato rilasciato il certificato, ovvero il sito della banca.  
  
 Per avviare una sessione protetta, il client invia l'equivalente di un "ciao" al server, insieme a un elenco di algoritmi di crittografia usabili per apporre firme, generare hash e procedere a operazioni di crittografia e decrittografia. In risposta, il sito restituisce un riconoscimento e indica il gruppo di algoritmi scelto. Durante questo handshake iniziale, entrambe le parti inviano e ricevono parametri nonce. Un *parametro nonce* è un pezzo di dati generato in modo casuale che viene usato, in combinazione con la chiave pubblica del sito, per creare un hash. Un *hash* è un nuovo numero derivato dai due numeri usando un algoritmo standard, ad esempio SHA1. Anche il client e il sito scambiano messaggi per accettare l'algoritmo hash da usare. L'hash è univoco e viene usato solo per la sessione tra il client e il sito per crittografare e decrittografare i messaggi. Sia il client che il servizio dispongono del parametro nonce originale e della chiave pubblica del certificato, pertanto entrambi i lati possono generare lo stesso hash. Il client convalida quindi l'hash inviato dal servizio (a) usando l'algoritmo concordato per calcolare l'hash dai dati e (b) confrontandolo con l'hash inviato dal servizio; se i due numeri corrispondono, il client ha la garanzia che l'hash non è stato manomesso. Il client può quindi usare l'hash come chiave per crittografare un messaggio che contiene ancora un altro hash nuovo. Il servizio può decrittografare il messaggio usando l'hash e recuperare questo terzultimo hash. Le informazioni accumulate (parametri nonce, chiave pubblica e altri dati) sono ora conosciute su entrambi i lati e può essere creato un hash finale (o chiave master). Questa chiave finale viene inviata in forma crittografata usando il penultimo hash. La chiave master viene quindi utilizzata per crittografare e decrittografare i messaggi per il resto della sessione. Poiché sia il client che il servizio utilizzano la stessa chiave, questa viene anche chiamata *chiave di sessione*.  
  
 La chiave di sessione viene definita anche chiave simmetrica o "segreto condiviso". Disporre di una chiave simmetrica è importante perché riduce i calcoli richiesti da entrambi lati della transazione. Se ogni messaggio richiedesse un nuovo scambio di parametri nonce e hash, le prestazioni peggiorerebbero. L'obiettivo finale di SSL è pertanto quello di usare una chiave simmetrica che consenta ai messaggi di passare liberamente da un lato all'altro con un maggiore grado di sicurezza ed efficienza.  
  
 La descrizione precedente è una versione semplificata di ciò che accade, poiché il protocollo può variare da sito a sito. È inoltre possibile che sia il client che il sito generino parametri nonce non combinati in modo algoritmico durante l'handshake, per aggiungere maggiore complessità, e di conseguenza protezione, al processo di scambio dei dati.  
  
### <a name="certificates-and-public-key-infrastructure"></a>Certificati e infrastruttura a chiave pubblica  
 Durante l'handshake, il servizio invia anche il proprio certificato SSL al client. Il certificato contiene informazioni quali la data di scadenza, l'autorità emittente e l'URI (Uniform Resource Identifier) del sito. Il client confronta questo URI con l'URI che aveva originariamente contattato, per assicurarsi che corrispondano, e controlla anche la data e l'autorità emittente.  
  
 Ogni certificato ha due chiavi, una chiave privata e una chiave pubblica e le due sono note come coppia di *chiavi di scambio*. In breve, la chiave privata è nota solo al proprietario del certificato, mentre quella pubblica è leggibile dal certificato. Ognuna delle due chiavi può essere usata per crittografare o decrittografare digest, hash o altre chiavi, ma solo in operazioni contrarie. Ad esempio, se il client esegue la crittografia con la chiave pubblica, solo il sito può decrittografare il messaggio usando la chiave privata. Allo stesso modo, se il sito esegue la crittografia con la chiave privata, il client può procedere alla decrittografia con la chiave pubblica. Questo fornisce al client l'assicurazione che i messaggi vengono scambiati solo con il possessore della chiave privata, poiché solo i messaggi crittografati con la chiave privata possono essere decrittografati con la chiave pubblica. Il sito riceve l'assicurazione che sta scambiando messaggi con un client che ha eseguito la crittografia usando la chiave pubblica. Tuttavia, questo scambio è protetto solo per un handshake iniziale, motivo per cui è essenziale creare l'effettiva chiave simmetrica. Ciononostante, tutte le comunicazioni dipendono dal servizio che dispone di un certificato SSL valido.  
  
## <a name="implementing-ssl-with-wcf"></a>Implementazione di SSL con WCF  
 La sicurezza del trasporto HTTP (o SSL) viene fornita esternamente a WCF. È possibile implementare SSL in due modi; il fattore decisivo dipende dalla modalità di host dell'applicazione:  
  
- Se si utilizza Internet Information Services (IIS) come host WCF, utilizzare l'infrastruttura IIS per configurare un servizio SSL.  
  
- Se si sta creando un'applicazione WCF indipendente, è possibile associare un certificato SSL all'indirizzo utilizzando lo strumento HttpCfg. exe.  
  
### <a name="using-iis-for-transport-security"></a>Uso di IIS per la protezione del trasporto  
  
#### <a name="iis-70"></a>IIS 7.0  
 Per configurare IIS 7,0 come host sicuro (tramite SSL), vedere la pagina relativa alla [configurazione di Secure Sockets Layer in iis 7,0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10)).  
  
Per configurare i certificati per l'utilizzo con IIS 7,0, vedere [Configuring Server Certificates in iis 7,0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732230(v=ws.10)).  
  
#### <a name="iis-60"></a>IIS 6.0  
 Per configurare IIS 6,0 come host sicuro (tramite SSL), vedere [configurazione Secure Sockets Layer](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc736992(v=ws.10)).  
  
 Per configurare i certificati per l'utilizzo con IIS 6,0, vedere [Certificates_IIS_SP1_Ops](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc757474(v=ws.10)).  
  
### <a name="using-httpcfg-for-ssl"></a>Uso di HttpCfg per SSL  

 Se si sta creando un'applicazione WCF indipendente, usare lo strumento [HttpCfg. exe](/windows/win32/http/httpcfg-exe) .
  
 Per ulteriori informazioni sull'utilizzo dello strumento HttpCfg. exe per configurare una porta con un certificato X. 509, vedere [procedura: configurare una porta con un certificato SSL](how-to-configure-a-port-with-an-ssl-certificate.md).  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza del trasporto](transport-security.md)
- [Sicurezza dei messaggi](message-security-in-wcf.md)

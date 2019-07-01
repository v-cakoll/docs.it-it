---
title: Protezione del trasporto HTTP
ms.date: 03/30/2017
ms.assetid: d3439262-c58e-4d30-9f2b-a160170582bb
ms.openlocfilehash: 456df42848c009dcf42022ac674a1d27e5b33972
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487026"
---
# <a name="http-transport-security"></a>Protezione del trasporto HTTP
Quando si usa HTTP come trasporto, la protezione viene fornita da un'implementazione SSL (Secure Sockets Layer). SSL viene ampiamente usato in Internet per autenticare un servizio presso un client e quindi garantire la riservatezza (crittografia) sul canale. Questo argomento viene illustrato come funziona SSL e come implementarlo in Windows Communication Foundation (WCF).  
  
## <a name="basic-ssl"></a>SSL di base  
 Per illustrare la modalità di funzionamento di SSL è preferibile usare uno scenario tipico, in questo caso il sito Web di una banca. Il sito consente a un cliente di accedere al sistema con un nome utente e una password. Dopo l'autenticazione, l'utente può eseguire transazioni, come, ad esempio, visualizzare i saldi dei conti, pagare bollette e spostare denaro da un conto all'altro.  
  
 Quando un utente visita prima di tutto il sito, il meccanismo SSL avvia una serie di negoziazioni, chiamate una *handshake*, con il client dell'utente (in questo caso, Internet Explorer). SSL prima autentica il sito della banca presso il cliente. Questo è un passaggio essenziale, perché i clienti devono innanzitutto sapere che stanno comunicando con il sito effettivo e non sono invece vittime di una truffa mirata far digitare loro nome utente e password. SSL esegue questa autenticazione usando un certificato SSL fornito da un'autorità attendibile, ad esempio VeriSign. La logica proseguirebbe simile al seguente: VeriSign attesta l'identità del sito della banca. Poiché Internet Explorer considera VeriSign attendibile, il sito viene a sua volta considerato attendibile. Se si desidera eseguire il controllo con VeriSign, è possibile fare clic sul logo VeriSign. Verrà visualizzata una dichiarazione di autenticità con la data di scadenza e il nome dell'organizzazione a cui è stato rilasciato il certificato, ovvero il sito della banca.  
  
 Per avviare una sessione protetta, il client invia l'equivalente di un "ciao" al server, insieme a un elenco di algoritmi di crittografia usabili per apporre firme, generare hash e procedere a operazioni di crittografia e decrittografia. In risposta, il sito restituisce un riconoscimento e indica il gruppo di algoritmi scelto. Durante questo handshake iniziale, entrambe le parti inviano e ricevono parametri nonce. Oggetto *nonce* è un dato generato casualmente che viene utilizzata, in combinazione con la chiave pubblica del sito, per creare un hash. Oggetto *hash* è un nuovo numero derivato da due numeri tramite un algoritmo standard quale SHA1. Il client e il sito si scambiano anche messaggi, per concordare l'algoritmo hash da usare. L'hash è univoco e viene usato solo per la sessione tra il client e il sito, per crittografare e decrittografare messaggi. Sia il client che il servizio dispongono del parametro nonce originale e della chiave pubblica del certificato, pertanto entrambi i lati possono generare lo stesso hash. Il client convalida quindi l'hash inviato dal servizio (a) usando l'algoritmo concordato per calcolare l'hash dai dati e (b) confrontandolo con l'hash inviato dal servizio; se i due numeri corrispondono, il client ha la garanzia che l'hash non è stato manomesso. Il client può quindi usare l'hash come chiave per crittografare un messaggio che contiene ancora un altro hash nuovo. Il servizio può decrittografare il messaggio usando l'hash e recuperare questo terzultimo hash. Le informazioni accumulate (parametri nonce, chiave pubblica e altri dati) sono ora conosciute su entrambi i lati e può essere creato un hash finale (o chiave master). Questa chiave finale viene inviata in forma crittografata usando il penultimo hash. La chiave master viene quindi usata per crittografare e decrittografare i messaggi per il resto della sessione. Poiché i client e il servizio utilizzano la stessa chiave, detta anche un *chiave di sessione*.  
  
 La chiave di sessione viene definita anche chiave simmetrica o "segreto condiviso". Disporre di una chiave simmetrica è importante perché riduce i calcoli richiesti da entrambi lati della transazione. Se ogni messaggio richiedesse un nuovo scambio di parametri nonce e hash, le prestazioni peggiorerebbero. L'obiettivo finale di SSL è pertanto quello di usare una chiave simmetrica che consenta ai messaggi di passare liberamente da un lato all'altro con un maggiore grado di sicurezza ed efficienza.  
  
 La descrizione precedente è una versione semplificata di ciò che accade, poiché il protocollo può variare da sito a sito. È inoltre possibile che sia il client che il sito generino parametri nonce non combinati in modo algoritmico durante l'handshake, per aggiungere maggiore complessità, e di conseguenza protezione, al processo di scambio dei dati.  
  
### <a name="certificates-and-public-key-infrastructure"></a>Certificati e infrastruttura a chiave pubblica  
 Durante l'handshake, il servizio invia anche il proprio certificato SSL al client. Il certificato contiene informazioni quali la data di scadenza, l'autorità emittente e l'URI (Uniform Resource Identifier) del sito. Il client confronta questo URI con l'URI che aveva originariamente contattato, per assicurarsi che corrispondano, e controlla anche la data e l'autorità emittente.  
  
 Ogni certificato ha due chiavi, una chiave privata e una chiave pubblica e due sono note come un *scambiare coppia di chiavi*. In breve, la chiave privata è nota solo al proprietario del certificato, mentre quella pubblica è leggibile dal certificato. Ognuna delle due chiavi può essere usata per crittografare o decrittografare digest, hash o altre chiavi, ma solo in operazioni contrarie. Ad esempio, se il client esegue la crittografia con la chiave pubblica, solo il sito può decrittografare il messaggio usando la chiave privata. Allo stesso modo, se il sito esegue la crittografia con la chiave privata, il client può procedere alla decrittografia con la chiave pubblica. Questo fornisce al client l'assicurazione che i messaggi vengono scambiati solo con il possessore della chiave privata, poiché solo i messaggi crittografati con la chiave privata possono essere decrittografati con la chiave pubblica. Il sito riceve l'assicurazione che sta scambiando messaggi con un client che ha eseguito la crittografia usando la chiave pubblica. Tuttavia, questo scambio è protetto solo per un handshake iniziale, motivo per cui è essenziale creare l'effettiva chiave simmetrica. Ciononostante, tutte le comunicazioni dipendono dal servizio che dispone di un certificato SSL valido.  
  
## <a name="implementing-ssl-with-wcf"></a>Implementazione di SSL con WCF  
 Sicurezza del trasporto HTTP (o SSL) viene fornito esternamente a WCF. È possibile implementare SSL in due modi; il fattore decisivo dipende dalla modalità di host dell'applicazione:  
  
- Se si usa Internet Information Services (IIS) dell'host WCF, usare l'infrastruttura IIS per configurare un servizio SSL.  
  
- Se si sta creando un'applicazione WCF self-hosted, è possibile associare un certificato SSL all'indirizzo usando lo strumento HttpCfg.exe.  
  
### <a name="using-iis-for-transport-security"></a>Uso di IIS per la protezione del trasporto  
  
#### <a name="iis-70"></a>IIS 7.0  
 Per configurare IIS 7.0 come host sicuro (con SSL), vedere [configurazione di Secure Sockets Layer in IIS 7.0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10)).  
  
Per configurare certificati per l'uso con IIS 7.0, vedere [configurazione dei certificati del Server in IIS 7.0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732230(v=ws.10)).  
  
#### <a name="iis-60"></a>IIS 6.0  
 Per configurare IIS 6.0 come host sicuro (con SSL), vedere [configurazione di Secure Sockets Layer](https://go.microsoft.com/fwlink/?LinkId=88601).  
  
 Per configurare certificati per l'uso con IIS 6.0, vedere [Certificates_IIS_SP1_Ops](https://go.microsoft.com/fwlink/?LinkId=88602).  
  
### <a name="using-httpcfg-for-ssl"></a>Uso di HttpCfg per SSL  
 Se si sta creando un'applicazione WCF self-hosted, scaricare lo strumento HttpCfg.exe, disponibile all'indirizzo il [sito di supporto per strumenti di Windows XP Service Pack 2](https://go.microsoft.com/fwlink/?LinkId=29002).  
  
 Per altre informazioni sull'uso dello strumento HttpCfg.exe per configurare una porta con un certificato X.509, vedere [come: Configurare una porta con un certificato SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza del trasporto](../../../../docs/framework/wcf/feature-details/transport-security.md)
- [Sicurezza dei messaggi](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)

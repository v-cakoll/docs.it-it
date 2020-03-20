---
title: Introduzione ai protocolli di collegamento
ms.date: 03/30/2017
helpviewer_keywords:
- data requests, pluggable protocols
- WebRequest class, pluggable protocols
- response to Internet request, pluggable protocols
- URI
- Windows Sockets
- request/response model
- sending data, pluggable protocols
- pluggable protocols
- WebClient class, about WebClient class
- pluggable protocols, about pluggable protocols
- Internet, pluggable protocols
- path identifiers
- Uniform Resource Identifier
- application development [.NET Framework], pluggable protocols
- requesting data from Internet, pluggable protocols
- receiving data, pluggable protocols
- protocols, pluggable
- server identifiers
- scheme identifiers
ms.assetid: 4b48e22d-e4e5-48f0-be80-d549bda97415
ms.openlocfilehash: 72b47b8159f9f6f0dc3a19c5cbf94335507d9e7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047870"
---
# <a name="introducing-pluggable-protocols"></a>Introduzione ai protocolli di collegamento
Microsoft .NET Framework offre un'implementazione a livelli, estendibile e gestita di servizi Internet che possono essere integrati rapidamente e facilmente nelle applicazioni. Le classi di accesso a Internet negli spazi dei nomi <xref:System.Net> e <xref:System.Net.Sockets> possono essere usate per implementare applicazioni basate sul Web e basate su Internet.  
  
## <a name="internet-applications"></a>Applicazioni Internet  
 Le applicazioni Internet possono essere classificate in due tipi generali: applicazioni client che richiedono informazioni e applicazioni server che rispondono alle richieste di informazioni dai client. La classica applicazione client-server Internet è il World Wide Web, in cui gli utenti usano i browser per accedere a documenti e ad altri dati archiviati in server Web in tutto il mondo.  
  
 Le applicazioni non si limitano solo a uno di questi ruoli. Ad esempio, il comune server applicazioni di livello intermedio risponde alle richieste dei client richiedendo dati a un altro server, caso in cui agisce sia come server sia come client.  
  
 L'applicazione client effettua una richiesta identificando la risorsa Internet richiesta e il protocollo di comunicazione da usare per la richiesta e la risposta. Se necessario, il client fornisce anche tutti i dati aggiuntivi necessari per completare la richiesta, come la posizione del proxy o le informazioni di autenticazione (nome utente, password e così via). Una volta creata, la richiesta può essere inviata al server.  
  
## <a name="identifying-resources"></a>Identificazione delle risorse  
 .NET Framework usa un URI (Uniform Resource Identifier) per identificare la risorsa Internet richiesta e il protocollo di comunicazione. L'URI è costituito da almeno tre, possibilmente quattro, parti: l'identificatore dello schema, che identifica il protocollo di comunicazione per la richiesta e la risposta, l'identificatore del server, costituito da un nome host DNS (Domain Name System) o un indirizzo TCP che identifica in modo univoco il server in Internet, l'identificatore del percorso, che individua le informazioni richieste nel server e una stringa di query facoltativa, che passa informazioni dal client al server. Ad esempio, l'URI `http://www.contoso.com/whatsnew.aspx?date=today` è costituito dall'identificatore dello schema `http`, dall'identificatore del server `www.contoso.com`, dal percorso `/whatsnew.aspx` e dalla stringa di query `?date=today`.  
  
 Dopo che il server ha ricevuto la richiesta e ha elaborato la risposta, restituisce la risposta all'applicazione client. La risposta include informazioni supplementari, tra cui il tipo di contenuto (ad esempio, testo non elaborato o dati XLM).  
  
## <a name="requests-and-responses-in-the-net-framework"></a>Richieste e risposte in .NET Framework  
 .NET Framework usa classi specifiche per fornire le tre informazioni necessarie per accedere alle risorse Internet tramite un modello di richiesta/risposta: la classe <xref:System.Uri>, che contiene l'URI della risorsa Internet desiderata, la classe <xref:System.Net.WebRequest>, che contiene una richiesta della risorsa e infine la classe <xref:System.Net.WebResponse>, che fornisce un contenitore per la risposta in arrivo.  
  
 Le applicazioni client creano istanze `WebRequest` passando l'URI della risorsa di rete al metodo <xref:System.Net.WebRequest.Create%2A>. Questo metodo statico crea una classe `WebRequest` per un protocollo specifico, ad esempio HTTP. La classe `WebRequest` restituita fornisce l'accesso alle proprietà che controllano sia la richiesta al server sia l'accesso al flusso di dati inviato quando viene effettuata la richiesta. Il metodo <xref:System.Net.WebRequest.GetResponse%2A> in `WebRequest` invia la richiesta dall'applicazione client al server identificato nell'URI. Nei casi in cui la risposta può arrivare in ritardo, la richiesta può essere effettuata in modo asincrono usando il metodo <xref:System.Net.WebRequest.BeginGetResponse%2A> in **WebRequest** e la risposta può essere restituita in un secondo momento usando il metodo <xref:System.Net.WebRequest.EndGetResponse%2A>.  
  
 I metodi **GetResponse** e **EndGetResponse** restituiscono una classe **WebResponse** che fornisce l'accesso ai dati restituiti dal server. Poiché questi dati vengono forniti all'applicazione richiedente come flusso dal metodo <xref:System.Net.WebResponse.GetResponseStream%2A>, possono essere usati in un'applicazione ovunque vengono usati i flussi di dati.  
  
 Le classi **WebRequest** e **WebResponse** sono alla base dei protocolli di collegamento, un'implementazione di servizi di rete che permette di sviluppare applicazioni che usano risorse Internet senza doversi preoccupare dei dettagli specifici del protocollo usato da ogni risorsa. Le classi discendenti di **WebRequest** vengono registrate con la classe **WebRequest** per gestire i dettagli dell'esecuzione delle effettive connessioni alle risorse Internet.  
  
 Ad esempio, la classe <xref:System.Net.HttpWebRequest> gestisce i dettagli della connessione a una risorsa Internet tramite HTTP. Per impostazione predefinita, quando il metodo **WebRequest.Create** rileva un URI che inizia con "http:" o "https:" (identificatori di protocollo per HTTP e HTTP sicuro), la classe **WebRequest** restituita può essere usata così com'è oppure è possibile eseguirne il cast di tipo a **HttpWebRequest** per accedere a proprietà specifiche del protocollo. Nella maggior parte dei casi, **WebRequest** fornisce tutte le informazioni necessarie per effettuare una richiesta.  
  
 Qualsiasi protocollo che può essere rappresentato come transazione di richiesta/risposta può essere usato in una classe **WebRequest**. È possibile derivare le classi specifiche del protocollo da **WebRequest** e **WebResponse** e quindi registrarle perché vengano usate dall'applicazione con il metodo <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType> statico.  
  
 Quando è necessaria l'autorizzazione client per le richieste Internet, la proprietà <xref:System.Net.WebRequest.Credentials%2A> di **WebRequest** fornisce le credenziali necessarie. Queste credenziali possono essere una semplice coppia nome/password per l'autenticazione digest o HTTP di base o un set nome/password/dominio per l'autenticazione NTLM o Kerberos. Un set di credenziali può essere archiviato in un'istanza <xref:System.Net.NetworkCredential>, mentre più set di credenziali possono essere archiviati contemporaneamente in un'istanza <xref:System.Net.CredentialCache>. **CredentialCache** usa l'URI della richiesta e lo schema di autenticazione supportato dal server per determinare quali credenziali inviare al server.  
  
## <a name="simple-requests-with-webclient"></a>Richieste semplici con WebClient  
 Per le applicazioni che devono effettuare richieste semplici di risorse Internet, la classe <xref:System.Net.WebClient> fornisce metodi comuni per il caricamento o il download dei dati in o da un server Internet. **WebClient** si basa sulla classe **WebRequest** per fornire l'accesso alle risorse Internet e di conseguenza la classe **WebClient** può usare qualsiasi protocollo di collegamento registrato.  
  
 Per le applicazioni che non possono utilizzare il modello di richiesta/risposta o per le applicazioni che devono restare <xref:System.Net.Sockets.TcpListener>in <xref:System.Net.Sockets.UdpClient> ascolto sulla rete e inviare richieste, lo spazio dei **nomi System.Net.Sockets** fornisce le <xref:System.Net.Sockets.TcpClient>classi , , e . Queste classi gestiscono i dettagli dell'esecuzione di connessioni tramite protocolli di trasporto diversi ed espongono la connessione di rete all'applicazione come flusso.  
  
 Gli sviluppatori che hanno familiarità con l'interfaccia Windows Sockets o che hanno bisogno del controllo fornito dalla programmazione a livello di socket troveranno le classi **System.Net.Sockets** appropriate a queste esigenze. Le classi **System.Net.Sockets** costituiscono un punto di transizione dal codice gestito al codice nativo all'interno delle classi **System.Net**. Nella maggior parte dei casi, le classi **System.Net.Sockets** eseguono il marshalling dei dati nelle rispettive controparti Windows a 32 bit e gestiscono tutti i controlli di sicurezza necessari.  
  
## <a name="see-also"></a>Vedere anche

- [programmazione di protocolli di collegamento](programming-pluggable-protocols.md)
- [Programmazione di rete in .NET Framework](index.md)
- [Esempi di programmazione di rete](network-programming-samples.md)

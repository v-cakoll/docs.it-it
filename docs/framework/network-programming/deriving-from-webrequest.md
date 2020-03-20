---
title: Derivazione da WebRequest
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, pluggable protocols
- protocol-specific request handler
- sending data, pluggable protocols
- pluggable protocols, class criteria
- Internet, pluggable protocols
- receiving data, pluggable protocols
- protocols, pluggable
ms.assetid: 9810c177-973e-43d7-823c-14960bd625ea
ms.openlocfilehash: 6bee864f8d24076d16f226c29d61801e856739d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048605"
---
# <a name="deriving-from-webrequest"></a>Derivazione da WebRequest
La classe <xref:System.Net.WebRequest> è una classe base astratta che fornisce metodi e proprietà di base per creare un gestore richieste specifico del protocollo adatto al modello di protocollo di collegamento di .NET Framework. Le applicazioni che usano la classe **WebRequest** possono richiedere i dati usando qualsiasi protocollo supportato senza dover specificare il protocollo usato.  
  
 Per usare una classe specifica del protocollo come protocollo di collegamento, è necessario che siano soddisfatti due criteri: la classe deve implementare l'interfaccia <xref:System.Net.IWebRequestCreate> e deve eseguire la registrazione con il metodo <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType>. La classe deve eseguire l'override di tutti i metodi e le proprietà astratti di **WebRequest** per fornire l'interfaccia di collegamento.  
  
 Le istanze di **WebRequest** sono monouso. Per eseguire un'altra richiesta, creare un nuovo elemento **WebRequest**. **WebRequest** supporta l'interfaccia <xref:System.Runtime.Serialization.ISerializable> per consentire agli sviluppatori di serializzare un modello **WebRequest** e quindi ricostruire il modello per richieste aggiuntive.  
  
## <a name="iwebrequest-create-method"></a>Metodo IWebRequest Create  
 Il metodo <xref:System.Net.IWebRequestCreate.Create%2A> è responsabile dell'inizializzazione di una nuova istanza della classe specifica del protocollo. Quando viene creato un nuovo elemento **WebRequest**, il metodo <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> fa corrispondere l'URI richiesto con i prefissi URI registrati con il metodo **RegisterPrefix**. Il metodo **Create** del discendente specifico del protocollo appropriato deve restituire un'istanza inizializzata del discendente in grado di eseguire una transazione di richiesta/risposta standard per il protocollo senza bisogno di modificare i campi specifici del protocollo.  
  
## <a name="connectiongroupname-property"></a>Proprietà ConnectionGroupName  
 La proprietà <xref:System.Net.WebRequest.ConnectionGroupName%2A> viene usata per denominare un gruppo di connessioni a una risorsa in modo che si possano eseguire più richieste tramite una singola connessione. Per implementare la condivisione di connessioni, è necessario usare un metodo specifico del protocollo per il pool e l'assegnazione delle connessioni. La classe <xref:System.Net.ServicePointManager> fornita, ad esempio, implementa la condivisione di connessioni per la classe <xref:System.Net.HttpWebRequest>. La classe **ServicePointManager** crea un elemento <xref:System.Net.ServicePoint> che fornisce una connessione a un server specifico per ogni gruppo di connessioni.  
  
## <a name="contentlength-property"></a>Proprietà ContentLength  
 La proprietà <xref:System.Net.WebRequest.ContentLength%2A> specifica il numero di byte di dati che verranno inviati al server durante il caricamento dei dati.  
  
 La proprietà <xref:System.Net.WebRequest.Method%2A> in genere deve essere impostata per indicare che è in corso un caricamento quando la proprietà **ContentLength** è impostata su un valore maggiore di zero.  
  
## <a name="contenttype-property"></a>Proprietà ContentType  
 La proprietà <xref:System.Net.WebRequest.ContentType%2A> fornisce le informazioni speciali che, in base al protocollo, devono essere inviate al server per identificare il tipo di contenuto inviato. Si tratta in genere del tipo di contenuto MIME dei dati caricati.  
  
## <a name="credentials-property"></a>Proprietà Credentials  
 La proprietà <xref:System.Net.WebRequest.Credentials%2A> contiene le informazioni necessarie per autenticare la richiesta con il server. È necessario implementare i dettagli del processo di autenticazione per il protocollo. La classe <xref:System.Net.AuthenticationManager> ha la responsabilità di autenticare le richieste e di fornire un token di autenticazione. La classe che fornisce le credenziali usate dal protocollo deve implementare l'interfaccia <xref:System.Net.ICredentials>.  
  
## <a name="headers-property"></a>Proprietà Headers  
 La proprietà <xref:System.Net.WebRequest.Headers%2A> contiene una raccolta arbitraria di coppie nome/valore dei metadati associati alla richiesta. Tutti i metadati necessari per il protocollo che possono essere espressi come coppia di nome/valore possono essere inclusi nella proprietà **Headers**. Queste informazioni in genere devono essere impostate prima di chiamare i metodi <xref:System.Net.WebRequest.GetRequestStream%2A> o <xref:System.Net.WebRequest.GetResponse%2A>. Dopo che la richiesta è stata eseguita, i metadati vengono considerati di sola lettura.  
  
 Non è obbligatorio usare la proprietà **Headers** per usare i metadati dell'intestazione. I metadati specifici del protocollo possono essere esposti come proprietà. La proprietà <xref:System.Net.HttpWebRequest.UserAgent%2A?displayProperty=nameWithType>, ad esempio, espone l'intestazione HTTP **User-Agent**. Quando si espongono i metadati dell'intestazione come proprietà, non consentire l'impostazione della stessa proprietà tramite la proprietà **Headers**.  
  
## <a name="method-property"></a>Proprietà Method  
 La proprietà <xref:System.Net.WebRequest.Method%2A> contiene il verbo o l'azione che la richiesta chiede al server di eseguire. L'impostazione predefinita della proprietà **Method** deve consentire un'azione di richiesta/risposta standard senza richiedere l'impostazione di proprietà specifiche del protocollo. Il valore predefinito del metodo <xref:System.Net.HttpWebResponse.Method%2A> è GET, che richiede una risorsa da un server Web e restituisce la risposta.  
  
 La proprietà **ContentLength** in genere deve essere impostata su un valore maggiore di zero quando la proprietà **Method** è impostata su un verbo o un'azione indicante che è in corso un caricamento.  
  
## <a name="preauthenticate-property"></a>Proprietà PreAuthenticate  
 Le applicazioni impostano la proprietà <xref:System.Net.WebRequest.PreAuthenticate%2A> per indicare che le informazioni sull'autenticazione devono essere inviate con la richiesta iniziale invece di attendere una richiesta di autenticazione. La proprietà **PreAuthenticate** è significativa solo se il protocollo supporta le credenziali di autenticazione inviate con la richiesta iniziale.  
  
## <a name="proxy-property"></a>Proprietà Proxy  
 La proprietà <xref:System.Net.WebRequest.Proxy%2A> contiene un'interfaccia <xref:System.Net.IWebProxy> usata per accedere alla risorsa richiesta. La proprietà **Proxy** è significativa solo se il protocollo supporta le richieste con proxy. È necessario impostare il proxy predefinito se ne è richiesto uno dal protocollo.  
  
 In alcuni ambienti, ad esempio dietro un firewall aziendale, il protocollo potrebbe essere necessario per usare un proxy. In tal caso, è necessario implementare l'interfaccia **IWebProxy** per creare una classe proxy che funzionerà per il protocollo.  
  
## <a name="requesturi-property"></a>Proprietà RequestUri  
 La proprietà <xref:System.Net.WebRequest.RequestUri%2A> contiene l'URI passato al metodo **WebRequest.Create**. È di sola lettura e non può essere modificata dopo che l'elemento **WebRequest** è stato creato. Se il protocollo supporta il reindirizzamento, la risposta può provenire da una risorsa identificata da un URI diverso. Se è necessario fornire l'accesso all'URI che ha risposto, si deve fornire una proprietà aggiuntiva contenente tale URI.  
  
## <a name="timeout-property"></a>Proprietà timeout  
 La proprietà <xref:System.Net.WebRequest.Timeout%2A> contiene il tempo di attesa, in millisecondi, prima che la richiesta raggiunga il timeout e generi un'eccezione. **Timeout** si applica solo alle richieste sincrone eseguite con il metodo <xref:System.Net.WebRequest.GetResponse%2A>. Le richieste asincrone devono usare il metodo <xref:System.Net.WebRequest.Abort%2A> per annullare una richiesta in sospeso.  
  
 L'impostazione della proprietà **Timeout** è significativa solo se la classe specifica del protocollo implementa un processo di timeout.  
  
## <a name="abort-method"></a>Metodo Abort  
 Il metodo <xref:System.Net.WebRequest.Abort%2A> annulla una richiesta asincrona in sospeso a un server. Dopo l'annullamento della richiesta, la chiamata a **GetResponse**, **BeginGetResponse**, **EndGetResponse**, **GetRequestStream**, **BeginGetRequestStream** o **EndGetRequestStream** genererà <xref:System.Net.WebException> con la proprietà <xref:System.Net.WebException.Status%2A> impostata su <xref:System.Net.WebExceptionStatus>.  
  
## <a name="begingetrequeststream-and-endgetrequeststream-methods"></a>Metodi BeginGetRequestStream e EndGetRequestStream  
 Il metodo <xref:System.Net.WebRequest.BeginGetRequestStream%2A> avvia una richiesta asincrona per il flusso che viene usato per caricare i dati sul server. Il metodo <xref:System.Net.WebRequest.EndGetRequestStream%2A> completa la richiesta asincrona e restituisce il flusso richiesto. Questi metodi implementano il metodo **GetRequestStream** usando il modello asincrono di .NET Framework standard.  
  
## <a name="begingetresponse-and-endgetresponse-methods"></a>Metodi BeginGetResponse ed EndGetResponse  
 Il metodo <xref:System.Net.WebRequest.BeginGetResponse%2A> avvia una richiesta asincrona a un server. Il metodo <xref:System.Net.WebRequest.EndGetResponse%2A> completa la richiesta asincrona e restituisce la risposta richiesta. Questi metodi implementano il metodo **GetResponse** usando il modello asincrono di .NET Framework standard.  
  
## <a name="getrequeststream-method"></a>Metodo GetRequestStream  
 Il metodo <xref:System.Net.WebRequest.GetRequestStream%2A> restituisce un flusso che viene usato per scrivere i dati nel server richiesto. Il flusso restituito deve essere un flusso di sola scrittura che non esegue ricerche. Viene usato come flusso di dati unidirezionale scritti sul server. Il flusso restituisce false per le proprietà <xref:System.IO.Stream.CanRead%2A> e <xref:System.IO.Stream.CanSeek%2A> e true per la proprietà <xref:System.IO.Stream.CanWrite%2A>.  
  
 Il metodo **GetRequestStream** in genere apre una connessione al server e, prima di restituire il flusso, invia le informazioni sull'intestazione indicanti che i dati vengono inviati al server. Poiché **GetRequestStream** inizia la richiesta, l'impostazione di proprietà **Header** o della proprietà **ContentLength** in genere non è consentita dopo la chiamata a **GetRequestStream**.  
  
## <a name="getresponse-method"></a>Metodo GetResponse  
 Il metodo <xref:System.Net.WebRequest.GetResponse%2A> restituisce un discendente specifico del protocollo della classe <xref:System.Net.WebResponse> che rappresenta la risposta dal server. A meno che la richiesta non sia già stata avviata dal metodo **GetRequestStream**, il metodo **GetResponse** crea una connessione alla risorsa identificata da **RequestUri**, invia le informazioni sull'intestazione indicanti il tipo di richiesta in esecuzione e quindi riceve la risposta dalla risorsa.  
  
 Dopo la chiamata al metodo **GetResponse**, tutte le proprietà sono da considerare di sola lettura. Le istanze di **WebRequest** sono monouso. Per eseguire un'altra richiesta, è consigliabile creare un nuovo elemento **WebRequest**.  
  
 Il metodo **GetResponse** è responsabile della creazione di un discendente di **WebResponse** appropriato per contenere la risposta in arrivo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.WebRequest>
- <xref:System.Net.HttpWebRequest>
- <xref:System.Net.FileWebRequest>
- [programmazione di protocolli di collegamento](programming-pluggable-protocols.md)
- [Derivazione da WebResponse](deriving-from-webresponse.md)

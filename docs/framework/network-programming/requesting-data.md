---
title: Richiesta di dati
description: Informazioni su come i protocolli di collegamento consentono di sviluppare applicazioni che usano una singola interfaccia per recuperare dati da più protocolli.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sending data
- WebRequest class, sending and receiving data
- requesting data from Internet, about requesting data
- WebClient class, sending and receiving data
- network, requesting data
- receiving data
- sending data, about sending data
- response to Internet request, about responding to Internet requests
- data requests
- receiving data, about receiving data
- Internet, requesting data
ms.assetid: df6f1e1d-6f2a-45dd-8141-4a85c3dafe1d
ms.openlocfilehash: 19350d685a81d56657ca0a117d61b50ae24fab6a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502184"
---
# <a name="requesting-data"></a>Richiesta di dati
Lo sviluppo di applicazioni in esecuzione nell'ambiente operativo distribuito dell'attuale rete Internet richiede un metodo efficace e semplice da usare per il recupero dei dati da risorse di tutti i tipi. I protocolli di collegamento consentono di sviluppare applicazioni che usano una singola interfaccia per recuperare i dati da più protocolli Internet.  
  
## <a name="uploading-and-downloading-data-from-an-internet-server"></a>Caricamento e download dei dati da un server Internet  
 Per semplici transazioni di richiesta e risposta, la classe <xref:System.Net.WebClient> offre il metodo più semplice per caricare e scaricare i dati da un server Internet. **WebClient** fornisce metodi per caricare e scaricare file, inviare e ricevere flussi, inviare un buffer di dati al server e ricevere una risposta. **WebClient** usa le classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> per stabilire le connessioni alla risorsa Internet, così che qualunque protocollo di collegamento registrato sia disponibile per l'uso.  
  
 Le applicazioni client che devono eseguire transazioni più complesse richiedono i dati dai server usando la classe **WebRequest** e i relativi discendenti. **WebRequest** incapsula i dettagli della connessione al server, inviando la richiesta e ricevendo la risposta. **WebRequest** è una classe astratta che definisce un set di proprietà e metodi disponibili per tutte le applicazioni che usano protocolli di collegamento. I discendenti di **WebRequest**, come <xref:System.Net.HttpWebRequest>, implementano le proprietà e i metodi definiti da **WebRequest** in modo coerente con il protocollo sottostante.  
  
 La classe **WebRequest** crea istanze specifiche del protocollo dei discendenti di **WebRequest** usando il valore dell'URI passato al metodo <xref:System.Net.WebRequest.Create%2A> per determinare l'istanza di classe derivata specifica da creare. Le applicazioni indicano i discendenti di **WebRequest** da usare per gestire una richiesta registrando il costruttore del discendente con il metodo <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType>.  
  
 Viene effettuata una richiesta alla risorsa Internet chiamando il metodo <xref:System.Net.WebRequest.GetResponse%2A> in **WebRequest**. Il metodo **GetResponse** costruisce la richiesta specifica del protocollo usando le proprietà di **WebRequest**, crea la connessione socket TCP o UDP al server e invia la richiesta. Per le richieste che inviano dati al server, ad esempio le richieste HTTP **Post** o FTP **Put**, il metodo <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> fornisce un flusso di rete in cui inviare dati.  
  
 Il metodo **GetResponse** restituisce un oggetto **WebResponse** specifico del protocollo che corrisponde all'oggetto **WebRequest**.  
  
 La classe **WebResponse** è anche una classe astratta che definisce le proprietà e i metodi disponibili per tutte le applicazioni che usano protocolli di collegamento. I discendenti di **WebResponse** implementano questi metodi e proprietà per il protocollo sottostante. La classe <xref:System.Net.HttpWebResponse>, ad esempio, implementa la classe **WebResponse** per HTTP.  
  
 I dati restituiti dal server vengono presentati all'applicazione nel flusso restituito dal metodo <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>. È possibile usare questo flusso come qualsiasi altro, come illustrato nell'esempio seguente.  
  
```csharp  
StreamReader sr =  
   new StreamReader(resp.GetResponseStream(), Encoding.ASCII);  
```  
  
```vb  
Dim sr As StreamReader  
sr = New StreamReader(resp.GetResponseStream(), Encoding.ASCII)  
```  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione di rete nel .NET Framework](index.md)
- [Procedura: Richiedere una pagina Web e recuperare i risultati sotto forma di flusso](how-to-request-a-web-page-and-retrieve-the-results-as-a-stream.md)
- [Procedura: Recuperare un oggetto WebResponse specifico del protocollo corrispondente a un oggetto WebRequest](how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest.md)

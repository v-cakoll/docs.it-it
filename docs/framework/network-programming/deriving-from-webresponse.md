---
title: Derivazione da WebResponse
ms.date: 03/30/2017
helpviewer_keywords:
- Deriving from WebResponse
ms.assetid: f11d4866-a199-4087-9306-a5a4c18b13db
ms.openlocfilehash: bd06928b08eb085ef13371687fb1e5b92c6c1d86
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048584"
---
# <a name="deriving-from-webresponse"></a>Derivazione da WebResponse
La classe <xref:System.Net.WebResponse> è una classe base astratta che fornisce metodi e proprietà di base per creare un risposta specifica del protocollo adatta al modello di protocollo di collegamento di .NET Framework. Le applicazioni che usano la classe <xref:System.Net.WebRequest> per richiedere i dati dalle risorse ricevono le risposte in **WebResponse**. I discendenti specifici del protocollo **WebResponse** devono implementare i membri astratti della classe **WebResponse**.  
  
 La classe **WebRequest** associata deve creare i discendenti di **WebResponse**. Le istanze di <xref:System.Net.HttpWebResponse>, ad esempio, vengono create solo come risultato della chiamata a <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> o <xref:System.Net.HttpWebRequest.EndGetResponse%2A?displayProperty=nameWithType>. Ogni elemento **WebResponse** contiene il risultato di una richiesta a una risorsa e non è destinato a essere riutilizzato.  
  
## <a name="contentlength-property"></a>Proprietà ContentLength  
 La proprietà <xref:System.Net.WebResponse.ContentLength%2A> indica il numero di byte di dati disponibili dal flusso restituito dal metodo <xref:System.Net.WebResponse.GetResponseStream%2A>. La proprietà **ContentLength** non indica il numero di byte delle informazioni dell'intestazione o dei metadati restituite dal server. Indica solo il numero di byte di dati nella risorsa richiesta in sé.  
  
## <a name="contenttype-property"></a>Proprietà ContentType  
 La proprietà <xref:System.Net.WebResponse.ContentType%2A> fornisce le informazioni speciali che, in base al protocollo, devono essere inviate al client per identificare il tipo di contenuto inviato dal server. Si tratta in genere del tipo di contenuto MIME dei dati restituiti.  
  
## <a name="headers-property"></a>Proprietà Headers  
 La proprietà <xref:System.Net.WebResponse.Headers%2A> contiene una raccolta arbitraria di coppie nome/valore dei metadati associati alla risposta. Tutti i metadati necessari per il protocollo che possono essere espressi come coppia di nome/valore possono essere inclusi nella proprietà **Headers**.  
  
 Non è obbligatorio usare la proprietà **Headers** per usare i metadati dell'intestazione. I metadati specifici del protocollo possono essere esposti come proprietà. La proprietà <xref:System.Net.HttpWebResponse.LastModified%2A?displayProperty=nameWithType>, ad esempio, espone l'intestazione HTTP **Last-Modified**. Quando si espongono i metadati dell'intestazione come proprietà, non consentire l'impostazione della stessa proprietà tramite la proprietà **Headers**.  
  
## <a name="responseuri-property"></a>Proprietà ResponseUri  
 La proprietà <xref:System.Net.WebResponse.ResponseUri%2A> contiene l'URI della risorsa che ha effettivamente fornito la risposta. Per i protocolli che non supportano il reindirizzamento, **ResponseUri** sarà uguale alla proprietà <xref:System.Net.WebRequest.RequestUri%2A> dell'elemento **WebRequest** che ha creato la risposta. Se il protocollo supporta il reindirizzamento della richiesta, **ResponseUri** conterrà l'URI della risposta.  
  
## <a name="close-method"></a>Metodo Close  
 Il metodo <xref:System.Net.WebResponse.Close%2A> chiude le connessioni eseguite dalla richiesta e dalla risposta e pulisce le risorse usate dalla risposta. Il metodo **Close** chiude le istanze del flusso usate dalla risposta, ma non genera un'eccezione se il flusso della risposta è stato chiuso prima da una chiamata al metodo <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.  
  
## <a name="getresponsestream-method"></a>Metodo GetResponseStream  
 Il metodo <xref:System.Net.WebResponse.GetResponseStream%2A> restituisce un flusso contenente la risposta dalla risorsa richiesta. Il flusso della risposta contiene solo i dati restituiti dalla risorsa. Le intestazioni o i metadati inclusi nella risposta devono essere rimossi dalla risposta ed esposti all'applicazione tramite le proprietà specifiche del protocollo o la proprietà **Headers**.  
  
 L'istanza del flusso restituita dal metodo **GetResponseStream** è di proprietà dell'applicazione e può essere chiusa senza chiudere **WebResponse**. Per convenzione, la chiamata al metodo **WebResponse.Close** chiude anche il flusso restituito da **GetResponse**.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.WebResponse>
- <xref:System.Net.HttpWebResponse>
- <xref:System.Net.FileWebResponse>
- [programmazione di protocolli di collegamento](programming-pluggable-protocols.md)
- [Derivazione da WebRequest](deriving-from-webrequest.md)

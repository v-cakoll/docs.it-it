---
title: programmazione di protocolli di collegamento
description: Informazioni su come le classi astratte WebRequest e WebResponse supportano i protocolli di collegamento, che consentono a un'applicazione di ottenere i dati senza specificare un protocollo.
ms.date: 03/30/2017
helpviewer_keywords:
- downloading Internet resources, pluggable protocols
- WebRequest class, pluggable protocols
- response to Internet request, pluggable protocols
- WebResponse class, pluggable protocols
- sending data, pluggable protocols
- network resources, pluggable protocols
- Internet, pluggable protocols
- programming pluggable protocols
- pluggable protocols, programming
- requesting data from Internet, pluggable protocols
- receiving data, pluggable protocols
- protocols, pluggable
ms.assetid: 66ef8456-7576-4e97-8956-959b216373db
ms.openlocfilehash: 510f616295abc13d93e0e0af5a37aca097d343e3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502197"
---
# <a name="programming-pluggable-protocols"></a>programmazione di protocolli di collegamento
Le classi astratte <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> rappresentano la base per i protocolli di collegamento. Tramite la derivazione di classi specifiche del protocollo da <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse>, un'applicazione può richiedere i dati da una risorsa Internet e leggere la risposta senza specificare il protocollo usato.  
  
 Prima di poter creare una <xref:System.Net.WebRequest> specifica del protocollo, è necessario registrarne il metodo Create. Usare il metodo statico <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> di <xref:System.Net.WebRequest> per registrare un discendente <xref:System.Net.WebRequest> per la gestione di un set di richieste in un particolare schema Internet, in uno schema e un server oppure in uno schema, un server e un percorso.  
  
 Nella maggior parte dei casi sarà possibile inviare e ricevere dati tramite i metodi e le proprietà della classe <xref:System.Net.WebRequest>. Tuttavia, se è necessario accedere alle proprietà specifiche del protocollo, è possibile eseguire il cast di tipo di <xref:System.Net.WebRequest> su una specifica istanza della classe derivata.  
  
 Per sfruttare i protocolli di collegamento, i discendenti <xref:System.Net.WebRequest> devono fornire una transazione di richiesta e risposta predefinita che non richiede l'impostazione di proprietà specifiche del protocollo. Ad esempio, la classe <xref:System.Net.HttpWebRequest> che implementa la classe <xref:System.Net.WebRequest> per il protocollo HTTP, fornisce una richiesta `GET` per impostazione predefinita e restituisce una <xref:System.Net.HttpWebResponse> che contiene il flusso restituito dal server Web.  
  
## <a name="see-also"></a>Vedere anche

- [Derivazione da WebRequest](deriving-from-webrequest.md)
- [Derivazione da WebResponse](deriving-from-webresponse.md)
- [Programmazione di rete nel .NET Framework](index.md)
- [Procedura: Eseguire il cast di tipo di un oggetto WebRequest per accedere a proprietà specifiche del protocollo](how-to-typecast-a-webrequest-to-access-protocol-specific-properties.md)

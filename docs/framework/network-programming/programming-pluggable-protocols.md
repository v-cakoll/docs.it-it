---
title: programmazione di protocolli di collegamento
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
caps.latest.revision: 12
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b422012004d164cf8a84ddeb53b6c0bf9fd1fb92
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# programmazione di protocolli di collegamento
Le classi astratte <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> rappresentano la base per i protocolli di collegamento. Tramite la derivazione di classi specifiche del protocollo da <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse>, un'applicazione può richiedere i dati da una risorsa Internet e leggere la risposta senza specificare il protocollo usato.  
  
 Prima di poter creare una <xref:System.Net.WebRequest> specifica del protocollo, è necessario registrarne il metodo Create. Usare il metodo statico <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> di <xref:System.Net.WebRequest> per registrare un discendente <xref:System.Net.WebRequest> per la gestione di un set di richieste in un particolare schema Internet, in uno schema e un server oppure in uno schema, un server e un percorso.  
  
 Nella maggior parte dei casi sarà possibile inviare e ricevere dati tramite i metodi e le proprietà della classe <xref:System.Net.WebRequest>. Tuttavia, se è necessario accedere alle proprietà specifiche del protocollo, è possibile eseguire il cast di tipo di <xref:System.Net.WebRequest> su una specifica istanza della classe derivata.  
  
 Per sfruttare i protocolli di collegamento, i discendenti <xref:System.Net.WebRequest> devono fornire una transazione di richiesta e risposta predefinita che non richiede l'impostazione di proprietà specifiche del protocollo. Ad esempio, la classe <xref:System.Net.HttpWebRequest> che implementa la classe <xref:System.Net.WebRequest> per il protocollo HTTP, fornisce una richiesta `GET` per impostazione predefinita e restituisce una <xref:System.Net.HttpWebResponse> che contiene il flusso restituito dal server Web.  
  
## Vedere anche  
 [Derivazione da WebRequest](../../../docs/framework/network-programming/deriving-from-webrequest.md)   
 [Derivazione da WebResponse](../../../docs/framework/network-programming/deriving-from-webresponse.md)   
 [Programmazione di rete in .NET Framework](../../../docs/framework/network-programming/index.md)   
 [Procedura: Eseguire il cast di tipo di un oggetto WebRequest per accedere a proprietà specifiche del protocollo](../../../docs/framework/network-programming/how-to-typecast-a-webrequest-to-access-protocol-specific-properties.md)


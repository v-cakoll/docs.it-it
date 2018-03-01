---
title: Creazione di documenti XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ea67841e44d8d88d2effec92eb1668142c1510f2
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="xml-document-creation"></a>Creazione di documenti XML
Sono disponibili due metodi per creare un documento XML: uno di questi consiste nel creare un **XmlDocument** senza parametri; l'altro consiste nel creare un **XmlDocument** e passarlo al documento XmlNameTable come parametro. Nell'esempio seguente viene illustrata la creazione di un nuovo **XmlDocument** vuoto senza l'uso di parametri.  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 Una volta creato un documento, è possibile caricarlo con i dati da una stringa, un flusso, un URL, un lettore di testo o una classe derivata **XmlReader** usando il metodo **Load**. È disponibile anche un altro metodo di caricamento, **LoadXML**, con il quale è possibile leggere il codice XML da una stringa. Per altre informazioni sui diversi metodi **Load**, vedere [Lettura di un documento XML nel DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).  
  
 È disponibile una classe denominata **XmlNameTable**. Questa è una tabella di oggetti stringa atomici. Tale tabella fornisce al parser XML un mezzo efficiente per usare lo stesso oggetto stringa per tutti i nomi degli attributi e degli elementi ripetuti in un documento XML. Quando un documento viene creato nel modo illustrato in precedenza e caricato con i nomi di attributi ed elementi, viene creata automaticamente una **XmlNameTable**. Se è già disponibile un documento con una tabella di nomi utili in un altro documento, è possibile creare un nuovo documento usando il metodo **Load** che accetta **XmlNameTable** come parametro. Quando viene creato con questo metodo, il documento utilizzerà l'**XmlNameTable** disponibile con tutti gli attributi e gli elementi già caricati dall'altro documento e questa potrà essere usata per paragonare i nomi di elementi e attributi in maniera efficiente. Per altre informazioni sull'**XmlNameTable**, vedere [Confronto di oggetti con XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md). Per riferimento, vedere <xref:System.Xml.XmlNameTable>.  
  
## <a name="see-also"></a>Vedere anche  
 [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)

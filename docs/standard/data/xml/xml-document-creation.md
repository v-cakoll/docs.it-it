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
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a0806e34cfbf7c8e0b5ba995ca4876b8d10405e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-creation"></a>Creazione di documenti XML
Sono disponibili due metodi per creare un documento XML: Un modo consiste nel creare un **XmlDocument** senza parametri. L'altro consiste nel creare un **XmlDocument** e passare al documento XmlNameTable come parametro. Nell'esempio seguente viene illustrato come creare un nuovo oggetto vuoto **XmlDocument** senza parametri.  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 Dopo aver creato un documento, è possibile caricare i dati da una stringa, flusso, un URL, il lettore di testo, o un **XmlReader** derivata della classe utilizzando il **caricare** metodo. È inoltre disponibile un altro metodo di caricamento, la **LoadXML** metodo, che legge codice XML da una stringa. Per ulteriori informazioni sui vari **carico** metodi, vedere [lettura di un documento XML nel DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).  
  
 È una classe denominata la **XmlNameTable**. Questa è una tabella di oggetti stringa atomici. Tale tabella fornisce al parser XML un mezzo efficiente per usare lo stesso oggetto stringa per tutti i nomi degli attributi e degli elementi ripetuti in un documento XML. Un **XmlNameTable** viene creata automaticamente quando un documento viene creato come illustrato in precedenza e viene caricato con i nomi di elemento e attributo quando il documento viene caricato. Se si dispone già di un documento con una tabella, di tali nomi utili in un altro documento, è possibile creare un nuovo documento usando il **carico** metodo che accetta un **XmlNameTable** come parametro. Quando il documento viene creato con questo metodo, utilizzerà il **XmlNameTable** con tutti gli attributi e gli elementi già caricati da altro documento. e questa potrà essere usata per paragonare i nomi di elementi e attributi in maniera efficiente. Per ulteriori informazioni sul **XmlNameTable**, vedere [confronto di oggetti con XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md). Per riferimento, vedere <xref:System.Xml.XmlNameTable>.  
  
## <a name="see-also"></a>Vedere anche  
 [XML Document Object Model (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)

---
title: Creazione di documenti XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
ms.openlocfilehash: 577d353a30c986d198140b4596ae1a7e199ddd6e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291981"
---
# <a name="xml-document-creation"></a>Creazione di documenti XML
Sono disponibili due metodi per creare un documento XML: uno di questi consiste nel creare un **XmlDocument** senza parametri; l'altro consiste nel creare un **XmlDocument** e passarlo al documento XmlNameTable come parametro. Nell'esempio seguente viene illustrata la creazione di un nuovo **XmlDocument** vuoto senza l'uso di parametri.  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 Una volta creato un documento, è possibile caricarlo con i dati da una stringa, un flusso, un URL, un lettore di testo o una classe derivata **XmlReader** usando il metodo **Load**. È disponibile anche un altro metodo di caricamento, **LoadXML**, con il quale è possibile leggere il codice XML da una stringa. Per altre informazioni sui diversi metodi **Load**, vedere [Lettura di un documento XML nel DOM](reading-an-xml-document-into-the-dom.md).  
  
 È disponibile una classe denominata **XmlNameTable**. Questa è una tabella di oggetti stringa atomici. Tale tabella fornisce al parser XML un mezzo efficiente per usare lo stesso oggetto stringa per tutti i nomi degli attributi e degli elementi ripetuti in un documento XML. Quando un documento viene creato nel modo illustrato in precedenza e caricato con i nomi di attributi ed elementi, viene creata automaticamente una **XmlNameTable**. Se è già disponibile un documento con una tabella di nomi utili in un altro documento, è possibile creare un nuovo documento usando il metodo **Load** che accetta **XmlNameTable** come parametro. Quando viene creato con questo metodo, il documento utilizzerà l'**XmlNameTable** disponibile con tutti gli attributi e gli elementi già caricati dall'altro documento e questa potrà essere usata per paragonare i nomi di elementi e attributi in maniera efficiente. Per altre informazioni sull'**XmlNameTable**, vedere [Confronto di oggetti con XmlNameTable](object-comparison-using-xmlnametable.md). Per riferimento, vedere <xref:System.Xml.XmlNameTable>.  
  
## <a name="see-also"></a>Vedere anche

- [XML DOM (Document Object Model)](xml-document-object-model-dom.md)

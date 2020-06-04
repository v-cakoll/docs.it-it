---
title: Conservazione degli spazi vuoti durante Serializing2
ms.date: 07/20/2015
ms.assetid: 2d7abbd4-37f4-422b-89dd-0a694b5edc17
ms.openlocfilehash: e9b73089830bf7e6cb0ea9e469bf667f12c571d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396402"
---
# <a name="preserving-white-space-while-serializing"></a>Conservazione di spazi vuoti durante la serializzazione
In questo argomento viene descritto come controllare lo spazio vuoto durante la serializzazione di un albero XML.  
  
 In uno scenario comune viene letto il codice XML rientrato, viene creata una struttura ad albero XML in memoria senza nodi di testo di tipo spazio vuoto (ossia senza conservare lo spazio vuoto), vengono eseguite alcune operazioni su XML e quindi l'XML viene salvato senza rientro. Quando si serializza l'XML con la formattazione, nell'albero XML viene conservato solo lo spazio vuoto significativo. Questo è il comportamento predefinito per [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 In un altro scenario comune viene letto e modificato codice XML che è già stato intenzionalmente rientrato. È possibile che si desideri non modificare questo rientro in alcun modo. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile ottenere questo risultato conservando lo spazio vuoto durante il caricamento o l'analisi XML e disabilitando la formattazione durante la serializzazione XML.  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a>Comportamento dello spazio vuoto di metodi che serializzano strutture ad albero XML  
 I metodi seguenti delle classi <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XDocument> serializzano un albero XML. È possibile serializzare un albero XML in un file, in un oggetto <xref:System.IO.TextReader> o in un oggetto <xref:System.Xml.XmlReader>. Il metodo `ToString` consente di eseguire la serializzazione in una stringa.  
  
- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
- [XElement.ToString()](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)
  
- [XDocument.ToString()](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)
  
 Se il metodo non accetta <xref:System.Xml.Linq.SaveOptions> come argomento, formatterà il codice XML serializzato, ovvero ne imposterà il rientro. In questo caso tutto lo spazio vuoto non significativo nella struttura ad albero XML verrà ignorato.  
  
 Se il metodo accetta <xref:System.Xml.Linq.SaveOptions> come argomento, è possibile specificare di non formattare il codice XML serializzato, ovvero il metodo non ne imposterà il rientro. In questo caso tutto lo spazio vuoto nella struttura ad albero XML verrà mantenuto.  
  
## <a name="see-also"></a>Vedere anche

- [Serializzazione di strutture ad albero XML (Visual Basic)](serializing-xml-trees.md)

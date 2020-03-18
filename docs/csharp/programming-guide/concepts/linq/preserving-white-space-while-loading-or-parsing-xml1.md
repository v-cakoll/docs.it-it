---
title: Conservazione di spazi vuoti durante il caricamento o l'analisi di dati XML
ms.date: 07/20/2015
ms.assetid: f3ff58c4-55aa-4fcd-b933-e3a2ee6e706c
ms.openlocfilehash: d015c21813df2224356bb49212fe282fa5372d03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69591546"
---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a>Conservazione di spazi vuoti durante il caricamento o l'analisi di dati XML
Questo argomento descrive come controllare il comportamento dello spazio vuoto di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 In uno scenario comune viene letto il codice XML rientrato, viene creata una struttura ad albero XML in memoria senza nodi di testo di tipo spazio vuoto (ossia senza conservare lo spazio vuoto), vengono eseguite alcune operazioni su XML e quindi l'XML viene salvato senza rientro. Quando si serializza l'XML con la formattazione, nell'albero XML viene conservato solo lo spazio vuoto significativo. Questo è il comportamento predefinito per [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 In un altro scenario comune viene letto e modificato codice XML che è già stato intenzionalmente rientrato. È possibile che si desideri non modificare questo rientro in alcun modo. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile ottenere questo risultato conservando lo spazio vuoto durante il caricamento o l'analisi XML e disabilitando la formattazione durante la serializzazione XML.  
  
 Questo argomento descrive il comportamento dello spazio vuoto dei metodi che popolano gli alberi XML. Per informazioni sul controllo dello spazio vuoto durante la serializzazione di strutture ad albero XML, vedere [Mantenimento dello spazio vuoto durante la serializzazione](./preserving-white-space-while-serializing.md).  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a>Comportamento dei metodi che popolano gli alberi XML  
 I metodi seguenti nelle classi <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XDocument> popolano un albero XML. È possibile popolare un albero XML da un file, un oggetto <xref:System.IO.TextReader>, un oggetto <xref:System.Xml.XmlReader> o una stringa:  
  
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
  
 Se il metodo non accetta <xref:System.Xml.Linq.LoadOptions> come argomento, non conserverà lo spazio vuoto non significativo.  
  
 Nella maggior parte dei casi, se il metodo accetta <xref:System.Xml.Linq.LoadOptions> come argomento, facoltativamente è possibile conservare lo spazio vuoto non significativo come nodi di testo nell'albero XML. Tuttavia, se il metodo carica l'XML da un oggetto <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlReader> determina se lo spazio vuoto verrà conservato o meno. L'impostazione di <xref:System.Xml.Linq.LoadOptions.PreserveWhitespace> non avrà effetto.  
  
 Se lo spazio vuoto viene conservato, con questi metodi lo spazio vuoto non significativo viene inserito nell'albero XML come nodi <xref:System.Xml.Linq.XText>. Se non viene conservato, i nodi di testo non vengono inseriti.  
  
 È possibile creare un albero XML usando <xref:System.Xml.XmlWriter>. I nodi scritti in <xref:System.Xml.XmlWriter> vengono popolati nell'albero. Tuttavia, quando si compila un albero XML usando questo metodo, vengono conservati tutti i nodi, a prescindere che corrispondano o meno a spazio vuoto e indipendentemente dal fatto che lo spazio vuoto sia o meno significativo.  
  
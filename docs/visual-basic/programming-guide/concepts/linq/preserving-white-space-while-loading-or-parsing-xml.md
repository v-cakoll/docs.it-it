---
title: Conservando lo spazio vuoto durante il caricamento o l'analisi XML2
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef6518e0-2c8d-462c-8b92-a16e9dc737ad
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d99cea37bb9817c40a6d3876b72ccdbd84d7e7ba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a>Conservazione di spazi vuoti durante il caricamento o l'analisi di dati XML
In questo argomento viene descritto come controllare il comportamento dello spazio vuoto di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .  
  
 In uno scenario comune viene letto il codice XML rientrato, viene creata una struttura ad albero XML in memoria senza nodi di testo di tipo spazio vuoto (ossia senza conservare lo spazio vuoto), vengono eseguite alcune operazioni su XML e quindi l'XML viene salvato senza rientro. Quando si serializza l'XML con la formattazione, nell'albero XML viene conservato solo lo spazio vuoto significativo. Questo è il comportamento predefinito per [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 In un altro scenario comune viene letto e modificato codice XML che è già stato intenzionalmente rientrato. È possibile che si desideri non modificare questo rientro in alcun modo. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile ottenere questo risultato conservando lo spazio vuoto durante il caricamento o l'analisi XML e disabilitando la formattazione durante la serializzazione XML.  
  
 In questo argomento viene descritto il comportamento dello spazio vuoto dei metodi che popolano l'albero XML. Per informazioni sul controllo dello spazio vuoto durante la serializzazione di strutture ad albero XML, vedere [Mantenimento dello spazio vuoto durante la serializzazione](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a>Comportamento dei metodi che popolano gli alberi XML  
 I metodi seguenti nelle classi <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XDocument> popolano un albero XML. È possibile popolare un albero XML da un file, un oggetto <xref:System.IO.TextReader>, un oggetto <xref:System.Xml.XmlReader> o una stringa:  
  
-   <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
  
 Se il metodo non accetta <xref:System.Xml.Linq.LoadOptions> come argomento, non conserverà lo spazio vuoto non significativo.  
  
 Nella maggior parte dei casi, se il metodo accetta <xref:System.Xml.Linq.LoadOptions> come argomento, facoltativamente è possibile conservare lo spazio vuoto non significativo come nodi di testo nell'albero XML. Tuttavia, se il metodo carica l'XML da un oggetto <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlReader> determina se lo spazio vuoto verrà conservato o meno. L'impostazione di <xref:System.Xml.Linq.LoadOptions.PreserveWhitespace> non avrà effetto.  
  
 Se lo spazio vuoto viene conservato, con questi metodi lo spazio vuoto non significativo viene inserito nell'albero XML come nodi <xref:System.Xml.Linq.XText>. Se non viene conservato, i nodi di testo non vengono inseriti.  
  
 È possibile creare un albero XML usando <xref:System.Xml.XmlWriter>. I nodi scritti in <xref:System.Xml.XmlWriter> vengono popolati nell'albero. Tuttavia, quando si compila un albero XML usando questo metodo, vengono conservati tutti i nodi, a prescindere che corrispondano o meno a spazio vuoto e indipendentemente dal fatto che lo spazio vuoto sia o meno significativo.  
  
## <a name="see-also"></a>Vedere anche  
 [Analisi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)

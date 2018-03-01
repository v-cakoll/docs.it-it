---
title: Trasformazioni XSLT
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 202f8820-224c-494f-b61e-cd127eac6e03
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 92d0688b86e6a95af46e09c21c1a8b3cdf66efc3
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="xslt-transformations"></a>Trasformazioni XSLT
L'Extensible Stylesheet Language Transformation (XSLT) consente di trasformare il contenuto di un documento XML di origine in un altro documento di formato o struttura diversi, ad esempio per trasformare l'XML in HTML per l'uso su un sito Web o per trasformarlo in un documento che contenga solo i campi richiesti da un'applicazione. Questo processo di trasformazione è specificato dalla raccomandazione [W3C XSL Transformations (XSLT) Version 1.0 recommendation](http://go.microsoft.com/fwlink/?LinkID=49919).  
  
 La classe <xref:System.Xml.Xsl.XslCompiledTransform> è il processore XSLT in .NET Framework. La classe <xref:System.Xml.Xsl.XslCompiledTransform> supporta la raccomandazione W3C XSLT 1.0.  
  
> [!NOTE]
>  La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in .NET Framework versione 2.0. La classe <xref:System.Xml.Xsl.XslCompiledTransform> è una nuova implementazione del motore XSLT, che include prestazioni migliori e nuove funzionalità di sicurezza. Si consiglia di creare le applicazioni XSLT usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Utilizzo della classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)  
 Vengono fornite informazioni sull'utilizzo della classe <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
 [Migrazione dalla classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 Viene descritto come migrare il codice dalla classe <xref:System.Xml.Xsl.XslTransform>.  
  
 [Compilatore XSLT (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)  
 Vengono fornite informazioni sull'utilizzo del compilatore XSLT.  
  
 [Trasformazioni XSLT con la classe XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 Vengono fornite informazioni sull'utilizzo della classe <xref:System.Xml.Xsl.XslTransform>.  
  
 **Nota** La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in .NET Framework release 2.0.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
  
 <xref:System.Xml.Xsl.XsltArgumentList>  
  
 <xref:System.Xml.Xsl.XsltSettings>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Documenti e dati XML](../../../../docs/standard/data/xml/index.md)

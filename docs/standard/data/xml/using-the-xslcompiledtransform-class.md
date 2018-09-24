---
title: Utilizzo della classe XslCompiledTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0537685a91db2c0e323b3f1bda24c6cadc264e34
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2018
ms.locfileid: "46578653"
---
# <a name="using-the-xslcompiledtransform-class"></a>Utilizzo della classe XslCompiledTransform
La classe <xref:System.Xml.Xsl.XslCompiledTransform> è il processore XSLT di Microsoft .NET Framework. Questa classe consente di compilare fogli di stile e di eseguire trasformazioni XSLT.  
  
> [!NOTE]
>  Sebbene le prestazioni complessive della classe <xref:System.Xml.Xsl.XslCompiledTransform> siano migliori rispetto alla classe <xref:System.Xml.Xsl.XslTransform>, l'esecuzione del metodo <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> della classe <xref:System.Xml.Xsl.XslCompiledTransform> potrebbe risultare più lenta di quella del metodo <xref:System.Xml.Xsl.XslTransform.Load%2A> della classe <xref:System.Xml.Xsl.XslTransform> la prima volta che tale metodo viene chiamato su una trasformazione. Questa situazione si verifica perché il file XSLT deve essere compilato prima del caricamento. Per altre informazioni, vedere il post di blog seguente: [XslCompiledTransform Slower than XslTransform?](https://blogs.msdn.microsoft.com/antosha/2006/07/16/xslcompiledtransform-slower-than-xsltransform/) (XslCompiledTransform è più lento di XslTransform?)  
  
## <a name="in-this-section"></a>In questa sezione  
 [Input alla classe XslCompiledTransform](../../../../docs/standard/data/xml/inputs-to-the-xslcompiledtransform-class.md)  
 Vengono descritte le opzioni di input XSLT disponibili.  
  
 [Opzioni di output nella classe XslCompiledTransform](../../../../docs/standard/data/xml/output-options-on-the-xslcompiledtransform-class.md)  
 Vengono descritte le opzioni di output XSLT disponibili.  
  
 [Risoluzione delle risorse esterne durante l'elaborazione XSLT](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 Viene descritto come usare la classe <xref:System.Xml.XmlResolver> per risolvere risorse esterne.  
  
 [Estensione di fogli di stile XSLT](../../../../docs/standard/data/xml/extending-xslt-style-sheets.md)  
 Viene descritto il supporto delle estensioni XSLT.  
  
|||  
|-|-|  
|[Errori XSLT risolvibili](../../../../docs/standard/data/xml/recoverable-xslt-errors.md)|Vengono elencati i comportamenti discretionary consentiti dalla raccomandazione W3C (World Wide Web Consortium) XSLT 1.0 e viene descritto il modo in cui tali comportamenti vengono gestiti dalla classe <xref:System.Xml.Xsl.XslCompiledTransform>.|  
|[Procedura: Trasformare un frammento di nodo](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|Viene descritto come trasformare un frammento di nodo.|  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Migrazione dalla classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 Viene descritto come migrare il codice dalla classe <xref:System.Xml.Xsl.XslTransform>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Xsl.XsltSettings>  
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>

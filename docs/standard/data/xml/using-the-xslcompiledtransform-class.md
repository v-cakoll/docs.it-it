---
title: Utilizzo della classe XslCompiledTransform
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a5c71a7796790343bf39de5bbfd03997c25d5f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-xslcompiledtransform-class"></a>Utilizzo della classe XslCompiledTransform
La classe <xref:System.Xml.Xsl.XslCompiledTransform> è il processore XSLT di Microsoft .NET Framework. Questa classe consente di compilare fogli di stile e di eseguire trasformazioni XSLT.  
  
> [!NOTE]
>  Sebbene le prestazioni complessive della classe <xref:System.Xml.Xsl.XslCompiledTransform> siano migliori rispetto alla classe <xref:System.Xml.Xsl.XslTransform>, l'esecuzione del metodo <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> della classe <xref:System.Xml.Xsl.XslCompiledTransform> potrebbe risultare più lenta di quella del metodo <xref:System.Xml.Xsl.XslTransform.Load%2A> della classe <xref:System.Xml.Xsl.XslTransform> la prima volta che tale metodo viene chiamato su una trasformazione. Questa situazione si verifica perché il file XSLT deve essere compilato prima del caricamento. Per ulteriori informazioni, vedere il post del blog: [XslCompiledTransform Slower che XslTransform?](http://go.microsoft.com/fwlink/?LinkId=130590)  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Input per la classe XslCompiledTransform](../../../../docs/standard/data/xml/inputs-to-the-xslcompiledtransform-class.md)  
 Vengono descritte le opzioni di input XSLT disponibili.  
  
 [Opzioni di output nella classe XslCompiledTransform](../../../../docs/standard/data/xml/output-options-on-the-xslcompiledtransform-class.md)  
 Vengono descritte le opzioni di output XSLT disponibili.  
  
 [Risolvere risorse esterne durante l'elaborazione XSLT](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 Viene descritto come usare la classe <xref:System.Xml.XmlResolver> per risolvere risorse esterne.  
  
 [Estensione di fogli di stile XSLT](../../../../docs/standard/data/xml/extending-xslt-style-sheets.md)  
 Viene descritto il supporto delle estensioni XSLT.  
  
|||  
|-|-|  
|[Errori XSLT risolvibili](../../../../docs/standard/data/xml/recoverable-xslt-errors.md)|Vengono elencati i comportamenti discretionary consentiti dalla raccomandazione W3C (World Wide Web Consortium) XSLT 1.0 e viene descritto il modo in cui tali comportamenti vengono gestiti dalla classe <xref:System.Xml.Xsl.XslCompiledTransform>.|  
|[Procedura: trasformare un frammento di nodo](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|Viene descritto come trasformare un frammento di nodo.|  
  
## <a name="related-sections"></a>Sezioni correlate  
 [La migrazione dalla classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 Viene descritto come migrare il codice dalla classe <xref:System.Xml.Xsl.XslTransform>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Xsl.XsltSettings>  
 <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>

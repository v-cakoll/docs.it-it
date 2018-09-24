---
title: Input di XmlDataDocument in XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: a0b536b6-cdb3-4a44-86c2-3b2ebc7bd4c9
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e7fb30104f36a565f4e6742c8f808c48e4ef39ec
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2018
ms.locfileid: "46696768"
---
# <a name="xmldatadocument-input-to-xsltransform"></a>Input di XmlDataDocument in XslTransform
> [!NOTE]
>  La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>. Per altre informazioni, vedere [Utilizzo della classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) e [Migrazione dalla classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Microsoft [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] implementa il DOM (Document Object Model) XML per fornire l'accesso ai dati nei documenti XML e nelle classi aggiuntive per scrivere, leggere e spostarsi all'interno dei documenti XML. Il tipo <xref:System.Xml.XmlDataDocument>, che si trova nello spazio dei nomi <xref:System.Xml>, fornisce un accesso relazionale ai dati poiché è in grado di sincronizzarsi con i dati relazionali nel tipo <xref:System.Data.DataSet>. È possibile visualizzare e modificare simultaneamente l'XML strutturato tramite la rappresentazione relazionale del tipo <xref:System.Data.DataSet> oppure è possibile modificare l'XML semistrutturato tramite la rappresentazione DOM del tipo <xref:System.Xml.XmlDataDocument>. Il tipo <xref:System.Xml.XmlDataDocument> supera quindi i limiti dei modelli basati sui dati XML e relazionali.  
  
 Se i dati sono archiviati in una struttura relazionale, per immetterli in una trasformazione XSLT, è possibile caricare i dati relazionali in un tipo <xref:System.Data.DataSet> e associarli al tipo  <xref:System.Xml.XmlDataDocument>. Il tipo <xref:System.Xml.XPath.XPathNavigator>, l'input per il tipo <xref:System.Xml.Xsl.XslTransform>, è implementato in un tipo <xref:System.Xml.XmlDataDocument> tramite l'interfaccia <xref:System.Xml.XPath.IXPathNavigable>. Ora è possibile eseguire trasformazioni XSLT sui dati relazionali caricandoli in un tipo <xref:System.Data.DataSet> e usando la sincronizzazione all'interno del tipo <xref:System.Xml.XmlDataDocument>.  
  
 Per altre informazioni sull'applicazione di una trasformazione ai dati relazionali, vedere [Applicazione di una trasformazione XSLT a un DataSet](../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.XmlDataDocument>  
- [Sincronizzazione di DataSet e XmlDataDocument](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
- [Trasformazioni XSLT con la classe XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
- [Implementazione del processore XSLT da parte della classe XslTransform](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
- [XPathNavigator nelle trasformazioni](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
- [XPathNodeIterator nelle trasformazioni](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
- [Input di XPathDocument in XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
- [Input di XmlDocument in XslTransform](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)

---
title: Utilizzo di schemi XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbbcc70c-bf9a-4f6a-af72-1bab5384a187
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e21d402dce02ecb332d041f0cda651df911979ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="working-with-xml-schemas"></a>Utilizzo di schemi XML
Per definire la struttura di un documento XML, oltre alle relazioni dei suoi elementi, i tipi di dati e i vincoli di contenuto, si usa una DTD (Document Type Definition, definizione del tipo di documento) o uno schema XSD (XML Schema Definition Language). Sebbene un documento XML venga considerato in formato corretto se soddisfa tutti i requisiti sintattici definiti dalla raccomandazione W3C (World Wide Web Consortium) Extensible Markup Language (XML) 1.0, non viene ritenuto valido a meno che non sia in formato corretto e conforme ai vincoli definiti dalla relativa DTD o dal relativo schema. Pertanto, anche se tutti i documenti XML validi sono in formato corretto, non tutti i documenti XML in formato corretto sono validi.  
  
 Per ulteriori informazioni su XML, vedere il [raccomandazione W3C XML 1.0](http://go.microsoft.com/fwlink/?linkid=7269). Per ulteriori informazioni sul XML Schema, vedere il [W3C XML Schema Part 1: Structures Recommendation](http://go.microsoft.com/fwlink/?linkid=48881) e [W3C XML Schema Part 2: Datatypes Recommendation](http://go.microsoft.com/fwlink/?linkid=17392) indicazioni.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [SOM (Schema Object Model) XML](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 Viene illustrato il modello SOM (Schema Object Model) nello spazio dei nomi <xref:System.Xml.Schema?displayProperty=nameWithType>, che fornisce un set di classi che consente di leggere lo schema XSD da un file oppure di creare a livello di codice uno schema in memoria.  
  
 [XmlSchemaSet per la compilazione dello Schema](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 Viene illustrata la classe <xref:System.Xml.Schema.XmlSchemaSet>, ovvero una cache in cui possono essere archiviati e convalidati gli schemi XSD.  
  
 [Convalida basata sul metodo Push di XmlSchemaValidator](../../../../docs/standard/data/xml/xmlschemavalidator-push-based-validation.md)  
 Viene illustrata la classe <xref:System.Xml.Schema.XmlSchemaValidator> che fornisce un meccanismo efficiente e a elevate prestazioni per la convalida basata sul metodo push di dati XML in base a schemi XSD.  
  
 [Deduzione di uno Schema XML](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)  
 Viene illustrato come usare la classe <xref:System.Xml.Schema.XmlSchemaInference> per inferire uno schema XSD dalla struttura di un documento XML.  
  
## <a name="reference"></a>Riferimento  
 <xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Convalida di un documento XML nel DOM](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
 Viene illustrato come convalidare il documento XML nel DOM (Document Object Model). È possibile convalidare il documento XML quando viene caricato nel DOM oppure convalidare un documento non convalidato in precedenza nel DOM.  
  
 [Convalida dello schema con XPathNavigator](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)  
 Viene illustrato come convalidare il documento XML esplorato e modificato usando la classe <xref:System.Xml.XPath.XPathNavigator>.

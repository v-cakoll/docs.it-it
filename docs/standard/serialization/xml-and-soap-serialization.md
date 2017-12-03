---
title: Serializzazione SOAP e XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d5b89392801e7cf85fcda121a86d0bda4e7ac18
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="xml-and-soap-serialization"></a>Serializzazione SOAP e XML
La serializzazione XML converte (serializza) le proprietà e i campi pubblici di un oggetto, o i parametri e i valori restituiti dei metodi, in un flusso XML conforme a uno specifico documento in linguaggio XSD (XML Schema Definition). La serializzazione XML produce classi fortemente tipizzate con campi e proprietà pubbliche convertiti in un formato seriale (in questo caso XML) per l'archiviazione o il trasporto.  
  
 Dal momento che XML è uno standard aperto, il flusso XML può essere elaborato da qualsiasi applicazione, in base alle necessità, indipendentemente dalla piattaforma. Ad esempio, i servizi Web XML creati tramite ASP.NET, utilizzano la classe <xref:System.Xml.Serialization.XmlSerializer> per creare flussi XML che passano dati tra applicazioni del servizio Web XML tramite Internet o sulle Intranet. Al contrario, la deserializzazione prende tale flusso XML e ricostruisce l'oggetto.  
  
 La serializzazione XML può essere utilizzata anche per serializzare oggetti nei flussi XML conformi alla specifica SOAP. Il SOAP è un protocollo basato su XML, specificamente progettato per trasportare chiamate di routine mediante XML.  
  
 Per serializzare o deserializzare oggetti, utilizzare la classe <xref:System.Xml.Serialization.XmlSerializer>. Per creare le classi da serializzare, utilizzare lo strumento XML Schema Definition.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Introduzione alla serializzazione XML](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 Fornisce una definizione generale di serializzazione, in modo particolare della serializzazione XML.  
  
 [Procedura: Serializzare un oggetto](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 Vengono fornite istruzioni dettagliate per la serializzazione di un oggetto.  
  
 [Procedura: Deserializzare un oggetto](../../../docs/standard/serialization/how-to-deserialize-an-object.md)  
 Vengono fornite istruzioni dettagliate per la deserializzazione di un oggetto.  
  
 [Esempi di serializzazione XML](../../../docs/standard/serialization/examples-of-xml-serialization.md)  
 Fornisce esempi che dimostrano le funzioni di base della serializzazione XML.  
  
 [Strumento XML Schema Definition e serializzazione XML](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)  
 Descrive come utilizzare lo strumento XML Schema Definition per creare classi conformi a un determinato schema XSD (XML Schema Definition) o generare uno schema XML da un file dll.  
  
 [Controllo della serializzazione XML mediante attributi](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)  
 Descrive come controllare la serializzazione tramite l'utilizzo di attributi.  
  
 [Attributi per il controllo della serializzazione XML](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md)  
 Elenca gli attributi utilizzati per il controllo della serializzazione XML.  
  
 [Procedura: Specificare un nome di elemento alternativo per un flusso XML](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
 Presenta uon scenario avanzato in cui viene illustrato come generare più flussi XML eseguendo l'override della serializzazione.  
  
 [Procedura: Controllare la serializzazione delle classi derivate](../../../docs/standard/serialization/how-to-control-serialization-of-derived-classes.md)  
 Viene fornito un esempio in cui viene illustrato come controllare la serializzazione di classi derivate.  
  
 [Procedura: Qualificare nomi di attributi ed elementi XML](../../../docs/standard/serialization/how-to-qualify-xml-element-and-xml-attribute-names.md)  
 Descrive come definire e controllare il modo in cui gli spazi dei nomi XML vengono utilizzati nel flusso XML.  
  
 [Serializzazione XML con Servizi Web XML](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)  
 Spiega in che modo la serializzazione XML viene utilizzata nei servizi Web XML.  
  
 [Procedura: Serializzare un oggetto come flusso XML con codifica SOAP](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
 Descrive come utilizzare la classe <xref:System.Xml.Serialization.XmlSerializer> per creare flussi XML SOAP codificati conformi alla sezione 5 del documento intitolato "Simple Object Access Protocol (SOAP) 1.1" del World Wide Web Consortium (www.w3.org).  
  
 [Procedura: Eseguire l'override della serializzazione XML con codifica SOAP](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)  
 Descrive il processo per l'esecuzione dell'override della serializzazione XML di oggetti come messaggi SOAP.  
  
 [Attributi per il controllo della serializzazione SOAP codificata](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)  
 Elenca gli attributi utilizzati per il controllo della serializzazione con codifica SOAP.  
  
 [Elemento \<system.xml.serialization>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 La configurazione di primo livello per il controllo della serializzazione XML.  
  
 [Elemento \<dateTimeSerialization>](../../../docs/standard/serialization/datetimeserialization-element.md)  
 Controlla la modalità della serializzazione di oggetti <xref:System.DateTime>.  
  
 [Elemento \<schemaImporterExtensions>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
 Contiene i tipi usati dalla classe <xref:System.Xml.Serialization.XmlSchemaImporter>.  
  
 [Elemento \<add> per \<xmlSchemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)  
 Aggiunge i tipi usati dalla classe <xref:System.Xml.Serialization.XmlSchemaImporter>.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Advanced Development Technologies](http://msdn.microsoft.com/en-us/c4a7e341-f0c6-4df4-a74f-223387ac6e4e) (Tecnologie di sviluppo avanzate)  
 Sono riportati collegamenti per accedere a ulteriori informazioni sulle tecniche e sulle attività di sviluppo avanzate in .NET Framework.  
  
 [Servizi Web XML creati mediante ASP.NET e tramite client di servizi Web XML](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c)  
 Fornisce gli argomenti che descrivono e spiegano come programmare i servizi Web XML con ASP.NET.  
  
## <a name="see-also"></a>Vedere anche  
 [Serializzazione binaria](../../../docs/standard/serialization/binary-serialization.md)

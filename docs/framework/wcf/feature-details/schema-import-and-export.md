---
title: Importazione ed esportazione degli schemi
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, schema import and export
- XsdDataContractExporter class
- XsdDataContractImporter class
ms.assetid: 0da32b50-ccd9-463a-844c-7fe803d3bf44
ms.openlocfilehash: 942ade69d92d8a213f65a3a2e463b6924e2f986e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590215"
---
# <a name="schema-import-and-export"></a>Importazione ed esportazione degli schemi
Windows Communication Foundation (WCF) include un nuovo motore di serializzazione, ovvero <xref:System.Runtime.Serialization.DataContractSerializer> . Il viene `DataContractSerializer` convertito tra .NET Framework oggetti e XML (in entrambe le direzioni). Oltre al serializzatore, WCF include meccanismi di importazione dello schema e di esportazione dello schema associati. *Schema* è una descrizione formale, precisa e leggibile dal computer della forma del codice XML prodotto dal serializzatore o a cui il deserializzatore può accedere. WCF utilizza il linguaggio XSD (XML Schema Definition) World Wide Web Consortium (W3C) come rappresentazione dello schema, che è ampiamente interoperabile con numerose piattaforme di terze parti.  
  
 Il componente di importazione dello schema, <xref:System.Runtime.Serialization.XsdDataContractImporter> , accetta un documento dello schema XSD e genera .NET Framework classi, in genere classi del contratto dati, in modo che i form serializzati corrispondano allo schema specificato.  
  
 Si consideri ad esempio il frammento di schema seguente:  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
 genera il tipo seguente (leggermente semplificato per una migliore leggibilità)  
  
 [!code-csharp[c_SchemaImportExport#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#1)]
 [!code-vb[c_SchemaImportExport#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#1)]  
  
 Si noti che il tipo generato segue alcune procedure consigliate per i contratti dati (disponibili in [procedure consigliate: controllo delle versioni dei contratti dati](../best-practices-data-contract-versioning.md)):  
  
- Il tipo implementa l'interfaccia <xref:System.Runtime.Serialization.IExtensibleDataObject>. Per altre informazioni, vedere [Contratti di dati compatibili con versioni successive](forward-compatible-data-contracts.md).  
  
- I membri dati vengono implementati come proprietà pubbliche che incapsulano campi privati.  
  
- La classe è una classe parziale e le aggiunte possono essere eseguite senza modificare il codice generato.  
  
 La classe <xref:System.Runtime.Serialization.XsdDataContractExporter> consente di eseguire l'inverso, ovvero considera i tipi serializzabili con `DataContractSerializer` e genera un documento dello schema XSD.  
  
## <a name="fidelity-is-not-guaranteed"></a>Fedeltà non garantita   
 Non è garantito che lo schema o i tipi eseguano un round trip con fedeltà assoluta Un *round trip* significa importare uno schema per creare un set di classi ed esportare il risultato per creare di nuovo uno schema. Lo stesso schema non può essere restituito. Anche per l'inversione del processo non è garantito il mantenimento della fedeltà (quando si esporta un tipo per generare lo schema e quindi si importa di nuovo il tipo, è improbabile che venga restituito lo stesso tipo).  
  
## <a name="supported-types"></a>Tipi supportati  
 Il modello del contratto dati supporta solo un sottoinsieme limitato dello schema WC3. Qualsiasi schema che non è conforme a tale sottoinsieme genererà un'eccezione durante il processo di importazione. Ad esempio, non esiste alcun sistema per specificare che un membro dati di un contratto dati debba essere serializzato come attributo XML. Di conseguenza, gli schemi che richiedono l'utilizzo di attributi XML non sono supportati e verranno generate eccezioni durante l'importazione, poiché è impossibile generare un contratto dati con la proiezione XML corretta.  
  
 Ad esempio, non è possibile importare il frammento di schema seguente utilizzando le impostazioni di importazione predefinite.  
  
 [!code-xml[c_SchemaImportExport#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#9)]  
  
 Per ulteriori informazioni, vedere [riferimento allo schema del contratto dati](data-contract-schema-reference.md). Se un schema non è conforme alle regole del contratto dati, utilizzare un motore di serializzazione diverso. Ad esempio, la classe <xref:System.Xml.Serialization.XmlSerializer> utilizza un proprio meccanismo separato di importazione dello schema. È inoltre disponibile una modalità di importazione speciale in cui l'intervallo dello schema supportato viene espanso. Per ulteriori informazioni, vedere la sezione relativa alla generazione di <xref:System.Xml.Serialization.IXmlSerializable> tipi in [importazione dello schema per la generazione di classi](importing-schema-to-generate-classes.md).  
  
 `XsdDataContractExporter`Supporta tutti i tipi di .NET Framework che possono essere serializzati con `DataContractSerializer` . Per ulteriori informazioni, vedere [tipi supportati dal serializzatore di contratti dati](types-supported-by-the-data-contract-serializer.md). Si noti che lo schema generato utilizzando `XsdDataContractExporter` consiste solitamente di dati validi che possono essere utilizzati da `XsdDataContractImporter`, a meno che non si utilizzi la classe <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> per personalizzare lo schema.  
  
 Per ulteriori informazioni sull'utilizzo di <xref:System.Runtime.Serialization.XsdDataContractImporter> , vedere [importazione dello schema per la generazione di classi](importing-schema-to-generate-classes.md).  
  
 Per ulteriori informazioni sull'utilizzo di <xref:System.Runtime.Serialization.XsdDataContractExporter> , vedere [esportazione di schemi dalle classi](exporting-schemas-from-classes.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- <xref:System.Runtime.Serialization.XsdDataContractExporter>
- [Importazione dello schema per generare classi](importing-schema-to-generate-classes.md)
- [Esportazione di schemi da classi](exporting-schemas-from-classes.md)

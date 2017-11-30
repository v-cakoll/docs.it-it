---
title: Attraversamento di schemi XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
ms.assetid: cce69574-5861-4a30-b730-2e18d915d8ee
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cc1883e8503567bdf2f6e0bda20cea777a12c7cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="traversing-xml-schemas"></a>Attraversamento di schemi XML
L'attraversamento di uno schema XML mediante l'API del modello SOM (Schema Object Model) consente di accedere a elementi, attributi e tipi archiviati nel modello SOM. Tale attraversamento rappresenta inoltre il primo passaggio per la modifica di uno schema XML tramite l'API del modello SOM.  
  
## <a name="traversing-an-xml-schema"></a>Attraversamento di uno schema XML  
 Le seguenti proprietà della classe <xref:System.Xml.Schema.XmlSchema> forniscono l'accesso alla raccolta degli elementi globali aggiunti a XML Schema.  
  
|Proprietà|Tipo di oggetto archiviato nella raccolta o nella matrice|  
|--------------|---------------------------------------------------|  
|<xref:System.Xml.Schema.XmlSchema.Elements%2A>|<xref:System.Xml.Schema.XmlSchemaElement>|  
|<xref:System.Xml.Schema.XmlSchema.Attributes%2A>|<xref:System.Xml.Schema.XmlSchemaAttribute>|  
|<xref:System.Xml.Schema.XmlSchema.AttributeGroups%2A>|<xref:System.Xml.Schema.XmlSchemaAttributeGroup>|  
|<xref:System.Xml.Schema.XmlSchema.Groups%2A>|<xref:System.Xml.Schema.XmlSchemaGroup>|  
|<xref:System.Xml.Schema.XmlSchema.Includes%2A>|<xref:System.Xml.Schema.XmlSchemaExternal>, <xref:System.Xml.Schema.XmlSchemaInclude>, <xref:System.Xml.Schema.XmlSchemaImport> o <xref:System.Xml.Schema.XmlSchemaRedefine>|  
|<xref:System.Xml.Schema.XmlSchema.Items%2A>|<xref:System.Xml.Schema.XmlSchemaObject> (fornisce l'accesso a elementi, attributi e tipi a livello globale).|  
|<xref:System.Xml.Schema.XmlSchema.Notations%2A>|<xref:System.Xml.Schema.XmlSchemaNotation>|  
|<xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A>|<xref:System.Xml.Schema.XmlSchemaType>, <xref:System.Xml.Schema.XmlSchemaSimpleType>, <xref:System.Xml.Schema.XmlSchemaComplexType>|  
|<xref:System.Xml.Schema.XmlSchema.UnhandledAttributes%2A>|<xref:System.Xml.XmlAttribute> (fornisce l'accesso agli attributi che non appartengono allo spazio dei nomi dello schema).|  
  
> [!NOTE]
>  Tutte le proprietà elencate nella precedente tabella, a eccezione della proprietà <xref:System.Xml.Schema.XmlSchema.Items%2A>, sono proprietà PSCI (Post-Schema-Compilation-Infoset) che non sono disponibili fino a quando lo schema non è stato compilato. La proprietà <xref:System.Xml.Schema.XmlSchema.Items%2A> è una proprietà precedente alla compilazione dello schema che può essere usata prima che lo schema venga compilato per accedere e apportare modifiche a elementi, attributi e tipi a livello globale.  
>   
>  La proprietà <xref:System.Xml.Schema.XmlSchema.UnhandledAttributes%2A> fornisce l'accesso agli attributi che non appartengono allo spazio dei nomi dello schema. Tali attributi non vengono elaborati dal processore dello schema.  
  
 L'esempio di codice che segue viene illustrato come attraversare lo schema del cliente creato nel [compilazione di schemi XML](../../../../docs/standard/data/xml/building-xml-schemas.md) argomento. Nell'esempio di codice viene eseguito l'attraversamento dello schema usando le raccolte descritte in precedenza e tutti gli elementi e attributi dello schema vengono scritti nella console.  
  
 L'esempio consente di attraversare lo schema del cliente eseguendo i passaggi seguenti.  
  
1.  Aggiunge lo schema del cliente a un nuovo oggetto <xref:System.Xml.Schema.XmlSchemaSet>, quindi lo compila. Eventuali avvisi ed errori di convalida dello schema rilevati durante la lettura e la compilazione dello schema vengono gestiti dal delegato <xref:System.Xml.Schema.ValidationEventHandler>.  
  
2.  Recupera l'oggetto <xref:System.Xml.Schema.XmlSchema> compilato dal tipo <xref:System.Xml.Schema.XmlSchemaSet> scorrendo la proprietà <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>. Dal momento che lo schema è stato compilato, è possibile accedere alle proprietà di PSCI (Post-Schema-Compilation-Infoset).  
  
3.  Scorre ciascun tipo <xref:System.Xml.Schema.XmlSchemaElement> nella raccolta <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A> della raccolta <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> successiva alla compilazione dello schema e scrive il nome di ciascun elemento nella console.  
  
4.  Ottiene il tipo complesso dell'elemento `Customer` usando la classe <xref:System.Xml.Schema.XmlSchemaComplexType>.  
  
5.  Se il tipo complesso dispone di attributi, ottiene un tipo <xref:System.Collections.IDictionaryEnumerator> per enumerare ciascun tipo <xref:System.Xml.Schema.XmlSchemaAttribute> e scrive il relativo nome nella console.  
  
6.  Ottiene la particella di sequenza del tipo complesso usando la classe <xref:System.Xml.Schema.XmlSchemaSequence>.  
  
7.  Scorre ciascun tipo <xref:System.Xml.Schema.XmlSchemaElement> nella raccolta <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType> e scrive il nome di ciascun elemento figlio nella console.  
  
 Di seguito è riportato l'esempio di codice completo.  
  
 [!code-cpp[XmlSchemaTraverseExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaTraverseExample/CPP/XmlSchemaTraverseExample.cpp#1)]
 [!code-csharp[XmlSchemaTraverseExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaTraverseExample/CS/XmlSchemaTraverseExample.cs#1)]
 [!code-vb[XmlSchemaTraverseExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaTraverseExample/VB/XmlSchemaTraverseExample.vb#1)]  
  
 Se è un tipo semplice o un tipo complesso definito dall'utente, il tipo della proprietà <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A?displayProperty=nameWithType> può essere <xref:System.Xml.Schema.XmlSchemaSimpleType> o <xref:System.Xml.Schema.XmlSchemaComplexType>. Se è uno dei tipi di dati incorporati definiti nella raccomandazione W3C relativa agli schemi XML, il tipo della proprietà può essere anche <xref:System.Xml.Schema.XmlSchemaDatatype>. Nello schema del cliente, il tipo della proprietà <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> dell'elemento `Customer` è <xref:System.Xml.Schema.XmlSchemaComplexType> e il tipo degli elementi `FirstName` e `LastName` è <xref:System.Xml.Schema.XmlSchemaSimpleType>.  
  
 Nell'esempio di codice il [compilazione di schemi XML](../../../../docs/standard/data/xml/building-xml-schemas.md) argomento utilizzato il <xref:System.Xml.Schema.XmlSchemaComplexType.Attributes%2A?displayProperty=nameWithType> raccolta a cui aggiungere l'attributo `CustomerId` per il `Customer` elemento. Questa è una proprietà precedente alla compilazione dello schema. La proprietà PSCI corrispondente è la raccolta <xref:System.Xml.Schema.XmlSchemaComplexType.AttributeUses%2A?displayProperty=nameWithType>, che contiene tutti gli attributi del tipo complesso, inclusi quelli ereditati tramite una derivazione del tipo.  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica del modello a oggetti dello Schema XML](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)  
 [Lettura e scrittura di schemi XML](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)  
 [Compilazione di schemi XML](../../../../docs/standard/data/xml/building-xml-schemas.md)  
 [Modifica di schemi XML](../../../../docs/standard/data/xml/editing-xml-schemas.md)  
 [Inclusione o importazione di schemi XML](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)  
 [XmlSchemaSet per la compilazione dello Schema](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 [Post-Schema Compilation Infoset](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)

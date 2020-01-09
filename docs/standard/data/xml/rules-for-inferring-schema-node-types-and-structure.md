---
title: Regole per l'inferenza dello schema per tipi di nodo e struttura
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d74ce896-717d-4871-8fd9-b070e2f53cb0
ms.openlocfilehash: 6d66384dea7018bcc3b2dd8fde96f4fa2653f8e8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710245"
---
# <a name="rules-for-inferring-schema-node-types-and-structure"></a>Regole per l'inferenza dello schema per tipi di nodo e struttura
In questo argomento viene descritto in che modo il processo di inferenza converte in una struttura XSD (XML Schema Definition Language) i tipi di nodo di un documento XML.  
  
## <a name="element-inference-rules"></a>Regole di inferenza dell'elemento  
 Contenuto della sezione vengono descritte le regole di inferenza per le dichiarazioni dell'elemento. Vengono inferite otto strutture di dichiarazioni dell'elemento:  
  
1. Elemento di tipo semplice  
  
2. Elemento vuoto  
  
3. Elemento vuoto con attributi  
  
4. Elemento con attributi e contenuto semplice  
  
5. Elemento con una sequenza di elementi figlio  
  
6. Elemento con una sequenza di elementi figlio e attributi  
  
7. Elemento con una sequenza di opzioni di elementi figlio  
  
8. Elemento con una sequenza di opzioni di elementi figlio e attributi  
  
> [!NOTE]
> Tutte le dichiarazioni `complexType` sono inferite come tipi anonimi. L'unico elemento globale inferito è l'elemento radice, tutti gli altri elementi sono locali.  
  
 Per ulteriori informazioni sul processo di inferenza dello schema, vedere [Inferenza degli schemi da documenti XML](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
### <a name="simple-typed-element"></a>Elemento di tipo semplice  
 Nella tabella seguente viene mostrato l'input XML nel metodo <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> e lo schema XML generato. L'elemento in grassetto mostra lo schema inferito per l'elemento di tipo semplice.  
  
 Per ulteriori informazioni sul processo di inferenza dello schema, vedere [Inferenza degli schemi da documenti XML](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>text</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root" type="xs:string" />`<br /><br /> `</xs:schema>`|  
  
### <a name="empty-element"></a>Elemento vuoto  
 Nella tabella seguente viene mostrato l'input XML nel metodo <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> e lo schema XML generato. L'elemento in grassetto mostra lo schema inferito per l'elemento vuoto.  
  
 Per ulteriori informazioni sul processo di inferenza dello schema, vedere [Inferenza degli schemi da documenti XML](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="empty" />`<br /><br /> `</xs:schema>`|  
  
### <a name="empty-element-with-attributes"></a>Elemento vuoto con attributi  
 Nella tabella seguente viene mostrato l'input XML nel metodo <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> e lo schema XML generato. L'elemento in grassetto mostra lo schema inferito per l'elemento vuoto con attributi.  
  
 Per ulteriori informazioni sul processo di inferenza dello schema, vedere [Inferenza degli schemi da documenti XML](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty attribute1="text"/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="empty">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-attributes-and-simple-content"></a>Elemento con attributi e contenuto semplice  
 Nella tabella seguente viene mostrato l'input XML nel metodo <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> e lo schema XML generato. Gli elementi in grassetto mostrano lo schema inferito per un elemento con attributi e contenuto semplice.  
  
 Per ulteriori informazioni sul processo di inferenza dello schema, vedere [Inferenza degli schemi da documenti XML](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">value</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:simpleContent>`<br /><br /> `<xs:extension base="xs:string">`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:extension>`<br /><br /> `</xs:simpleContent>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-of-child-elements"></a>Elemento con una sequenza di elementi figlio  
 Nella tabella seguente viene mostrato l'input XML nel metodo <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> e lo schema XML generato. Gli elementi in grassetto mostrano lo schema inferito per un elemento con una sequenza di elementi figlio.  
  
> [!NOTE]
> Anche se un elemento contiene solo un elemento figlio, viene ancora considerato come una sequenza.  
  
 Per ulteriori informazioni sul processo di inferenza dello schema, vedere [Inferenza degli schemi da documenti XML](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:element name="subElement" />`<br /><br /> `</xs:sequence>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-of-child-elements-and-attributes"></a>Elemento con una sequenza di elementi figlio e attributi  
 Nella tabella seguente viene mostrato l'input XML nel metodo <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> e lo schema XML generato. Gli elementi in grassetto mostrano lo schema inferito per un elemento con una sequenza di elementi figlio e attributi.  
  
> [!NOTE]
> Anche se un elemento contiene solo un elemento figlio, viene ancora considerato come una sequenza.  
  
 Per ulteriori informazioni sul processo di inferenza dello schema, vedere [Inferenza degli schemi da documenti XML](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:sequence>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-and-choices-of-child-elements"></a>Elemento con una sequenza e opzioni di elementi figlio  
 Nella tabella seguente viene mostrato l'input XML nel metodo <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> e lo schema XML generato. Gli elementi in grassetto mostrano lo schema inferito per un elemento con una sequenza e opzione di elementi figlio.  
  
> [!NOTE]
> L'attributo `maxOccurs` dell'elemento `xs:choice` è impostato su `"unbounded"` nello schema inferito.  
  
 Per ulteriori informazioni sul processo di inferenza dello schema, vedere [Inferenza degli schemi da documenti XML](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:choice maxOccurs="unbounded">`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:choice>`<br /><br /> `</xs:sequence>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-and-choice-of-child-elements-and-attributes"></a>Elemento con una sequenza e opzione di elementi figlio e attributi  
 Nella tabella seguente viene mostrato l'input XML nel metodo <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> e lo schema XML generato. Gli elementi in grassetto mostrano lo schema inferito per un elemento con una sequenza e opzione di elementi figlio e attributi.  
  
> [!NOTE]
> L'attributo `maxOccurs` dell'elemento `xs:choice` è impostato su `"unbounded"` nello schema inferito.  
  
 Per ulteriori informazioni sul processo di inferenza dello schema, vedere [Inferenza degli schemi da documenti XML](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:choice maxOccurs="unbounded">`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:choice>`<br /><br /> `</xs:sequence>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="attribute-processing"></a>Elaborazione degli attributi  
 Ogni volta che in un nodo viene rilevato un nuovo attributo, questo viene aggiunto alla definizione inferita del nodo con `use="required"`. Al successivo rilevamento dello stesso nodo nell'istanza, il processo di inferenza confronterà gli attributi dell'istanza corrente con quelli già inferiti. Se mancano alcuni nodi già inferiti nell'istanza, `use="optional"` viene aggiunto alla definizione dell'attributo. I nuovo attributi vengono aggiunti alle dichiarazioni esistenti con `use="optional"`.  
  
### <a name="occurrence-constraints"></a>Vincoli di occorrenza  
 Durante il processo di inferenza dello schema, vengono generati gli attributi `minOccurs` e `maxOccurs`, per i componenti inferiti di uno schema, con valori uguali a `"0"` o `"1"` e `"1"` o `"unbounded"`. I valori `"1"` e `"unbounded"` sono usati solo quando i valori `"0"` e `"1"` non sono in grado di convalidare il documento XML (ad esempio, se `MinOccurs="0"` non descrive con precisione un elemento, si utilizzerà `minOccurs="1"`).  
  
### <a name="mixed-content"></a>Contenuto misto  
 Se in un elemento è presente contenuto misto (ad esempio del testo frammisto a elementi), viene generato l'attributo `mixed="true"` per la definizione del tipo complesso inferito.  
  
## <a name="other-node-type-inference-rules"></a>Altre regole di inferenza del tipo di nodo  
 Nella tabella seguente vengono descritte le regole di inferenza per istruzioni di elaborazione, commenti, riferimenti all'entità, CDATA, tipo di documento e nodi dello spazio dei nomi.  
  
|Tipo di nodo|Conversione|  
|---------------|-----------------|  
|Istruzione di elaborazione|Ignorato.|  
|Commento|Ignorato.|  
|Riferimento all'entità|La classe <xref:System.Xml.Schema.XmlSchemaInference> non gestisce i riferimenti all'entità. Se un documento XML contiene riferimenti all'entità, è necessario usare un lettore che espande le entità. Ad esempio, è possibile passare un tipo <xref:System.Xml.XmlTextReader> con la proprietà <xref:System.Xml.XmlTextReader.EntityHandling%2A> impostata su <xref:System.Xml.EntityHandling.ExpandEntities> come parametro. Se si rilevano riferimenti all'entità che il lettore non espande, viene generata un'eccezione.|  
|CDATA|Le sezioni `<![CDATA[ … ]]` di un documento XML verranno inferite come `xs:string`.|  
|Tipo di documento|Ignorato.|  
|Spazi dei nomi|Ignorato.|  
  
 Per ulteriori informazioni sul processo di inferenza dello schema, vedere [Inferenza degli schemi da documenti XML](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Schema.XmlSchemaInference>
- [SOM (Schema Object Model) XML](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)
- [Inferenza di uno schema XML](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)
- [Inferenza degli schemi da documenti XML](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)
- [Regole per l'inferenza di tipi semplici](../../../../docs/standard/data/xml/rules-for-inferring-simple-types.md)

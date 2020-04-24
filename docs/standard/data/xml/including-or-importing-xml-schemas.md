---
title: Inclusione o importazione di schemi XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: fe1b4a11-37f4-4e1a-93c9-239f4fe736c0
ms.openlocfilehash: d9a18876d8a5ba3067aa35c617b1e20fce0411f5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710778"
---
# <a name="including-or-importing-xml-schemas"></a><span data-ttu-id="21d04-102">Inclusione o importazione di schemi XML</span><span class="sxs-lookup"><span data-stu-id="21d04-102">Including or Importing XML Schemas</span></span>
<span data-ttu-id="21d04-103">Uno schema XML può contenere elementi `<xs:import />`, `<xs:include />` e `<xs:redefine />`.</span><span class="sxs-lookup"><span data-stu-id="21d04-103">An XML schema may contain `<xs:import />`, `<xs:include />`, and `<xs:redefine />` elements.</span></span> <span data-ttu-id="21d04-104">Questi elementi dello schema fanno riferimento ad altri schemi XML che possono essere usati per integrare la struttura dello schema che li include o importa.</span><span class="sxs-lookup"><span data-stu-id="21d04-104">These schema elements refer to other XML schemas that can be used to supplement the structure of the schema that includes or imports them.</span></span> <span data-ttu-id="21d04-105">Nell'API del modello SOM (Schema Object Model), a questi elementi sono associate le classi <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> e <xref:System.Xml.Schema.XmlSchemaRedefine>.</span><span class="sxs-lookup"><span data-stu-id="21d04-105">The <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> and <xref:System.Xml.Schema.XmlSchemaRedefine> classes, map to these elements in the Schema Object Model (SOM) API.</span></span>  
  
## <a name="including-or-importing-an-xml-schema"></a><span data-ttu-id="21d04-106">Inclusione o importazione di uno schema XML</span><span class="sxs-lookup"><span data-stu-id="21d04-106">Including or Importing an XML Schema</span></span>  
 <span data-ttu-id="21d04-107">L'esempio di codice seguente integra lo schema del cliente creato nell'argomento [Compilazione di XML Schema](../../../../docs/standard/data/xml/building-xml-schemas.md) con lo schema dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="21d04-107">The following code example supplements the customer schema created in the [Building XML Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md) topic with the address schema.</span></span> <span data-ttu-id="21d04-108">L'integrazione dello schema del cliente con lo schema dell'indirizzo rende disponibili i tipi di indirizzo nello schema del cliente.</span><span class="sxs-lookup"><span data-stu-id="21d04-108">Supplementing the customer schema with the address schema makes address types available in the customer schema.</span></span>  
  
 <span data-ttu-id="21d04-109">È possibile incorporare lo schema dell'indirizzo mediante l'elemento `<xs:include />` o `<xs:import />` per usare i componenti dello schema dell'indirizzo senza apportarvi modifiche oppure mediante un elemento `<xs:redefine />` per modificare i componenti in modo che soddisfino le esigenze dello schema del cliente.</span><span class="sxs-lookup"><span data-stu-id="21d04-109">The address schema can be incorporated using either `<xs:include />` or `<xs:import />` elements to use the components of the address schema as-is, or using an `<xs:redefine />` element to modify any of its components to suit the need of the customer schema.</span></span> <span data-ttu-id="21d04-110">Poiché nello schema dell'indirizzo `targetNamespace` è diverso da quello dello schema del cliente, vengono usati l'elemento `<xs:import />` e quindi la semantica di importazione.</span><span class="sxs-lookup"><span data-stu-id="21d04-110">Because the address schema has a `targetNamespace` that is different from that of the customer schema, the `<xs:import />` element and therefore import semantics is used.</span></span>  
  
 <span data-ttu-id="21d04-111">L'esempio di codice consente di includere lo schema dell'indirizzo eseguendo i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="21d04-111">The code example includes the address schema in the following steps.</span></span>  
  
1. <span data-ttu-id="21d04-112">Aggiunge lo schema del cliente e lo schema dell'indirizzo a un nuovo oggetto <xref:System.Xml.Schema.XmlSchemaSet>, quindi li compila.</span><span class="sxs-lookup"><span data-stu-id="21d04-112">Adds the customer schema and the address schema to a new <xref:System.Xml.Schema.XmlSchemaSet> object and then compiles them.</span></span> <span data-ttu-id="21d04-113">Eventuali avvisi ed errori di convalida dello schema rilevati durante la lettura e la compilazione degli schemi vengono gestiti dal delegato <xref:System.Xml.Schema.ValidationEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="21d04-113">Any schema validation warnings and errors encountered reading or compiling the schemas are handled by the <xref:System.Xml.Schema.ValidationEventHandler> delegate.</span></span>  
  
2. <span data-ttu-id="21d04-114">Recupera gli oggetti <xref:System.Xml.Schema.XmlSchema> compilati per gli schemi del cliente e dell'indirizzo dal tipo <xref:System.Xml.Schema.XmlSchemaSet> scorrendo la proprietà <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>.</span><span class="sxs-lookup"><span data-stu-id="21d04-114">Retrieves the compiled <xref:System.Xml.Schema.XmlSchema> objects for both the customer and address schemas from the <xref:System.Xml.Schema.XmlSchemaSet> by iterating over the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property.</span></span> <span data-ttu-id="21d04-115">Dal momento che gli schemi sono stati compilati, è possibile accedere alle proprietà del set PSCI (Post-Schema-Compilation-Infoset).</span><span class="sxs-lookup"><span data-stu-id="21d04-115">Because the schemas are compiled, Post-Schema-Compilation-Infoset (PSCI) properties are accessible.</span></span>  
  
3. <span data-ttu-id="21d04-116">Crea un oggetto <xref:System.Xml.Schema.XmlSchemaImport>, imposta la proprietà <xref:System.Xml.Schema.XmlSchemaImport.Namespace%2A> dell'elemento import sullo spazio dei nomi dello schema dell'indirizzo, imposta la proprietà <xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A> dell'elemento import sull'oggetto <xref:System.Xml.Schema.XmlSchema> dello schema dell'indirizzo e aggiunge l'elemento import alla proprietà <xref:System.Xml.Schema.XmlSchema.Includes%2A> dello schema del cliente.</span><span class="sxs-lookup"><span data-stu-id="21d04-116">Creates an <xref:System.Xml.Schema.XmlSchemaImport> object, sets the <xref:System.Xml.Schema.XmlSchemaImport.Namespace%2A> property of the import to the namespace of the address schema, sets the <xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A> property of the import to the <xref:System.Xml.Schema.XmlSchema> object of the address schema, and adds the import to the <xref:System.Xml.Schema.XmlSchema.Includes%2A> property of the customer schema.</span></span>  
  
4. <span data-ttu-id="21d04-117">Rielabora e compila l'oggetto modificato <xref:System.Xml.Schema.XmlSchema> dello schema del cliente usando i metodi <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> e <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> della classe <xref:System.Xml.Schema.XmlSchemaSet> e lo scrive nella console.</span><span class="sxs-lookup"><span data-stu-id="21d04-117">Reprocesses and compiles the modified <xref:System.Xml.Schema.XmlSchema> object of the customer schema using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> and <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet> class and writes it to the console.</span></span>  
  
5. <span data-ttu-id="21d04-118">Infine, usando la proprietà <xref:System.Xml.Schema.XmlSchema.Includes%2A> dello schema del cliente, scrive in modo ricorsivo nella console tutti gli schemi importati nello schema del cliente.</span><span class="sxs-lookup"><span data-stu-id="21d04-118">Finally, recursively writes all of the schemas imported into the customer schema to the console using the <xref:System.Xml.Schema.XmlSchema.Includes%2A> property of the customer schema.</span></span> <span data-ttu-id="21d04-119">La proprietà <xref:System.Xml.Schema.XmlSchema.Includes%2A> fornisce l'accesso a tutti gli elementi include, import o redefine aggiunti a uno schema.</span><span class="sxs-lookup"><span data-stu-id="21d04-119">The <xref:System.Xml.Schema.XmlSchema.Includes%2A> property provides access to all the includes, imports, or redefines added to a schema.</span></span>  
  
 <span data-ttu-id="21d04-120">Di seguito è riportato l'esempio di codice completo e gli schemi del cliente e dell'indirizzo scritti nella console.</span><span class="sxs-lookup"><span data-stu-id="21d04-120">The following is the complete code example and the customer and address schemas written to the console.</span></span>  
  
 [!code-cpp[XmlSchemaImportExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaImportExample/CPP/XmlSchemaImportExample.cpp#1)]
 [!code-csharp[XmlSchemaImportExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaImportExample/CS/XmlSchemaImportExample.cs#1)]
 [!code-vb[XmlSchemaImportExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaImportExample/VB/XmlSchemaImportExample.vb#1)]  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:import namespace="http://www.example.com/IPO" />  
  <xs:element name="Customer">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="FirstName" type="xs:string" />  
        <xs:element name="LastName" type="tns:LastNameType" />  
      </xs:sequence>  
      <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" />  
    </xs:complexType>  
  </xs:element>  
  <xs:simpleType name="LastNameType">  
    <xs:restriction base="xs:string">  
      <xs:maxLength value="20" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
<schema targetNamespace="http://www.example.com/IPO" xmlns="http://www.w3.org/2001/XMLSchema" xmlns:ipo="http://www.example.com/IPO">  
  <annotation>  
    <documentation xml:lang="en">  
      Addresses for International Purchase order schema  
      Copyright 2000 Example.com. All rights reserved.  
    </documentation>  
  </annotation>  
  <complexType name="Address">  
    <sequence>  
      <element name="name"   type="string"/>  
      <element name="street" type="string"/>  
      <element name="city"   type="string"/>  
    </sequence>  
  </complexType>  
  <complexType name="USAddress">  
    <complexContent>  
      <extension base="ipo:Address">  
        <sequence>  
          <element name="state" type="ipo:USState"/>  
          <element name="zip"   type="positiveInteger"/>  
        </sequence>  
      </extension>  
    </complexContent>  
  </complexType>  
  <!-- other Address derivations for more countries or regions -->  
  <simpleType name="USState">  
    <restriction base="string">  
      <enumeration value="AK"/>  
      <enumeration value="AL"/>  
      <enumeration value="AR"/>  
      <!-- and so on ... -->  
    </restriction>  
  </simpleType>  
</schema>  
```  
  
 <span data-ttu-id="21d04-121">Per altre informazioni sugli elementi `<xs:import />`, `<xs:include />` e `<xs:redefine />` e sulle classi <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> e <xref:System.Xml.Schema.XmlSchemaRedefine>, vedere il documento [W3C XML Schema](https://www.w3.org/XML/Schema) e la documentazione di riferimento sulle classi dello spazio dei nomi <xref:System.Xml.Schema?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="21d04-121">For more information about the `<xs:import />`, `<xs:include />`, and `<xs:redefine />` elements and the <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> and <xref:System.Xml.Schema.XmlSchemaRedefine> classes, see the [W3C XML Schema](https://www.w3.org/XML/Schema) and the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace class reference documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21d04-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="21d04-122">See also</span></span>

- [<span data-ttu-id="21d04-123">Cenni preliminari sul modello SOM XML</span><span class="sxs-lookup"><span data-stu-id="21d04-123">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [<span data-ttu-id="21d04-124">Lettura e scrittura di schemi XML</span><span class="sxs-lookup"><span data-stu-id="21d04-124">Reading and Writing XML Schemas</span></span>](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)
- [<span data-ttu-id="21d04-125">Compilazione di XML Schema</span><span class="sxs-lookup"><span data-stu-id="21d04-125">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [<span data-ttu-id="21d04-126">Attraversamento di schemi XML</span><span class="sxs-lookup"><span data-stu-id="21d04-126">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [<span data-ttu-id="21d04-127">Modifica di schemi XML</span><span class="sxs-lookup"><span data-stu-id="21d04-127">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [<span data-ttu-id="21d04-128">XmlSchemaSet per la compilazione di schemi</span><span class="sxs-lookup"><span data-stu-id="21d04-128">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)

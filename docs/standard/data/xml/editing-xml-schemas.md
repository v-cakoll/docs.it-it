---
title: Modifica di schemi XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: fa09c8e5-c2b9-49d2-bb0d-40330cd13e4d
ms.openlocfilehash: b309c390ede3afc38122188337fa0dc3336e3ad5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84292059"
---
# <a name="editing-xml-schemas"></a><span data-ttu-id="33d9d-102">Modifica di schemi XML</span><span class="sxs-lookup"><span data-stu-id="33d9d-102">Editing XML Schemas</span></span>

<span data-ttu-id="33d9d-103">La modifica di uno schema XML rappresenta una delle funzionalità più importanti del modello SOM (Schema Object Model).</span><span class="sxs-lookup"><span data-stu-id="33d9d-103">Editing an XML schema is one of the most important features of the Schema Object Model (SOM).</span></span> <span data-ttu-id="33d9d-104">È possibile usare tutte le proprietà del modello SOM precedenti alla compilazione dello schema per modificare i valori esistenti in uno schema XML.</span><span class="sxs-lookup"><span data-stu-id="33d9d-104">All of the pre-schema-compilation properties of the SOM can be used to change the existing values in an XML schema.</span></span> <span data-ttu-id="33d9d-105">Sarà quindi possibile ricompilare lo schema XML per riflettere le modifiche.</span><span class="sxs-lookup"><span data-stu-id="33d9d-105">The XML schema can then be recompiled to reflect the changes.</span></span>

<span data-ttu-id="33d9d-106">Il primo passaggio della modifica di uno schema caricato nel modello SOM consiste nell'attraversare lo schema.</span><span class="sxs-lookup"><span data-stu-id="33d9d-106">The first step in editing a schema loaded into the SOM is to traverse the schema.</span></span> <span data-ttu-id="33d9d-107">Prima di tentare di modificare uno schema, è necessario essere in grado di attraversare uno schema usando un'API del SOM.</span><span class="sxs-lookup"><span data-stu-id="33d9d-107">You should be familiar with traversing a schema using the SOM API before you attempt to edit a schema.</span></span> <span data-ttu-id="33d9d-108">È necessario inoltre conoscere le proprietà del set PSCI (Post-Schema-Compilation-Infoset) precedenti e successive alla compilazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="33d9d-108">You should also be familiar with the pre- and post-schema-compilation properties of the Post-Schema-Compilation-Infoset (PSCI).</span></span>

## <a name="editing-an-xml-schema"></a><span data-ttu-id="33d9d-109">Modifica di uno schema XML</span><span class="sxs-lookup"><span data-stu-id="33d9d-109">Editing an XML Schema</span></span>

<span data-ttu-id="33d9d-110">In questa sezione vengono forniti due esempi di codice che consentono di modificare lo schema del cliente creato nell'argomento [Compilazione di XML Schema](building-xml-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="33d9d-110">In this section, two code examples are provided, both of which edit the customer schema created in the [Building XML Schemas](building-xml-schemas.md) topic.</span></span> <span data-ttu-id="33d9d-111">Il primo esempio di codice aggiunge un nuovo elemento `PhoneNumber` all'elemento `Customer`, mentre il secondo aggiunge un nuovo attributo `Title` all'elemento `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="33d9d-111">The first code example adds a new `PhoneNumber` element to the `Customer` element and the second code example adds a new `Title` attribute to the `FirstName` element.</span></span> <span data-ttu-id="33d9d-112">Nel primo esempio, inoltre, per attraversare lo schema del cliente, viene usata la raccolta <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> successiva alla compilazione dello schema, mentre nel secondo esempio di codice viene usata la raccolta <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> precedente alla compilazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="33d9d-112">The first sample also uses the post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collection as the means of traversing the customer schema while the second code example uses the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection.</span></span>

### <a name="phonenumber-element-example"></a><span data-ttu-id="33d9d-113">Esempio dell'elemento PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="33d9d-113">PhoneNumber Element Example</span></span>

<span data-ttu-id="33d9d-114">Il primo esempio di codice aggiunge un nuovo elemento `PhoneNumber` all'elemento `Customer` dello schema del cliente.</span><span class="sxs-lookup"><span data-stu-id="33d9d-114">This first code example adds a new `PhoneNumber` element to the `Customer` element of the customer schema.</span></span> <span data-ttu-id="33d9d-115">L'esempio di codice consente di modificare lo schema del cliente eseguendo i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="33d9d-115">The code example edits the customer schema in the following steps.</span></span>

1. <span data-ttu-id="33d9d-116">Aggiunge lo schema del cliente a un nuovo oggetto <xref:System.Xml.Schema.XmlSchemaSet>, quindi lo compila.</span><span class="sxs-lookup"><span data-stu-id="33d9d-116">Adds the customer schema to a new <xref:System.Xml.Schema.XmlSchemaSet> object and then compiles it.</span></span> <span data-ttu-id="33d9d-117">Eventuali avvisi ed errori di convalida dello schema rilevati durante la lettura e la compilazione dello schema vengono gestiti dal delegato <xref:System.Xml.Schema.ValidationEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="33d9d-117">Any schema validation warnings and errors encountered reading or compiling the schema are handled by the <xref:System.Xml.Schema.ValidationEventHandler> delegate.</span></span>

2. <span data-ttu-id="33d9d-118">Recupera l'oggetto <xref:System.Xml.Schema.XmlSchema> compilato dal tipo <xref:System.Xml.Schema.XmlSchemaSet> scorrendo la proprietà <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>.</span><span class="sxs-lookup"><span data-stu-id="33d9d-118">Retrieves the compiled <xref:System.Xml.Schema.XmlSchema> object from the <xref:System.Xml.Schema.XmlSchemaSet> by iterating over the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property.</span></span> <span data-ttu-id="33d9d-119">Dal momento che lo schema è stato compilato, è possibile accedere alle proprietà di PSCI (Post-Schema-Compilation-Infoset).</span><span class="sxs-lookup"><span data-stu-id="33d9d-119">Because the schema is compiled, Post-Schema-Compilation-Infoset (PSCI) properties are accessible.</span></span>

3. <span data-ttu-id="33d9d-120">Crea l'elemento `PhoneNumber` mediante la classe <xref:System.Xml.Schema.XmlSchemaElement>, la restrizione del tipo semplice `xs:string` mediante le classi <xref:System.Xml.Schema.XmlSchemaSimpleType> e <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction>, aggiunge un facet pattern alla proprietà <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction.Facets%2A> della restrizione, quindi aggiunge la restrizione alla proprietà <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A> del tipo semplice e il tipo semplice alla proprietà <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> dell'elemento `PhoneNumber`.</span><span class="sxs-lookup"><span data-stu-id="33d9d-120">Creates the `PhoneNumber` element using the <xref:System.Xml.Schema.XmlSchemaElement> class, the `xs:string` simple type restriction using the <xref:System.Xml.Schema.XmlSchemaSimpleType> and <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> classes, adds a pattern facet to the <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction.Facets%2A> property of the restriction, and adds the restriction to the <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A> property of the simple type and the simple type to the <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> of the `PhoneNumber` element.</span></span>

4. <span data-ttu-id="33d9d-121">Scorre ciascun tipo <xref:System.Xml.Schema.XmlSchemaElement> nella raccolta <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A> della raccolta <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> successiva alla compilazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="33d9d-121">Iterates over each <xref:System.Xml.Schema.XmlSchemaElement> in the <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A> collection of the post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collection.</span></span>

5. <span data-ttu-id="33d9d-122">Se la proprietà <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> dell'elemento è `"Customer"`, recupera il tipo complesso dell'elemento `Customer` mediante la classe <xref:System.Xml.Schema.XmlSchemaComplexType> e la particella di sequenza del tipo complesso mediante la classe <xref:System.Xml.Schema.XmlSchemaSequence>.</span><span class="sxs-lookup"><span data-stu-id="33d9d-122">If the <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> of the element is `"Customer"`, gets the complex type of the `Customer` element using the <xref:System.Xml.Schema.XmlSchemaComplexType> class and the sequence particle of the complex type using the <xref:System.Xml.Schema.XmlSchemaSequence> class.</span></span>

6. <span data-ttu-id="33d9d-123">Aggiunge il nuovo elemento `PhoneNumber` alla sequenza contenente gli elementi `FirstName` e `LastName` esistenti usando la raccolta <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A> precedente allo schema della sequenza.</span><span class="sxs-lookup"><span data-stu-id="33d9d-123">Adds the new `PhoneNumber` element to the sequence containing the existing `FirstName` and `LastName` elements using the pre-schema-compilation <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A> collection of the sequence.</span></span>

7. <span data-ttu-id="33d9d-124">Infine, rielabora e compila l'oggetto modificato <xref:System.Xml.Schema.XmlSchema> usando i metodi <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> e <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> della classe <xref:System.Xml.Schema.XmlSchemaSet> e lo scrive nella console.</span><span class="sxs-lookup"><span data-stu-id="33d9d-124">Finally, reprocesses and compiles the modified <xref:System.Xml.Schema.XmlSchema> object using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> and <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet> class and writes it to the console.</span></span>

<span data-ttu-id="33d9d-125">Di seguito è riportato l'esempio di codice completo.</span><span class="sxs-lookup"><span data-stu-id="33d9d-125">The following is the complete code example.</span></span>

[!code-cpp[XmlSchemaEditExample1#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample1/CPP/XmlSchemaEditExample1.cpp#1)]
[!code-csharp[XmlSchemaEditExample1#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample1/CS/XmlSchemaEditExample1.cs#1)]
[!code-vb[XmlSchemaEditExample1#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample1/VB/XmlSchemaEditExample1.vb#1)]

<span data-ttu-id="33d9d-126">Di seguito è riportato lo schema modificato del cliente e creato nell'argomento [Compilazione di XML Schema](building-xml-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="33d9d-126">The following is the modified customer schema created in the [Building XML Schemas](building-xml-schemas.md) topic.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="Customer">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="FirstName" type="xs:string" />
        <xs:element name="LastName" type="tns:LastNameType" />
        <xs:element name="PhoneNumber">           <xs:simpleType>             <xs:restriction base="xs:string">               <xs:pattern value="\d{3}-\d{3}-\d(4)" />             </xs:restriction>           </xs:simpleType>         </xs:element>
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
```

### <a name="title-attribute-example"></a><span data-ttu-id="33d9d-127">Esempio dell'attributo Title</span><span class="sxs-lookup"><span data-stu-id="33d9d-127">Title Attribute Example</span></span>

<span data-ttu-id="33d9d-128">Il secondo esempio di codice aggiunge un nuovo attributo `Title` all'elemento `FirstName` dello schema del cliente.</span><span class="sxs-lookup"><span data-stu-id="33d9d-128">This second code example, adds a new `Title` attribute to the `FirstName` element of the customer schema.</span></span> <span data-ttu-id="33d9d-129">Nel primo esempio di codice il tipo dell'elemento `FirstName` è `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="33d9d-129">In the first code example, the type of the `FirstName` element is `xs:string`.</span></span> <span data-ttu-id="33d9d-130">Per fare in modo che l'elemento `FirstName` presenti un attributo e un contenuto di stringa, è necessario modificarne il tipo impostandolo su un tipo complesso con un modello di contenuto derivato dall'estensione di contenuto semplice.</span><span class="sxs-lookup"><span data-stu-id="33d9d-130">For the `FirstName` element to have an attribute along with string content, its type must be changed to a complex type with a simple content extension content model.</span></span>

<span data-ttu-id="33d9d-131">L'esempio di codice consente di modificare lo schema del cliente eseguendo i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="33d9d-131">The code example edits the customer schema in the following steps.</span></span>

1. <span data-ttu-id="33d9d-132">Aggiunge lo schema del cliente a un nuovo oggetto <xref:System.Xml.Schema.XmlSchemaSet>, quindi lo compila.</span><span class="sxs-lookup"><span data-stu-id="33d9d-132">Adds the customer schema to a new <xref:System.Xml.Schema.XmlSchemaSet> object and then compiles it.</span></span> <span data-ttu-id="33d9d-133">Eventuali avvisi ed errori di convalida dello schema rilevati durante la lettura e la compilazione dello schema vengono gestiti dal delegato <xref:System.Xml.Schema.ValidationEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="33d9d-133">Any schema validation warnings and errors encountered reading or compiling the schema are handled by the <xref:System.Xml.Schema.ValidationEventHandler> delegate.</span></span>

2. <span data-ttu-id="33d9d-134">Recupera l'oggetto <xref:System.Xml.Schema.XmlSchema> compilato dal tipo <xref:System.Xml.Schema.XmlSchemaSet> scorrendo la proprietà <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>.</span><span class="sxs-lookup"><span data-stu-id="33d9d-134">Retrieves the compiled <xref:System.Xml.Schema.XmlSchema> object from the <xref:System.Xml.Schema.XmlSchemaSet> by iterating over the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property.</span></span> <span data-ttu-id="33d9d-135">Dal momento che lo schema è stato compilato, è possibile accedere alle proprietà di PSCI (Post-Schema-Compilation-Infoset).</span><span class="sxs-lookup"><span data-stu-id="33d9d-135">Because the schema is compiled, Post-Schema-Compilation-Infoset (PSCI) properties are accessible.</span></span>

3. <span data-ttu-id="33d9d-136">Crea un nuovo tipo complesso per l'elemento `FirstName` usando la classe <xref:System.Xml.Schema.XmlSchemaComplexType>.</span><span class="sxs-lookup"><span data-stu-id="33d9d-136">Creates a new complex type for the `FirstName` element using the <xref:System.Xml.Schema.XmlSchemaComplexType> class.</span></span>

4. <span data-ttu-id="33d9d-137">Crea una nuova estensione di contenuto semplice, con un tipo di base di `xs:string`, usando le classi <xref:System.Xml.Schema.XmlSchemaSimpleContent> e <xref:System.Xml.Schema.XmlSchemaSimpleContentExtension>.</span><span class="sxs-lookup"><span data-stu-id="33d9d-137">Creates a new simple content extension, with a base type of `xs:string`, using the <xref:System.Xml.Schema.XmlSchemaSimpleContent> and <xref:System.Xml.Schema.XmlSchemaSimpleContentExtension> classes.</span></span>

5. <span data-ttu-id="33d9d-138">Crea il nuovo attributo `Title` usando la classe <xref:System.Xml.Schema.XmlSchemaAttribute>, con una proprietà <xref:System.Xml.Schema.XmlSchemaAttribute.SchemaTypeName%2A> di `xs:string` e aggiunge l'attributo all'estensione di contenuto semplice.</span><span class="sxs-lookup"><span data-stu-id="33d9d-138">Creates the new `Title` attribute using the <xref:System.Xml.Schema.XmlSchemaAttribute> class, with a <xref:System.Xml.Schema.XmlSchemaAttribute.SchemaTypeName%2A> of `xs:string` and adds the attribute to the simple content extension.</span></span>

6. <span data-ttu-id="33d9d-139">Imposta il modello di contenuto del contenuto semplice sull'estensione di contenuto semplice e il modello di contenuto del tipo complesso sul contenuto semplice.</span><span class="sxs-lookup"><span data-stu-id="33d9d-139">Sets the content model of the simple content to the simple content extension and the content model of the complex type to the simple content.</span></span>

7. <span data-ttu-id="33d9d-140">Aggiunge il nuovo tipo complesso alla raccolta <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> precedente alla compilazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="33d9d-140">Adds the new complex type to the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection.</span></span>

8. <span data-ttu-id="33d9d-141">Scorre ciascun tipo <xref:System.Xml.Schema.XmlSchemaObject> nella raccolta <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> precedente alla compilazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="33d9d-141">Iterates over each <xref:System.Xml.Schema.XmlSchemaObject> in the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection.</span></span>

> [!NOTE]
> <span data-ttu-id="33d9d-142">Dal momento che l'elemento `FirstName` non è un elemento globale nello schema, non è disponibile nella raccolta <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> o <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="33d9d-142">Because the `FirstName` element is not a global element in the schema, it is not available in the <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> or <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collections.</span></span> <span data-ttu-id="33d9d-143">L'esempio di codice individua l'elemento `FirstName` dopo aver individuato l'elemento `Customer`.</span><span class="sxs-lookup"><span data-stu-id="33d9d-143">The code example locates the `FirstName` element by first locating the `Customer` element.</span></span>
>
> <span data-ttu-id="33d9d-144">Nel primo esempio di codice lo schema era stato attraversato usando la raccolta <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> successiva alla compilazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="33d9d-144">The first code example traversed the schema using the post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collection.</span></span> <span data-ttu-id="33d9d-145">In questo esempio, per attraversare lo schema viene usata la raccolta <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> precedente alla compilazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="33d9d-145">In this sample, the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection is used to traverse the schema.</span></span> <span data-ttu-id="33d9d-146">Mentre entrambe le raccolte forniscono l'accesso agli elementi globali dello schema, lo scorrimento della raccolta <xref:System.Xml.Schema.XmlSchema.Items%2A> richiede più tempo, poiché è necessario scorrere tutti gli elementi globali dello schema e poiché non sono presenti proprietà PSCI.</span><span class="sxs-lookup"><span data-stu-id="33d9d-146">While both collections provide access to the global elements in the schema, iterating through the <xref:System.Xml.Schema.XmlSchema.Items%2A> collection is more time consuming because you must iterate over all global elements in the schema and it does not have any PSCI properties.</span></span> <span data-ttu-id="33d9d-147">Le raccolte PSCI (le proprietà <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.Attributes%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A?displayProperty=nameWithType> e così via) forniscono l'accesso diretto agli elementi, agli attributi, ai tipi globali e alle relative proprietà PSCI.</span><span class="sxs-lookup"><span data-stu-id="33d9d-147">The PSCI collections (<xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.Attributes%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A?displayProperty=nameWithType>, and so on) provide direct access to their global elements, attributes, and types and their PSCI properties.</span></span>

1. <span data-ttu-id="33d9d-148">Se la proprietà <xref:System.Xml.Schema.XmlSchemaObject> è un elemento la cui proprietà <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> è `"Customer"`, vengono recuperati il tipo complesso dell'elemento `Customer` mediante la classe <xref:System.Xml.Schema.XmlSchemaComplexType> e la particella di sequenza del tipo complesso mediante la classe <xref:System.Xml.Schema.XmlSchemaSequence>.</span><span class="sxs-lookup"><span data-stu-id="33d9d-148">If the <xref:System.Xml.Schema.XmlSchemaObject> is an element, whose <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> is `"Customer"`, gets the complex type of the `Customer` element using the <xref:System.Xml.Schema.XmlSchemaComplexType> class and the sequence particle of the complex type using the <xref:System.Xml.Schema.XmlSchemaSequence> class.</span></span>

2. <span data-ttu-id="33d9d-149">Scorre ciascun tipo <xref:System.Xml.Schema.XmlSchemaParticle> nella raccolta <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType> precedente alla compilazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="33d9d-149">Iterates over each <xref:System.Xml.Schema.XmlSchemaParticle> in the pre-schema-compilation <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType> collection.</span></span>

3. <span data-ttu-id="33d9d-150">Se il tipo <xref:System.Xml.Schema.XmlSchemaParticle> è un elemento e la relativa proprietà <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> è `"FirstName"`, imposta la proprietà <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> dell'elemento `FirstName` su nuovo tipo complesso `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="33d9d-150">If the <xref:System.Xml.Schema.XmlSchemaParticle> is an element, who's <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> is `"FirstName"`, sets the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> of the `FirstName` element to the new `FirstName` complex type.</span></span>

4. <span data-ttu-id="33d9d-151">Infine, rielabora e compila l'oggetto modificato <xref:System.Xml.Schema.XmlSchema> usando i metodi <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> e <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> della classe <xref:System.Xml.Schema.XmlSchemaSet> e lo scrive nella console.</span><span class="sxs-lookup"><span data-stu-id="33d9d-151">Finally, reprocesses and compiles the modified <xref:System.Xml.Schema.XmlSchema> object using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> and <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet> class and writes it to the console.</span></span>

<span data-ttu-id="33d9d-152">Di seguito è riportato l'esempio di codice completo.</span><span class="sxs-lookup"><span data-stu-id="33d9d-152">The following is the complete code example.</span></span>

[!code-cpp[XmlSchemaEditExample2#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample2/CPP/XmlSchemaEditExample2.cpp#1)]
[!code-csharp[XmlSchemaEditExample2#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample2/CS/XmlSchemaEditExample2.cs#1)]
[!code-vb[XmlSchemaEditExample2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample2/VB/XmlSchemaEditExample2.vb#1)]

<span data-ttu-id="33d9d-153">Di seguito è riportato lo schema modificato del cliente e creato nell'argomento [Compilazione di XML Schema](building-xml-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="33d9d-153">The following is the modified customer schema created in the [Building XML Schemas](building-xml-schemas.md) topic.</span></span>

```xml
<?xml version="1.0" encoding=" utf-8"?>
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="Customer">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="FirstName" type="tns:FirstNameComplexType" />
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
  <xs:complexType name="FirstNameComplexType">     <xs:simpleContent>       <xs:extension base="xs:string">         <xs:attribute name="Title" type="xs:string" />       </xs:extension>     </xs:simpleContent>   </xs:complexType>
</xs:schema>
```

## <a name="see-also"></a><span data-ttu-id="33d9d-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33d9d-154">See also</span></span>

- [<span data-ttu-id="33d9d-155">Cenni preliminari sul modello SOM XML</span><span class="sxs-lookup"><span data-stu-id="33d9d-155">XML Schema Object Model Overview</span></span>](xml-schema-object-model-overview.md)
- [<span data-ttu-id="33d9d-156">Lettura e scrittura di schemi XML</span><span class="sxs-lookup"><span data-stu-id="33d9d-156">Reading and Writing XML Schemas</span></span>](reading-and-writing-xml-schemas.md)
- [<span data-ttu-id="33d9d-157">Compilazione di XML Schema</span><span class="sxs-lookup"><span data-stu-id="33d9d-157">Building XML Schemas</span></span>](building-xml-schemas.md)
- [<span data-ttu-id="33d9d-158">Attraversamento di schemi XML</span><span class="sxs-lookup"><span data-stu-id="33d9d-158">Traversing XML Schemas</span></span>](traversing-xml-schemas.md)
- [<span data-ttu-id="33d9d-159">Inclusione o importazione di schemi XML</span><span class="sxs-lookup"><span data-stu-id="33d9d-159">Including or Importing XML Schemas</span></span>](including-or-importing-xml-schemas.md)
- [<span data-ttu-id="33d9d-160">XmlSchemaSet per la compilazione di schemi</span><span class="sxs-lookup"><span data-stu-id="33d9d-160">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="33d9d-161">Post-Schema Compilation Infoset (PSCI, infoset sulla compilazione post-schema)</span><span class="sxs-lookup"><span data-stu-id="33d9d-161">Post-Schema Compilation Infoset</span></span>](post-schema-compilation-infoset.md)

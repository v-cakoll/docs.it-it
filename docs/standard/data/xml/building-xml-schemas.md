---
title: Compilazione di XML Schema
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 8a5ea56c-0140-4b51-8997-875ae6a8e0cb
ms.openlocfilehash: c921331b00fe137d4ad52d62951e8c161768dfae
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711142"
---
# <a name="building-xml-schemas"></a><span data-ttu-id="cec42-102">Compilazione di XML Schema</span><span class="sxs-lookup"><span data-stu-id="cec42-102">Building XML Schemas</span></span>
<span data-ttu-id="cec42-103">Le classi nello spazio dei nomi <xref:System.Xml.Schema?displayProperty=nameWithType> sono associate alle strutture definite nella raccomandazione W3C (World Wide Web Consortium) XML Schema e possono essere usate per compilare schemi XML in memoria.</span><span class="sxs-lookup"><span data-stu-id="cec42-103">The classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace map to the structures defined in the World Wide Web Consortium (W3C) XML Schema Recommendation and can be used to build XML schemas in-memory.</span></span>  
  
## <a name="building-an-xml-schema"></a><span data-ttu-id="cec42-104">Compilazione di un XML Schema</span><span class="sxs-lookup"><span data-stu-id="cec42-104">Building an XML Schema</span></span>  
 <span data-ttu-id="cec42-105">Nei seguenti esempi di codice, per compilare in memoria uno schema XML del cliente viene usata l'API del modello SOM (Schema Object Model).</span><span class="sxs-lookup"><span data-stu-id="cec42-105">In the code examples that follow, the SOM API is used to build a customer XML schema in-memory.</span></span>  
  
### <a name="creating-element-and-attributes"></a><span data-ttu-id="cec42-106">Creazione di elementi e attributi</span><span class="sxs-lookup"><span data-stu-id="cec42-106">Creating Element and Attributes</span></span>  
 <span data-ttu-id="cec42-107">Negli esempi di codice, lo schema del cliente viene compilato dal basso verso l'alto, ovvero vengono creati prima gli elementi e gli attributi figlio con i tipi corrispondenti, poi gli elementi principali.</span><span class="sxs-lookup"><span data-stu-id="cec42-107">The code examples build the customer schema from the bottom up, creating the child elements, attributes, and their corresponding types first, and then the top-level elements.</span></span>  
  
 <span data-ttu-id="cec42-108">Nel seguente esempio di codice gli elementi `FirstName`, `LastName` e l'attributo `CustomerId` dello schema del cliente vengono creati usando le classi <xref:System.Xml.Schema.XmlSchemaElement> e <xref:System.Xml.Schema.XmlSchemaAttribute> del modello SOM.</span><span class="sxs-lookup"><span data-stu-id="cec42-108">In the following code example, the `FirstName` and `LastName` elements, as well as the `CustomerId` attribute of the customer schema are created using the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAttribute> classes of the SOM.</span></span> <span data-ttu-id="cec42-109">A parte le proprietà <xref:System.Xml.Schema.XmlSchemaElement.Name%2A> delle classi <xref:System.Xml.Schema.XmlSchemaElement> e <xref:System.Xml.Schema.XmlSchemaAttribute>, che corrispondono all'attributo "name" degli elementi `<xs:element />` e `<xs:attribute />` in XML Schema, tutti gli altri attributi consentiti dallo schema (`defaultValue`, `fixedValue`, `form` e così via) contengono le proprietà corrispondenti nelle classi <xref:System.Xml.Schema.XmlSchemaElement> e <xref:System.Xml.Schema.XmlSchemaAttribute>.</span><span class="sxs-lookup"><span data-stu-id="cec42-109">Apart from the <xref:System.Xml.Schema.XmlSchemaElement.Name%2A> properties of the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAttribute> classes, which correspond to the "name" attribute of the `<xs:element />` and `<xs:attribute />` elements in an XML schema, all other attributes allowed by the schema (`defaultValue`, `fixedValue`, `form`, and so on) have corresponding properties in the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAttribute> classes.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#2)]
 [!code-csharp[XmlSchemaCreateExample#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#2)]
 [!code-vb[XmlSchemaCreateExample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#2)]  
  
### <a name="creating-schema-types"></a><span data-ttu-id="cec42-110">Creazione di tipi di schema</span><span class="sxs-lookup"><span data-stu-id="cec42-110">Creating Schema Types</span></span>  
 <span data-ttu-id="cec42-111">Il contenuto degli elementi e degli attributi è definito dai relativi tipi.</span><span class="sxs-lookup"><span data-stu-id="cec42-111">The content of elements and attributes is defined by their types.</span></span> <span data-ttu-id="cec42-112">Per creare elementi e attributi i cui tipi corrispondano a uno dei tipi incorporati nello schema, la proprietà <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> della classe <xref:System.Xml.Schema.XmlSchemaElement> o <xref:System.Xml.Schema.XmlSchemaAttribute> viene impostata con il nome completo corrispondente del tipo incorporato usando la classe <xref:System.Xml.XmlQualifiedName>.</span><span class="sxs-lookup"><span data-stu-id="cec42-112">To create elements and attributes whose types are one of the built-in schema types, the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> or <xref:System.Xml.Schema.XmlSchemaAttribute> classes are set with the corresponding qualified name of the built-in type using the <xref:System.Xml.XmlQualifiedName> class.</span></span> <span data-ttu-id="cec42-113">Per creare un tipo definito dall'utente per gli elementi e gli attributi, viene creato un nuovo tipo semplice o complesso usando la classe <xref:System.Xml.Schema.XmlSchemaSimpleType> o <xref:System.Xml.Schema.XmlSchemaComplexType>.</span><span class="sxs-lookup"><span data-stu-id="cec42-113">To create a user-defined type for elements and attributes, a new simple or complex type is created using the <xref:System.Xml.Schema.XmlSchemaSimpleType> or <xref:System.Xml.Schema.XmlSchemaComplexType> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cec42-114">Per creare tipi semplici o complessi senza nome anonimo figlio di un elemento o attributo (si applicano solo tipi semplici per gli attributi), impostare il <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> proprietà del <xref:System.Xml.Schema.XmlSchemaElement> o <xref:System.Xml.Schema.XmlSchemaAttribute> alle classi di tipo semplice o complesso senza nome, anziché il <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> proprietà del <xref:System.Xml.Schema.XmlSchemaElement> o <xref:System.Xml.Schema.XmlSchemaAttribute> classi.</span><span class="sxs-lookup"><span data-stu-id="cec42-114">To create unnamed simple or complex types that are anonymous children of an element or attribute (only simple types apply for attributes), set the <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> or <xref:System.Xml.Schema.XmlSchemaAttribute> classes to the unnamed simple or complex type, instead of the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> or <xref:System.Xml.Schema.XmlSchemaAttribute> classes.</span></span>  
  
 <span data-ttu-id="cec42-115">Gli schemi XML consentono di derivare per restrizione da altri tipi semplici (incorporati o definiti dall'utente) sia i tipi semplici anonimi sia i tipi semplici denominati oppure di crearli come un elenco o un'unione di altri tipi semplici.</span><span class="sxs-lookup"><span data-stu-id="cec42-115">XML schemas allow both anonymous and named simple types to be derived by restriction from other simple types (built-in or user-defined) or constructed as a list or union of other simple types.</span></span> <span data-ttu-id="cec42-116">La classe <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> consente di creare un tipo semplice per restrizione dal tipo `xs:string` incorporato.</span><span class="sxs-lookup"><span data-stu-id="cec42-116">The <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> class is used to create a simple type by restricting the built-in `xs:string` type.</span></span> <span data-ttu-id="cec42-117">Per creare tipi di unione o di elenco, è possibile usare anche la classe <xref:System.Xml.Schema.XmlSchemaSimpleTypeList> o <xref:System.Xml.Schema.XmlSchemaSimpleTypeUnion>.</span><span class="sxs-lookup"><span data-stu-id="cec42-117">You can also use the <xref:System.Xml.Schema.XmlSchemaSimpleTypeList> or <xref:System.Xml.Schema.XmlSchemaSimpleTypeUnion> classes to create list or union types.</span></span> <span data-ttu-id="cec42-118">La proprietà <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A?displayProperty=nameWithType> indica se è una restrizione, un elenco o un'unione di tipi semplici.</span><span class="sxs-lookup"><span data-stu-id="cec42-118">The <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A?displayProperty=nameWithType> property denotes whether it is a simple type restriction, list, or union.</span></span>  
  
 <span data-ttu-id="cec42-119">Nel seguente esempio di codice il tipo dell'elemento `FirstName` è un tipo `xs:string` incorporato, il tipo dell'elemento `LastName` è un tipo semplice denominato che è una restrizione del tipo `xs:string` incorporato, il valore del facet `MaxLength` è 20 e il tipo dell'attributo `CustomerId` è il tipo `xs:positiveInteger` incorporato.</span><span class="sxs-lookup"><span data-stu-id="cec42-119">In the following code example, the `FirstName` element's type is the built-in type `xs:string`, the `LastName` element's type is a named simple type that is a restriction of the built-in type `xs:string`, with a `MaxLength` facet value of 20, and the `CustomerId` attribute's type is the built-in type `xs:positiveInteger`.</span></span> <span data-ttu-id="cec42-120">L'elemento `Customer` è un tipo complesso anonimo la cui particella è rappresentata dalla sequenza degli elementi `FirstName` e `LastName` e i cui attributi contengono l'attributo `CustomerId`.</span><span class="sxs-lookup"><span data-stu-id="cec42-120">The `Customer` element is an anonymous complex type whose particle is the sequence of the `FirstName` and `LastName` elements and whose attributes contains the `CustomerId` attribute.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cec42-121">È inoltre possibile usare le classi <xref:System.Xml.Schema.XmlSchemaChoice> o <xref:System.Xml.Schema.XmlSchemaAll> come particella del tipo complesso per replicare la semantica `<xs:choice />` o `<xs:all />`.</span><span class="sxs-lookup"><span data-stu-id="cec42-121">You can also use the <xref:System.Xml.Schema.XmlSchemaChoice> or <xref:System.Xml.Schema.XmlSchemaAll> classes as the particle of the complex type to replicate `<xs:choice />` or `<xs:all />` semantics.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#3](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#3)]
 [!code-csharp[XmlSchemaCreateExample#3](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#3)]
 [!code-vb[XmlSchemaCreateExample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#3)]  
  
### <a name="creating-and-compiling-schemas"></a><span data-ttu-id="cec42-122">Creazione e compilazione di schemi</span><span class="sxs-lookup"><span data-stu-id="cec42-122">Creating and Compiling Schemas</span></span>  
 <span data-ttu-id="cec42-123">A questo punto, usando l'API del modello SOM, sono stati creati in memoria gli elementi e attributi figlio, i tipi corrispondenti e l'elemento di livello principale `Customer`.</span><span class="sxs-lookup"><span data-stu-id="cec42-123">At this point, the child elements and attributes, their corresponding types, and the top-level `Customer` element have been created in-memory using the SOM API.</span></span> <span data-ttu-id="cec42-124">Nel seguente esempio di codice l'elemento dello schema viene creato usando la classe <xref:System.Xml.Schema.XmlSchema>, vi vengono aggiunti i tipi e gli elementi di livello principale tramite la proprietà <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType>, quindi lo schema completo viene compilato usando la classe <xref:System.Xml.Schema.XmlSchemaSet> e viene scritto nella console.</span><span class="sxs-lookup"><span data-stu-id="cec42-124">In the following code example, the schema element is created using the <xref:System.Xml.Schema.XmlSchema> class, the top-level elements and types are added to it using the <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> property and the complete schema is compiled using the <xref:System.Xml.Schema.XmlSchemaSet> class and written to the console.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#4](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#4)]
 [!code-csharp[XmlSchemaCreateExample#4](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#4)]
 [!code-vb[XmlSchemaCreateExample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#4)]  
  
 <span data-ttu-id="cec42-125">Il metodo <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A?displayProperty=nameWithType> convalida lo schema del cliente in base alle regole per gli schemi XML e rende disponibili le proprietà successive alla compilazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="cec42-125">The <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A?displayProperty=nameWithType> method validates the customer schema against the rules for an XML schema and makes post-schema-compilation properties available.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cec42-126">Tutte le proprietà nell'API del modello SOM successive alla compilazione dello schema sono diverse dall'infoset sulla convalida post-schema.</span><span class="sxs-lookup"><span data-stu-id="cec42-126">All post-schema-compilation properties in the SOM API differ from the Post-Schema-Validation-Infoset.</span></span>  
  
 <span data-ttu-id="cec42-127">Il tipo <xref:System.Xml.Schema.ValidationEventHandler> aggiunto al tipo <xref:System.Xml.Schema.XmlSchemaSet> è un delegato che chiama il metodo di callback `ValidationCallback` per gestire gli avvisi e gli errori di convalida dello schema.</span><span class="sxs-lookup"><span data-stu-id="cec42-127">The <xref:System.Xml.Schema.ValidationEventHandler> added to the <xref:System.Xml.Schema.XmlSchemaSet> is a delegate that calls the callback method `ValidationCallback` to handle schema validation warnings and errors.</span></span>  
  
 <span data-ttu-id="cec42-128">Di seguito è riportato l'esempio di codice completo e lo schema del cliente scritto nella console.</span><span class="sxs-lookup"><span data-stu-id="cec42-128">The following is the complete code example, and the customer schema written to the console.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#1)]
 [!code-csharp[XmlSchemaCreateExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#1)]
 [!code-vb[XmlSchemaCreateExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#1)]  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
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
```  
  
## <a name="see-also"></a><span data-ttu-id="cec42-129">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="cec42-129">See also</span></span>

- [<span data-ttu-id="cec42-130">Cenni preliminari sul modello SOM XML</span><span class="sxs-lookup"><span data-stu-id="cec42-130">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [<span data-ttu-id="cec42-131">Lettura e scrittura di schemi XML</span><span class="sxs-lookup"><span data-stu-id="cec42-131">Reading and Writing XML Schemas</span></span>](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)
- [<span data-ttu-id="cec42-132">Attraversamento di schemi XML</span><span class="sxs-lookup"><span data-stu-id="cec42-132">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [<span data-ttu-id="cec42-133">Modifica di schemi XML</span><span class="sxs-lookup"><span data-stu-id="cec42-133">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [<span data-ttu-id="cec42-134">Inclusione o importazione di schemi XML</span><span class="sxs-lookup"><span data-stu-id="cec42-134">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [<span data-ttu-id="cec42-135">XmlSchemaSet per la compilazione di schemi</span><span class="sxs-lookup"><span data-stu-id="cec42-135">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="cec42-136">Post-Schema Compilation Infoset (PSCI, infoset sulla compilazione post-schema)</span><span class="sxs-lookup"><span data-stu-id="cec42-136">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)

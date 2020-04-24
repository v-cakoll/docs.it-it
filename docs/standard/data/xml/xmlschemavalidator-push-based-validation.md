---
title: Convalida basata sul metodo push di XmlSchemaValidator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 911d4460-dd91-4958-85b2-2ca3299f9ec6
ms.openlocfilehash: 6a0cc110c2b8bcd97b9f5c16a344db5a63046353
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709803"
---
# <a name="xmlschemavalidator-push-based-validation"></a><span data-ttu-id="d8943-102">Convalida basata sul metodo push di XmlSchemaValidator</span><span class="sxs-lookup"><span data-stu-id="d8943-102">XmlSchemaValidator Push-Based Validation</span></span>

<span data-ttu-id="d8943-103">La classe <xref:System.Xml.Schema.XmlSchemaValidator> fornisce un meccanismo efficiente e a elevate prestazioni per la convalida basata sul metodo push di dati XML in base a schemi XML.</span><span class="sxs-lookup"><span data-stu-id="d8943-103">The <xref:System.Xml.Schema.XmlSchemaValidator> class provides an efficient, high-performance mechanism to validate XML data against XML schemas in a push-based manner.</span></span> <span data-ttu-id="d8943-104">Ad esempio, la classe <xref:System.Xml.Schema.XmlSchemaValidator> consente di convalidare un infoset XML sul posto senza la necessità di serializzarlo come documento XML e di eseguire nuovamente l'analisi del documento mediante un lettore XML di convalida.</span><span class="sxs-lookup"><span data-stu-id="d8943-104">For example, the <xref:System.Xml.Schema.XmlSchemaValidator> class allows you to validate an XML infoset in-place without having to serialize it as an XML document and then reparse the document using a validating XML reader.</span></span>

<span data-ttu-id="d8943-105">La classe <xref:System.Xml.Schema.XmlSchemaValidator> può essere usata in scenari avanzati, ad esempio per la compilazione di motori di convalida in base a origini dati XML personalizzate oppure per la compilazione di un writer XML di convalida.</span><span class="sxs-lookup"><span data-stu-id="d8943-105">The <xref:System.Xml.Schema.XmlSchemaValidator> class can be used in advanced scenarios such as building validation engines over custom XML data sources or as a way to build a validating XML writer.</span></span>

<span data-ttu-id="d8943-106">Di seguito è riportato un esempio di utilizzo della classe <xref:System.Xml.Schema.XmlSchemaValidator> per convalidare il file `contosoBooks.xml` in base allo schema `contosoBooks.xsd`.</span><span class="sxs-lookup"><span data-stu-id="d8943-106">The following is an example of using the <xref:System.Xml.Schema.XmlSchemaValidator> class to validate the `contosoBooks.xml` file against the `contosoBooks.xsd` schema.</span></span> <span data-ttu-id="d8943-107">Nell'esempio viene usata la classe <xref:System.Xml.Serialization.XmlSerializer> per deserializzare il file `contosoBooks.xml` e passare il valore dei nodi ai metodi della classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-107">The example uses the <xref:System.Xml.Serialization.XmlSerializer> class to deserialize the `contosoBooks.xml` file and pass the value of the nodes to the methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span>

> [!NOTE]
> <span data-ttu-id="d8943-108">Questo esempio viene usato in tutte le sezioni di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d8943-108">This example is used throughout the sections of this topic.</span></span>

[!code-csharp[XmlSchemaValidatorExamples#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaValidatorExamples/CS/XmlSchemaValidatorExamples.cs#1)]
[!code-vb[XmlSchemaValidatorExamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaValidatorExamples/VB/XmlSchemaValidatorExamples.vb#1)]

<span data-ttu-id="d8943-109">Nell'esempio il file `contosoBooks.xml` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="d8943-109">The example takes the `contosoBooks.xml` file as input.</span></span>

[!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]

<span data-ttu-id="d8943-110">Anche il file `contosoBooks.xsd` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="d8943-110">The example also takes the `contosoBooks.xsd` as an input.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" targetNamespace="http://www.contoso.com/books" xmlns:xs="http://www.w3.org/2001/XMLSchema">
    <xs:element name="bookstore">
        <xs:complexType>
            <xs:sequence>
                <xs:element maxOccurs="unbounded" name="book">
                    <xs:complexType>
                        <xs:sequence>
                            <xs:element name="title" type="xs:string" />
                            <xs:element name="author">
                                <xs:complexType>
                                    <xs:sequence>
                                        <xs:element minOccurs="0" name="name" type="xs:string" />
                                        <xs:element minOccurs="0" name="first-name" type="xs:string" />
                                        <xs:element minOccurs="0" name="last-name" type="xs:string" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="price" type="xs:decimal" />
                        </xs:sequence>
                        <xs:attribute name="genre" type="xs:string" use="required" />
                        <xs:attribute name="publicationdate" type="xs:date" use="required" />
                        <xs:attribute name="ISBN" type="xs:string" use="required" />
                    </xs:complexType>
                </xs:element>
            </xs:sequence>
        </xs:complexType>
    </xs:element>
</xs:schema>
```

## <a name="validating-xml-data-using-xmlschemavalidator"></a><span data-ttu-id="d8943-111">Convalida di dati XML mediante XmlSchemaValidator</span><span class="sxs-lookup"><span data-stu-id="d8943-111">Validating XML Data using XmlSchemaValidator</span></span>

<span data-ttu-id="d8943-112">Per iniziare la convalida di un infoset XML, è necessario innanzitutto inizializzare una nuova istanza della classe <xref:System.Xml.Schema.XmlSchemaValidator> usando il costruttore <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8943-112">To begin validating an XML infoset, you must first initialize a new instance of the <xref:System.Xml.Schema.XmlSchemaValidator> class using the <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor.</span></span>

<span data-ttu-id="d8943-113">Il costruttore <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> accetta gli oggetti <xref:System.Xml.XmlNameTable>, <xref:System.Xml.Schema.XmlSchemaSet>, <xref:System.Xml.XmlNamespaceManager> e un valore <xref:System.Xml.Schema.XmlSchemaValidationFlags> come parametri.</span><span class="sxs-lookup"><span data-stu-id="d8943-113">The <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor takes <xref:System.Xml.XmlNameTable>, <xref:System.Xml.Schema.XmlSchemaSet>, and <xref:System.Xml.XmlNamespaceManager> objects as parameters as well as a <xref:System.Xml.Schema.XmlSchemaValidationFlags> value as a parameter.</span></span> <span data-ttu-id="d8943-114">L'oggetto <xref:System.Xml.XmlNameTable> viene usato per atomizzare stringhe note di spazi dei nomi, quali lo spazio dei nomi dello schema, lo spazio dei nomi XML e così via. Tale oggetto viene passato al metodo <xref:System.Xml.Schema.XmlSchemaDatatype.ParseValue%2A> durante la convalida del contenuto semplice.</span><span class="sxs-lookup"><span data-stu-id="d8943-114">The <xref:System.Xml.XmlNameTable> object is used to atomize well-known namespace strings like the schema namespace, the XML namespace, and so on, and is passed to the <xref:System.Xml.Schema.XmlSchemaDatatype.ParseValue%2A> method while validating simple content.</span></span> <span data-ttu-id="d8943-115">Nell'oggetto <xref:System.Xml.Schema.XmlSchemaSet> sono contenuti gli schemi XML usato per convalidare l'infoset XML.</span><span class="sxs-lookup"><span data-stu-id="d8943-115">The <xref:System.Xml.Schema.XmlSchemaSet> object contains the XML schemas used to validate the XML infoset.</span></span> <span data-ttu-id="d8943-116">L'oggetto <xref:System.Xml.XmlNamespaceManager> viene usato per risolvere gli spazi dei nomi rilevati durante la convalida.</span><span class="sxs-lookup"><span data-stu-id="d8943-116">The <xref:System.Xml.XmlNamespaceManager> object is used to resolve namespaces encountered during validation.</span></span> <span data-ttu-id="d8943-117">Il valore <xref:System.Xml.Schema.XmlSchemaValidationFlags> viene usato per disabilitare determinate funzionalità di convalida.</span><span class="sxs-lookup"><span data-stu-id="d8943-117">The <xref:System.Xml.Schema.XmlSchemaValidationFlags> value is used to disable certain features of validation.</span></span>

<span data-ttu-id="d8943-118">Per altre informazioni sul costruttore <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-118">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="initializing-validation"></a><span data-ttu-id="d8943-119">Inizializzazione della convalida</span><span class="sxs-lookup"><span data-stu-id="d8943-119">Initializing Validation</span></span>

<span data-ttu-id="d8943-120">Dopo la creazione di un oggetto <xref:System.Xml.Schema.XmlSchemaValidator>, sono disponibili due metodi di overload <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> usati per inizializzare lo stato dell'oggetto <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-120">After an <xref:System.Xml.Schema.XmlSchemaValidator> object has been constructed, there are two overloaded <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> methods used to initialize the state of the <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span> <span data-ttu-id="d8943-121">Di seguito sono riportati i due metodi <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8943-121">The following are the two <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> methods.</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

<span data-ttu-id="d8943-122">Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> predefinito consente di inizializzare un oggetto <xref:System.Xml.Schema.XmlSchemaValidator> al relativo stato iniziale e il metodo di overload <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> che accetta un tipo <xref:System.Xml.Schema.XmlSchemaObject> come parametro consente di inizializzare un oggetto <xref:System.Xml.Schema.XmlSchemaValidator> al relativo stato iniziale per la convalida parziale.</span><span class="sxs-lookup"><span data-stu-id="d8943-122">The default <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method initializes an <xref:System.Xml.Schema.XmlSchemaValidator> object to its starting state, and the overloaded <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter initializes an <xref:System.Xml.Schema.XmlSchemaValidator> object to its starting state for partial validation.</span></span>

<span data-ttu-id="d8943-123">È possibile chiamare i metodi <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> solo dopo la creazione di un oggetto <xref:System.Xml.Schema.XmlSchemaValidator> o la chiamata al metodo <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8943-123">Both <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> methods can only be called immediately after an <xref:System.Xml.Schema.XmlSchemaValidator> object has been constructed or after a call to <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>.</span></span>

<span data-ttu-id="d8943-124">Per un esempio del metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>, vedere l'introduzione.</span><span class="sxs-lookup"><span data-stu-id="d8943-124">For an example of the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method, see the example in the introduction.</span></span> <span data-ttu-id="d8943-125">Per altre informazioni sul metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-125">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="partial-validation"></a><span data-ttu-id="d8943-126">Convalida parziale</span><span class="sxs-lookup"><span data-stu-id="d8943-126">Partial Validation</span></span>

<span data-ttu-id="d8943-127">Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> che accetta un tipo <xref:System.Xml.Schema.XmlSchemaObject> come parametro consente di inizializzare un oggetto <xref:System.Xml.Schema.XmlSchemaValidator> al relativo stato iniziale per la convalida parziale.</span><span class="sxs-lookup"><span data-stu-id="d8943-127">The <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter initializes an <xref:System.Xml.Schema.XmlSchemaValidator> object to its starting state for partial validation.</span></span>

<span data-ttu-id="d8943-128">Nell'esempio seguente un tipo <xref:System.Xml.Schema.XmlSchemaObject> viene inizializzato per la convalida parziale usando il metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d8943-128">In the following example, an <xref:System.Xml.Schema.XmlSchemaObject> is initialized for partial validation using the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d8943-129">L'elemento dello schema `orderNumber` viene passato selezionandolo in base al tipo <xref:System.Xml.XmlQualifiedName> nella raccolta <xref:System.Xml.Schema.XmlSchemaObjectTable> restituita dalla proprietà <xref:System.Xml.Schema.XmlSchemaSet.GlobalElements%2A> dell'oggetto <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="d8943-129">The `orderNumber` schema element is passed by selecting the schema element by <xref:System.Xml.XmlQualifiedName> in the <xref:System.Xml.Schema.XmlSchemaObjectTable> collection returned by the <xref:System.Xml.Schema.XmlSchemaSet.GlobalElements%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet> object.</span></span> <span data-ttu-id="d8943-130">Questo elemento specifico viene quindi convalidato dall'oggetto <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-130">The <xref:System.Xml.Schema.XmlSchemaValidator> object then validates this specific element.</span></span>

```vb
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()
schemaSet.Add(Nothing, "schema.xsd")
schemaSet.Compile()
Dim nameTable As NameTable = New NameTable()
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(nameTable)

Dim validator As XmlSchemaValidator = New XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None)
validator.Initialize(schemaSet.GlobalElements.Item(New XmlQualifiedName("orderNumber")))

validator.ValidateElement("orderNumber", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateText("123")
validator.ValidateEndElement(Nothing)
```

```csharp
XmlSchemaSet schemaSet = new XmlSchemaSet();
schemaSet.Add(null, "schema.xsd");
schemaSet.Compile();
NameTable nameTable = new NameTable();
XmlNamespaceManager manager = new XmlNamespaceManager(nameTable);

XmlSchemaValidator validator = new XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None);
validator.Initialize(schemaSet.GlobalElements[new XmlQualifiedName("orderNumber")]);

validator.ValidateElement("orderNumber", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateText("123");
validator.ValidateEndElement(null);
```

<span data-ttu-id="d8943-131">Nell'esempio il seguente schema XML viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="d8943-131">The example takes the following XML schema as input.</span></span>

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="orderNumber" type="xs:int" />
</xs:schema>
```

<span data-ttu-id="d8943-132">Per altre informazioni sul metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-132">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="adding-additional-schemas"></a><span data-ttu-id="d8943-133">Aggiunta di altri schemi</span><span class="sxs-lookup"><span data-stu-id="d8943-133">Adding Additional Schemas</span></span>

<span data-ttu-id="d8943-134">Per aggiungere uno schema XML al set di schemi usato durante la convalida, viene usando il metodo <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> della classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-134">The <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method of the <xref:System.Xml.Schema.XmlSchemaValidator> class is used to add an XML schema to the set of schemas used during validation.</span></span> <span data-ttu-id="d8943-135">Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> può essere usato per simulare l'effetto prodotto dal rilevamento di uno schema XML inline nell'infoset XML da convalidare.</span><span class="sxs-lookup"><span data-stu-id="d8943-135">The <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method can be used to simulate the effect of encountering an inline XML schema in the XML infoset being validated.</span></span>

> [!NOTE]
> <span data-ttu-id="d8943-136">Lo spazio dei nomi di destinazione del parametro <xref:System.Xml.Schema.XmlSchema> non può corrispondere ad alcun elemento o attributo già rilevato dall'oggetto <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-136">The target namespace of the <xref:System.Xml.Schema.XmlSchema> parameter cannot match that of any element or attribute already encountered by the <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span>
>
> <span data-ttu-id="d8943-137">Se il valore <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessInlineSchema?displayProperty=nameWithType> non è stato passato come parametro al costruttore <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> non esegue alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="d8943-137">If the <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessInlineSchema?displayProperty=nameWithType> value was not passed as a parameter to the <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor, the <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method does nothing.</span></span>

<span data-ttu-id="d8943-138">Il risultato del metodo <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> dipende dal contesto corrente del nodo XML da convalidare.</span><span class="sxs-lookup"><span data-stu-id="d8943-138">The result of the <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method is dependant on the current XML node context being validated.</span></span> <span data-ttu-id="d8943-139">Per altre informazioni sui contesti di convalida, vedere la sezione "Contesto di convalida" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d8943-139">For more information about validation contexts, see the "Validation Context" section of this topic.</span></span>

<span data-ttu-id="d8943-140">Per altre informazioni sul metodo <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-140">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="validating-elements-attributes-and-content"></a><span data-ttu-id="d8943-141">Convalida di elementi, attributi e contenuto</span><span class="sxs-lookup"><span data-stu-id="d8943-141">Validating Elements, Attributes, and Content</span></span>

<span data-ttu-id="d8943-142">La classe <xref:System.Xml.Schema.XmlSchemaValidator> fornisce diversi metodi usati per convalidare elementi, attributi e contenuto in un infoset XML in base a schemi XML.</span><span class="sxs-lookup"><span data-stu-id="d8943-142">The <xref:System.Xml.Schema.XmlSchemaValidator> class provides several methods used to validate elements, attributes, and content in an XML infoset against XML schemas.</span></span> <span data-ttu-id="d8943-143">Nella tabella seguente viene descritto ciascuno di questi metodi.</span><span class="sxs-lookup"><span data-stu-id="d8943-143">The following table describes each of these methods.</span></span>

|<span data-ttu-id="d8943-144">Metodo</span><span class="sxs-lookup"><span data-stu-id="d8943-144">Method</span></span>|<span data-ttu-id="d8943-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8943-145">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|<span data-ttu-id="d8943-146">Convalida il nome dell'elemento nel contesto corrente.</span><span class="sxs-lookup"><span data-stu-id="d8943-146">Validates the element name in the current context.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|<span data-ttu-id="d8943-147">Convalida l'attributo nel contesto dell'elemento corrente oppure in base all'oggetto <xref:System.Xml.Schema.XmlSchemaAttribute> passato come parametro al metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8943-147">Validates the attribute in the current element context or against the <xref:System.Xml.Schema.XmlSchemaAttribute> object passed as a parameter to the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|<span data-ttu-id="d8943-148">Verifica la presenza di tutti gli attributi richiesti nel contesto dell'elemento e prepara l'oggetto <xref:System.Xml.Schema.XmlSchemaValidator> per la convalida del contenuto figlio dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="d8943-148">Verifies whether all the required attributes in the element context are present and prepares the <xref:System.Xml.Schema.XmlSchemaValidator> object to validate the child content of the element.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|<span data-ttu-id="d8943-149">Verifica se il testo è consentito nel contesto dell'elemento corrente e accumula il testo da convalidare se l'elemento corrente dispone di contenuto semplice.</span><span class="sxs-lookup"><span data-stu-id="d8943-149">Validates whether text is allowed in the current element context, and accumulates the text for validation if the current element has simple content.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|<span data-ttu-id="d8943-150">Verifica se gli spazi vuoti sono consentiti nel contesto dell'elemento corrente e accumula gli spazi vuoti da convalidare se l'elemento corrente dispone di contenuto semplice.</span><span class="sxs-lookup"><span data-stu-id="d8943-150">Validates whether white-space is allowed in the current element context, and accumulates the white-space for validation whether the current element has simple content.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|<span data-ttu-id="d8943-151">Verifica se il contenuto di testo dell'elemento è valido in base al relativo tipo di dati per gli elementi con contenuto semplice e verifica se il contenuto dell'elemento corrente è completo per gli elementi con contenuto complesso.</span><span class="sxs-lookup"><span data-stu-id="d8943-151">Verifies whether the text content of the element is valid according to its data type for elements with simple content, and verifies whether the content of the current element is complete for elements with complex content.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|<span data-ttu-id="d8943-152">Ignora la convalida del contenuto dell'elemento corrente e prepara l'oggetto <xref:System.Xml.Schema.XmlSchemaValidator> per la convalida del contenuto nel contesto dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="d8943-152">Skips validation of the current element content and prepares the <xref:System.Xml.Schema.XmlSchemaValidator> object to validate content in the parent element's context.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|<span data-ttu-id="d8943-153">Termina la convalida e verifica i vincoli di identità per l'intero documento XML se è impostata l'opzione di convalida <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessIdentityConstraints>.</span><span class="sxs-lookup"><span data-stu-id="d8943-153">Ends validation and checks identity constraints for the entire XML document if the <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessIdentityConstraints> validation option is set.</span></span>|

> [!NOTE]
> <span data-ttu-id="d8943-154">La classe <xref:System.Xml.Schema.XmlSchemaValidator> presenta una transizione dello stato definita che impone la sequenza e l'occorrenza delle chiamate effettuate a ciascuno dei metodi descritti nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="d8943-154">The <xref:System.Xml.Schema.XmlSchemaValidator> class has a defined state transition that enforces the sequence and occurrence of calls made to each of the methods described in the previous table.</span></span> <span data-ttu-id="d8943-155">La transizione dello stato specifica per la classe <xref:System.Xml.Schema.XmlSchemaValidator> è descritta nella sezione "Transizione dello stato di XmlSchemaValidator" di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d8943-155">The specific state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class is described in the "XmlSchemaValidator State Transition" section of this topic.</span></span>

<span data-ttu-id="d8943-156">Per un esempio dei metodi usati per convalidare elementi, attributi e contenuto di un infoset XML, vedere l'esempio nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="d8943-156">For an example of the methods used to validate elements, attributes, and content in an XML infoset, see the example in the previous section.</span></span> <span data-ttu-id="d8943-157">Per altre informazioni su questi metodi, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-157">For more information about these methods, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="validating-content-using-an-xmlvaluegetter"></a><span data-ttu-id="d8943-158">Convalida del contenuto mediante XmlValueGetter</span><span class="sxs-lookup"><span data-stu-id="d8943-158">Validating Content Using an XmlValueGetter</span></span>

<span data-ttu-id="d8943-159">Il <xref:System.Xml.Schema.XmlValueGetter>`delegate` può essere usato per passare il valore di nodi Attribute, di nodi di tipo text o di nodi con spazi vuoti come tipi CLR (Common Language Runtime) compatibili con il tipo XSD (XML Schema Definition Language) del nodo Attribute, di tipo text o con spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="d8943-159">The <xref:System.Xml.Schema.XmlValueGetter>`delegate` can be used to pass the value of attribute, text, or white-space nodes as a Common Language Runtime (CLR) types compatible with the XML Schema Definition Language (XSD) type of the attribute, text, or white-space node.</span></span> <span data-ttu-id="d8943-160">Un <xref:System.Xml.Schema.XmlValueGetter>`delegate` è utile se il valore CLR di un nodo Attribute, di un nodo di tipo text o di un nodo con spazi vuoti è già disponibile. Inoltre, evita la necessità di convertire il nodo in `string` e di analizzarlo nuovamente per la convalida.</span><span class="sxs-lookup"><span data-stu-id="d8943-160">An <xref:System.Xml.Schema.XmlValueGetter>`delegate` is useful if the CLR value of an attribute, text, or white-space node is already available, and avoids the cost of converting it to a `string` and then reparsing it again for validation.</span></span>

<span data-ttu-id="d8943-161">I metodi di overload <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> e <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> accettano il valore dei nodi Attribute, dei nodi di tipo text o dei nodi con spazi vuoti come `string` o come <xref:System.Xml.Schema.XmlValueGetter>`delegate`.</span><span class="sxs-lookup"><span data-stu-id="d8943-161">The <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> methods are overloaded and accept the value of attribute, text, or white-space nodes as a `string` or <xref:System.Xml.Schema.XmlValueGetter>`delegate`.</span></span>

<span data-ttu-id="d8943-162">I seguenti metodi della classe <xref:System.Xml.Schema.XmlSchemaValidator> accettano un tipo <xref:System.Xml.Schema.XmlValueGetter>`delegate` come parametro.</span><span class="sxs-lookup"><span data-stu-id="d8943-162">The following methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class accept an <xref:System.Xml.Schema.XmlValueGetter>`delegate` as a parameter.</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>

<span data-ttu-id="d8943-163">Di seguito è riportato un <xref:System.Xml.Schema.XmlValueGetter>`delegate` di esempio descritto nell'esempio della classe <xref:System.Xml.Schema.XmlSchemaValidator> nell'introduzione.</span><span class="sxs-lookup"><span data-stu-id="d8943-163">The following is an example <xref:System.Xml.Schema.XmlValueGetter>`delegate` taken from the <xref:System.Xml.Schema.XmlSchemaValidator> class example in the introduction.</span></span> <span data-ttu-id="d8943-164">Il <xref:System.Xml.Schema.XmlValueGetter>`delegate` restituisce il valore di un attributo come oggetto <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="d8943-164">The <xref:System.Xml.Schema.XmlValueGetter>`delegate` returns the value of an attribute as a <xref:System.DateTime> object.</span></span> <span data-ttu-id="d8943-165">Per convalidare l'oggetto <xref:System.DateTime> restituito dall'oggetto <xref:System.Xml.Schema.XmlValueGetter>, l'oggetto <xref:System.Xml.Schema.XmlSchemaValidator> lo converte innanzitutto in ValueType (ovvero nel mapping predefinito di CLR per il tipo XSD) per il tipo di dati dell'attributo, quindi verifica i facet nel valore convertito.</span><span class="sxs-lookup"><span data-stu-id="d8943-165">To validate this <xref:System.DateTime> object returned by the <xref:System.Xml.Schema.XmlValueGetter>, the <xref:System.Xml.Schema.XmlSchemaValidator> object first converts it to the ValueType (ValueType is the default CLR mapping for the XSD type) for the data type of the attribute and then checks facets on the converted value.</span></span>

```vb
Shared dateTimeGetterContent As Object

Shared Function DateTimeGetterHandle() As Object
    Return dateTimeGetterContent
End Function

Shared Function DateTimeGetter(dateTime As DateTime) As XmlValueGetter
    dateTimeGetterContent = dateTime
    Return New XmlValueGetter(AddressOf DateTimeGetterHandle)
End Function
```

```csharp
static object dateTimeGetterContent;

static object DateTimeGetterHandle()
{
    return dateTimeGetterContent;
}

static XmlValueGetter DateTimeGetter(DateTime dateTime)
{
    dateTimeGetterContent = dateTime;
    return new XmlValueGetter(dateTimeGetterHandle);
}
```

<span data-ttu-id="d8943-166">Per un esempio completo dell'oggetto <xref:System.Xml.Schema.XmlValueGetter>`delegate`, vedere l'introduzione.</span><span class="sxs-lookup"><span data-stu-id="d8943-166">For a complete example of the <xref:System.Xml.Schema.XmlValueGetter>`delegate`, see the example in the introduction.</span></span> <span data-ttu-id="d8943-167">Per altre informazioni sul <xref:System.Xml.Schema.XmlValueGetter>`delegate`, vedere la documentazione di riferimento per il tipo <xref:System.Xml.Schema.XmlValueGetter> e per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-167">For more information about the <xref:System.Xml.Schema.XmlValueGetter>`delegate`, see the <xref:System.Xml.Schema.XmlValueGetter>, and <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="post-schema-validation-information"></a><span data-ttu-id="d8943-168">informazioni sulla convalida post-schema</span><span class="sxs-lookup"><span data-stu-id="d8943-168">Post-Schema-Validation-Information</span></span>

<span data-ttu-id="d8943-169">La classe <xref:System.Xml.Schema.XmlSchemaInfo> rappresenta alcune delle informazioni di convalida post-schema di un nodo XML convalidata dalla classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-169">The <xref:System.Xml.Schema.XmlSchemaInfo> class represents some of the Post-Schema-Validation-Information of an XML node validated by the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span> <span data-ttu-id="d8943-170">Diversi metodi della classe <xref:System.Xml.Schema.XmlSchemaValidator> accettano un oggetto <xref:System.Xml.Schema.XmlSchemaInfo> come parametro `null` (`out`) facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d8943-170">Various methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class accept an <xref:System.Xml.Schema.XmlSchemaInfo> object as an optional, (`null`) `out` parameter.</span></span>

<span data-ttu-id="d8943-171">Una volta eseguita la convalida, le proprietà dell'oggetto <xref:System.Xml.Schema.XmlSchemaInfo> vengono impostate con i risultati della convalida.</span><span class="sxs-lookup"><span data-stu-id="d8943-171">Upon successful validation, properties of the <xref:System.Xml.Schema.XmlSchemaInfo> object are set with the results of the validation.</span></span> <span data-ttu-id="d8943-172">Ad esempio, dopo la convalida di un attributo usando il metodo <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, le proprietà <xref:System.Xml.Schema.XmlSchemaInfo>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaType%2A> e <xref:System.Xml.Schema.XmlSchemaInfo.MemberType%2A> dell'oggetto <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A>, se specificate, vengono impostate con i risultati della convalida.</span><span class="sxs-lookup"><span data-stu-id="d8943-172">For example, upon successful validation of an attribute using the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method, the <xref:System.Xml.Schema.XmlSchemaInfo> object's (if specified) <xref:System.Xml.Schema.XmlSchemaInfo.SchemaAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaType%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.MemberType%2A>, and <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> properties are set with the results of the validation.</span></span>

<span data-ttu-id="d8943-173">Il seguente metodo della classe <xref:System.Xml.Schema.XmlSchemaValidator> accetta un oggetto <xref:System.Xml.Schema.XmlSchemaInfo> come parametro out.</span><span class="sxs-lookup"><span data-stu-id="d8943-173">The following <xref:System.Xml.Schema.XmlSchemaValidator> class methods accept an <xref:System.Xml.Schema.XmlSchemaInfo> object as an out parameter.</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>

<span data-ttu-id="d8943-174">Per un esempio completo della classe <xref:System.Xml.Schema.XmlSchemaInfo>, vedere l'introduzione.</span><span class="sxs-lookup"><span data-stu-id="d8943-174">For a complete example of the <xref:System.Xml.Schema.XmlSchemaInfo> class, see the example in the introduction.</span></span> <span data-ttu-id="d8943-175">Per altre informazioni sulla classe <xref:System.Xml.Schema.XmlSchemaInfo>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaInfo>.</span><span class="sxs-lookup"><span data-stu-id="d8943-175">For more information about the <xref:System.Xml.Schema.XmlSchemaInfo> class, see the <xref:System.Xml.Schema.XmlSchemaInfo> class reference documentation.</span></span>

### <a name="retrieving-expected-particles-attributes-and-unspecified-default-attributes"></a><span data-ttu-id="d8943-176">Recupero di particelle e attributi previsti e di attributi predefiniti non specificati</span><span class="sxs-lookup"><span data-stu-id="d8943-176">Retrieving Expected Particles, Attributes, and Unspecified Default Attributes</span></span>

<span data-ttu-id="d8943-177">La classe <xref:System.Xml.Schema.XmlSchemaValidator> fornisce i metodi <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> e <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> per il recupero di particelle e attributi previsti e di attributi predefiniti non specificati nel contesto di convalida corrente.</span><span class="sxs-lookup"><span data-stu-id="d8943-177">The <xref:System.Xml.Schema.XmlSchemaValidator> class provides the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> methods to retrieve the expected particles, attributes, and unspecified default attributes in the current validation context.</span></span>

#### <a name="retrieving-expected-particles"></a><span data-ttu-id="d8943-178">Recupero di particelle previste</span><span class="sxs-lookup"><span data-stu-id="d8943-178">Retrieving Expected Particles</span></span>

<span data-ttu-id="d8943-179">Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituisce una matrice di oggetti <xref:System.Xml.Schema.XmlSchemaParticle> contenenti le particelle previste nel contesto dell'elemento corrente.</span><span class="sxs-lookup"><span data-stu-id="d8943-179">The <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns an array of <xref:System.Xml.Schema.XmlSchemaParticle> objects containing the expected particles in the current element context.</span></span> <span data-ttu-id="d8943-180">Le particelle valide che possono essere restituite dal metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> sono istanze delle classi <xref:System.Xml.Schema.XmlSchemaElement> e <xref:System.Xml.Schema.XmlSchemaAny>.</span><span class="sxs-lookup"><span data-stu-id="d8943-180">The valid particles that can be returned by the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method are instances of the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAny> classes.</span></span>

<span data-ttu-id="d8943-181">Se il compositor per il modello di contenuto è `xs:sequence`, verrà restituita solo la particella successiva nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="d8943-181">When the compositor for the content model is an `xs:sequence`, only the next particle in the sequence is returned.</span></span> <span data-ttu-id="d8943-182">Se il compositor per il modello di contenuto è `xs:all` o `xs:choice`, verranno restituite tutte le particelle che possono seguire nel contesto dell'elemento corrente.</span><span class="sxs-lookup"><span data-stu-id="d8943-182">If the compositor for the content model is an `xs:all` or an `xs:choice`, then all valid particles that could follow in the current element context are returned.</span></span>

> [!NOTE]
> <span data-ttu-id="d8943-183">Se il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> viene chiamato subito dopo il metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà tutti gli elementi globali.</span><span class="sxs-lookup"><span data-stu-id="d8943-183">If the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method is called immediately after calling the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method, the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns all global elements.</span></span>

<span data-ttu-id="d8943-184">Ad esempio, nello schema XSD (XML Schema Definition Language) e nel documento XML seguenti, dopo la convalida dell'elemento `book`, l'elemento `book` è il contesto dell'elemento corrente.</span><span class="sxs-lookup"><span data-stu-id="d8943-184">For example, in the XML Schema Definition Language (XSD) schema and XML document that follow, after validating the `book` element, the `book` element is the current element context.</span></span> <span data-ttu-id="d8943-185">Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituisce una matrice contenente un singolo oggetto <xref:System.Xml.Schema.XmlSchemaElement> che rappresenta l'elemento `title`.</span><span class="sxs-lookup"><span data-stu-id="d8943-185">The <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns an array containing a single <xref:System.Xml.Schema.XmlSchemaElement> object representing the `title` element.</span></span> <span data-ttu-id="d8943-186">Se il contesto di convalida è l'elemento `title`, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituisce una matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="d8943-186">When the validation context is the `title` element, the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns an empty array.</span></span> <span data-ttu-id="d8943-187">Se il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> viene chiamato dopo la convalida dell'elemento `title` ma prima della convalida dell'elemento `description`, restituirà una matrice contenente un singolo oggetto <xref:System.Xml.Schema.XmlSchemaElement> che rappresenta l'elemento `description`.</span><span class="sxs-lookup"><span data-stu-id="d8943-187">If the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method is called after the `title` element has been validated but before the `description` element has been validated, it returns an array containing a single <xref:System.Xml.Schema.XmlSchemaElement> object representing the `description` element.</span></span> <span data-ttu-id="d8943-188">Se il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> viene chiamato dopo la convalida dell'elemento `description`, restituirà una matrice contenente un singolo oggetto <xref:System.Xml.Schema.XmlSchemaAny> che rappresenta il carattere jolly.</span><span class="sxs-lookup"><span data-stu-id="d8943-188">If the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method is called after the `description` element has been validated then it returns an array containing a single <xref:System.Xml.Schema.XmlSchemaAny> object representing the wildcard.</span></span>

```vb
Dim reader As XmlReader =  XmlReader.Create("input.xml")

Dim schemaSet As New XmlSchemaSet()
schemaSet.Add(Nothing, "schema.xsd")
Dim manager As New XmlNamespaceManager(reader.NameTable)

Dim validator As New XmlSchemaValidator(reader.NameTable,schemaSet,manager,XmlSchemaValidationFlags.None)
validator.Initialize()

validator.ValidateElement("book", "", Nothing)

validator.ValidateEndOfAttributes(Nothing)
For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next

validator.ValidateElement("title", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next
validator.ValidateEndElement(Nothing)

For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next

validator.ValidateElement("description", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateEndElement(Nothing)

For Each particle As XmlSchemaParticle In validator.GetExpectedParticles()
    Console.WriteLine(particle.GetType())
Next

validator.ValidateElement("namespace", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateEndElement(Nothing)

validator.ValidateEndElement(Nothing)
```

```csharp
XmlReader reader = XmlReader.Create("input.xml");

var schemaSet = new XmlSchemaSet();
schemaSet.Add(null, "schema.xsd");
var manager = new XmlNamespaceManager(reader.NameTable);

var validator = new XmlSchemaValidator(reader.NameTable, schemaSet, manager, XmlSchemaValidationFlags.None);
validator.Initialize();

validator.ValidateElement("book", "", null);

validator.ValidateEndOfAttributes(null);
foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}

validator.ValidateElement("title", "", null);
validator.ValidateEndOfAttributes(null);
foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}
validator.ValidateEndElement(null);

foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}

validator.ValidateElement("description", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateEndElement(null);

foreach (XmlSchemaParticle particle in validator.GetExpectedParticles())
{
    Console.WriteLine(particle.GetType());
}

validator.ValidateElement("namespace", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateEndElement(null);

validator.ValidateEndElement(null);
```

 <span data-ttu-id="d8943-189">Nell'esempio viene preso come input il codice XML seguente:</span><span class="sxs-lookup"><span data-stu-id="d8943-189">The example takes the following XML as input:</span></span>

```xml
<xs:schema xmlns:xs="http://www.w3c.org/2001/XMLSchema">
  <xs:element name="book">
    <xs:sequence>
      <xs:element name="title" type="xs:string" />
      <xs:element name="description" type="xs:string" />
      <xs:any processContent="lax" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:element>
</xs:schema>
```

<span data-ttu-id="d8943-190">Nell'esempio il seguente schema XSD viene preso come input:</span><span class="sxs-lookup"><span data-stu-id="d8943-190">The example takes the following XSD schema as input:</span></span>

```xml
<book>
  <title>My Book</title>
  <description>My Book's Description</description>
  <namespace>System.Xml.Schema</namespace>
</book>
```

> [!NOTE]
> <span data-ttu-id="d8943-191">I risultati dei metodi <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> e <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> della classe <xref:System.Xml.Schema.XmlSchemaValidator> dipendono dal contesto corrente da convalidare.</span><span class="sxs-lookup"><span data-stu-id="d8943-191">The results of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class are dependent on the current context being validated.</span></span> <span data-ttu-id="d8943-192">Per altre informazioni, vedere la sezione "Contesto di convalida" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d8943-192">For more information, see the "Validation Context" section of this topic.</span></span>

<span data-ttu-id="d8943-193">Per un esempio del metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, vedere l'introduzione.</span><span class="sxs-lookup"><span data-stu-id="d8943-193">For an example of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method, see the example in the introduction.</span></span> <span data-ttu-id="d8943-194">Per altre informazioni sul metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-194">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="retrieving-expected-attributes"></a><span data-ttu-id="d8943-195">Recupero di attributi previsti</span><span class="sxs-lookup"><span data-stu-id="d8943-195">Retrieving Expected Attributes</span></span>

<span data-ttu-id="d8943-196">Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituisce una matrice di oggetti <xref:System.Xml.Schema.XmlSchemaAttribute> contenenti gli attributi previsti nel contesto dell'elemento corrente.</span><span class="sxs-lookup"><span data-stu-id="d8943-196">The <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method returns an array of <xref:System.Xml.Schema.XmlSchemaAttribute> objects containing the expected attributes in the current element context.</span></span>

<span data-ttu-id="d8943-197">Ad esempio, nell'esempio dell'introduzione il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> viene usato per recuperare tutti gli attributi dell'elemento `book`.</span><span class="sxs-lookup"><span data-stu-id="d8943-197">For example, in the example in the introduction, the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method is used to retrieve all the attributes of the `book` element.</span></span>

<span data-ttu-id="d8943-198">Se il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> viene chiamato subito dopo il metodo <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>, verranno restituiti tutti gli attributi che possono essere presenti nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="d8943-198">If you call the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method immediately after the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> method, all the attributes that could appear in the XML document are returned.</span></span> <span data-ttu-id="d8943-199">Tuttavia, se il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> viene chiamato dopo una o più chiamate al metodo <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, verranno restituiti gli attributi che non sono ancora stati convalidati per l'elemento corrente.</span><span class="sxs-lookup"><span data-stu-id="d8943-199">However, if you call the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method after one or more calls to the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method, the attributes that have not yet been validated for the current element are returned.</span></span>

> [!NOTE]
> <span data-ttu-id="d8943-200">I risultati dei metodi <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> e <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> della classe <xref:System.Xml.Schema.XmlSchemaValidator> dipendono dal contesto corrente da convalidare.</span><span class="sxs-lookup"><span data-stu-id="d8943-200">The results of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class are dependent on the current context being validated.</span></span> <span data-ttu-id="d8943-201">Per altre informazioni, vedere la sezione "Contesto di convalida" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d8943-201">For more information, see the "Validation Context" section of this topic.</span></span>

<span data-ttu-id="d8943-202">Per un esempio del metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, vedere l'introduzione.</span><span class="sxs-lookup"><span data-stu-id="d8943-202">For an example of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method, see the example in the introduction.</span></span> <span data-ttu-id="d8943-203">Per altre informazioni sul metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-203">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="retrieving-unspecified-default-attributes"></a><span data-ttu-id="d8943-204">Recupero di attributi predefiniti non specificati</span><span class="sxs-lookup"><span data-stu-id="d8943-204">Retrieving Unspecified Default Attributes</span></span>

<span data-ttu-id="d8943-205">Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> compila il tipo <xref:System.Collections.ArrayList> specificato con gli oggetti <xref:System.Xml.Schema.XmlSchemaAttribute> per gli attributi con valori predefiniti che non sono stati convalidati in precedenza usando il metodo <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> nel contesto dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="d8943-205">The <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method populates the <xref:System.Collections.ArrayList> specified with <xref:System.Xml.Schema.XmlSchemaAttribute> objects for any attributes with default values that have not been previously validated using the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method in the element context.</span></span> <span data-ttu-id="d8943-206">Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> deve essere chiamato dopo aver chiamato il metodo <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> in ogni attributo del contesto dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="d8943-206">The <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method should be called after calling the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method on each attribute in the element context.</span></span> <span data-ttu-id="d8943-207">Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> deve essere usato per determinare gli attributi predefiniti da inserire nel documento XML da convalidare, è necessario usare .</span><span class="sxs-lookup"><span data-stu-id="d8943-207">The <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method should be used to determine what default attributes are to be inserted into the XML document being validated.</span></span>

<span data-ttu-id="d8943-208">Per altre informazioni sul metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-208">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="handling-schema-validation-events"></a><span data-ttu-id="d8943-209">Gestione degli eventi di convalida dello schema</span><span class="sxs-lookup"><span data-stu-id="d8943-209">Handling Schema Validation Events</span></span>

<span data-ttu-id="d8943-210">Gli avvisi e gli errori di convalida dello schema rilevati durante la convalida sono gestiti dall'evento <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> della classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-210">Schema validation warnings and errors encountered during validation are handled by the <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> event of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span>

<span data-ttu-id="d8943-211">Gli avvisi di convalida dello schema presentano un valore <xref:System.Xml.Schema.XmlSeverityType> pari a <xref:System.Xml.Schema.XmlSeverityType.Warning> mentre gli errori di convalida dello schema presentano un valore <xref:System.Xml.Schema.XmlSeverityType> pari a <xref:System.Xml.Schema.XmlSeverityType.Error>.</span><span class="sxs-lookup"><span data-stu-id="d8943-211">Schema validation warnings have an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Warning> and schema validation errors have an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Error>.</span></span> <span data-ttu-id="d8943-212">Se non è stato assegnato alcun evento <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler>, verrà generato un tipo <xref:System.Xml.Schema.XmlSchemaValidationException> per tutti gli errori di convalida dello schema con un valore <xref:System.Xml.Schema.XmlSeverityType> pari a <xref:System.Xml.Schema.XmlSeverityType.Error>.</span><span class="sxs-lookup"><span data-stu-id="d8943-212">If no <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> has been assigned, an <xref:System.Xml.Schema.XmlSchemaValidationException> is thrown for all schema validation errors with an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Error>.</span></span> <span data-ttu-id="d8943-213">Tuttavia, non verrà generato un tipo <xref:System.Xml.Schema.XmlSchemaValidationException> per gli avvisi di convalida dello schema con un valore <xref:System.Xml.Schema.XmlSeverityType> pari a <xref:System.Xml.Schema.XmlSeverityType.Warning>.</span><span class="sxs-lookup"><span data-stu-id="d8943-213">However, an <xref:System.Xml.Schema.XmlSchemaValidationException> is not thrown for schema validation warnings with an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Warning>.</span></span>

<span data-ttu-id="d8943-214">Di seguito è riportato un esempio di un ti<xref:System.Xml.Schema.ValidationEventHandler> che riceve avvisi ed errori di convalida dello schema rilevati durante la convalida dello schema nell'esempio dell'introduzione.</span><span class="sxs-lookup"><span data-stu-id="d8943-214">The following is an example of a <xref:System.Xml.Schema.ValidationEventHandler> that receives schema validation warnings and errors encountered during schema validation taken from the example in the introduction.</span></span>

```vb
Shared Sub SchemaValidationEventHandler(sender As Object, e As ValidationEventArgs)

    Select Case e.Severity
        Case XmlSeverityType.Error
            Console.WriteLine(vbCrLf & "Error: {0}", e.Message)
            Exit Sub
        Case XmlSeverityType.Warning
            Console.WriteLine(vbCrLf & "Warning: {0}", e.Message)
            Exit Sub
    End Select
End Sub
```

```csharp
static void SchemaValidationEventHandler(object sender, ValidationEventArgs e)
{
    switch (e.Severity)
    {
        case XmlSeverityType.Error:
            Console.WriteLine("\nError: {0}", e.Message);
            break;
        case XmlSeverityType.Warning:
            Console.WriteLine("\nWarning: {0}", e.Message);
            break;
    }
}
```

<span data-ttu-id="d8943-215">Per un esempio completo del tipo <xref:System.Xml.Schema.ValidationEventHandler>, vedere l'introduzione.</span><span class="sxs-lookup"><span data-stu-id="d8943-215">For a complete example of the <xref:System.Xml.Schema.ValidationEventHandler>, see the example in the introduction.</span></span> <span data-ttu-id="d8943-216">Per altre informazioni, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaInfo>.</span><span class="sxs-lookup"><span data-stu-id="d8943-216">For more information, see the <xref:System.Xml.Schema.XmlSchemaInfo> class reference documentation.</span></span>

## <a name="xmlschemavalidator-state-transition"></a><span data-ttu-id="d8943-217">Transizione dello stato di XmlSchemaValidator</span><span class="sxs-lookup"><span data-stu-id="d8943-217">XmlSchemaValidator State Transition</span></span>

<span data-ttu-id="d8943-218">La classe <xref:System.Xml.Schema.XmlSchemaValidator> presenta una transizione dello stato definita che impone la sequenza e l'occorrenza delle chiamate effettuate a ciascuno dei metodi usati per convalidare elementi, attributi e contenuto di un infoset XML.</span><span class="sxs-lookup"><span data-stu-id="d8943-218">The <xref:System.Xml.Schema.XmlSchemaValidator> class has a defined state transition that enforces the sequence and occurrence of calls made to each of the methods used to validate elements, attributes, and content in an XML infoset.</span></span>

<span data-ttu-id="d8943-219">Nella tabella seguente vengono descritti la transizione dello stato della classe <xref:System.Xml.Schema.XmlSchemaValidator>, nonché la sequenza e l'occorrenza delle chiamate del metodo che possono essere effettuate in ciascuno stato.</span><span class="sxs-lookup"><span data-stu-id="d8943-219">The following table describes the state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class, and the sequence and occurrence of method calls that can be made in each state.</span></span>

|<span data-ttu-id="d8943-220">State</span><span class="sxs-lookup"><span data-stu-id="d8943-220">State</span></span>|<span data-ttu-id="d8943-221">Transizione</span><span class="sxs-lookup"><span data-stu-id="d8943-221">Transition</span></span>|
|-----------|----------------|
|<span data-ttu-id="d8943-222">Convalida</span><span class="sxs-lookup"><span data-stu-id="d8943-222">Validate</span></span>|<span data-ttu-id="d8943-223"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> &#124; TopLevel\*) <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A></span><span class="sxs-lookup"><span data-stu-id="d8943-223"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> &#124; TopLevel\*) <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A></span></span>|
|<span data-ttu-id="d8943-224">TopLevel</span><span class="sxs-lookup"><span data-stu-id="d8943-224">TopLevel</span></span>|<span data-ttu-id="d8943-225"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span><span class="sxs-lookup"><span data-stu-id="d8943-225"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span></span>|
|<span data-ttu-id="d8943-226">Elemento</span><span class="sxs-lookup"><span data-stu-id="d8943-226">Element</span></span>|<span data-ttu-id="d8943-227"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A><xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Contenuto\*)?</span><span class="sxs-lookup"><span data-stu-id="d8943-227"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\*)?</span></span> <span data-ttu-id="d8943-228"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> &#124;</span><span class="sxs-lookup"><span data-stu-id="d8943-228"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> &#124;</span></span><br /><br /> <span data-ttu-id="d8943-229"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A><xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> &#124; \* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A></span><span class="sxs-lookup"><span data-stu-id="d8943-229"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span></span><br /><br /> <span data-ttu-id="d8943-230"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A><xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> \* &#124; di <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> contenuto \* <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A></span><span class="sxs-lookup"><span data-stu-id="d8943-230"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span></span>|
|<span data-ttu-id="d8943-231">Contenuto</span><span class="sxs-lookup"><span data-stu-id="d8943-231">Content</span></span>|<span data-ttu-id="d8943-232"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span><span class="sxs-lookup"><span data-stu-id="d8943-232"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span></span>|

> [!NOTE]
> <span data-ttu-id="d8943-233">Se la chiamata al metodo non viene effettuata nella sequenza corretta in base allo stato corrente di un oggetto <xref:System.InvalidOperationException>, verrà generato un oggetto <xref:System.Xml.Schema.XmlSchemaValidator> da parte di ciascuno dei metodi della tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="d8943-233">An <xref:System.InvalidOperationException> is thrown by each of the methods in the table above when the call to the method is made in the incorrect sequence according to the current state of an <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span>

<span data-ttu-id="d8943-234">Nella tabella precedente, relativa alla transizione dello stato, vengono usati i segni di punteggiatura per descrivere i metodi e alti stati che possono essere chiamati per ciascuno stato di transizione della classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-234">The state transition table above uses punctuation symbols to describe the methods and other states that can be called for each state of the state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span> <span data-ttu-id="d8943-235">I segni usati sono gli stessi del riferimento agli standard XML per la DTD (Document Type Definition).</span><span class="sxs-lookup"><span data-stu-id="d8943-235">The symbols used are the same symbols found in the XML Standards reference for Document Type Definition (DTD).</span></span>

<span data-ttu-id="d8943-236">Nella tabella seguente vengono descritti gli effetti dei segni di punteggiatura della tabella precedente relativa alla transizione dello stato sui metodi e su altri stati che possono essere chiamati per ciascuno stato di transizione della classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-236">The following table describes how the punctuation symbols found in the state transition table above affect the methods and other states that can be called for each state in the state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span>

|<span data-ttu-id="d8943-237">Simbolo</span><span class="sxs-lookup"><span data-stu-id="d8943-237">Symbol</span></span>|<span data-ttu-id="d8943-238">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8943-238">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="d8943-239">&#124;</span><span class="sxs-lookup"><span data-stu-id="d8943-239">&#124;</span></span>|<span data-ttu-id="d8943-240">È possibile chiamare il metodo o lo stato che precede o che segue la barra.</span><span class="sxs-lookup"><span data-stu-id="d8943-240">Either method or state (the one before the bar or the one after it) can be called.</span></span>|
|<span data-ttu-id="d8943-241">?</span><span class="sxs-lookup"><span data-stu-id="d8943-241">?</span></span>|<span data-ttu-id="d8943-242">Il metodo o lo stato che precede il punto interrogativo è facoltativo. Tuttavia, se viene chiamato, può essere chiamato solo una volta.</span><span class="sxs-lookup"><span data-stu-id="d8943-242">The method or state that precedes the question mark is optional but if it is called it can only be called once.</span></span>|
|*|<span data-ttu-id="d8943-243">Il metodo o lo stato che precede il simbolo \* è facoltativo e può essere chiamato più di una volta.</span><span class="sxs-lookup"><span data-stu-id="d8943-243">The method or state that precedes the \* symbol is optional, and can be called more than once.</span></span>|

## <a name="validation-context"></a><span data-ttu-id="d8943-244">Contesto di convalida</span><span class="sxs-lookup"><span data-stu-id="d8943-244">Validation Context</span></span>

<span data-ttu-id="d8943-245">I metodi della classe <xref:System.Xml.Schema.XmlSchemaValidator> usati per convalidare elementi, attributi e contenuto in un infoset XML modificano il contesto di convalida di un oggetto <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-245">The methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class used to validate elements, attributes, and content in an XML infoset, change the validation context of an <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span> <span data-ttu-id="d8943-246">Ad esempio, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> ignora la convalida del contenuto dell'elemento corrente e prepara l'oggetto <xref:System.Xml.Schema.XmlSchemaValidator> per la convalida del contenuto nel contesto dell'elemento padre. Dal punto di vista funzionale, equivale a ignorare la convalida di tutti gli elementi figlio dell'elemento corrente e a chiamare il metodo <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8943-246">For example, the <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> method skips validation of the current element content and prepares the <xref:System.Xml.Schema.XmlSchemaValidator> object to validate content in the parent element's context; it is equivalent to skipping validation for all the children of the current element and then calling the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> method.</span></span>

<span data-ttu-id="d8943-247">I risultati dei metodi <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> e <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> della classe <xref:System.Xml.Schema.XmlSchemaValidator> dipendono dal contesto corrente da convalidare.</span><span class="sxs-lookup"><span data-stu-id="d8943-247">The results of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class are dependent on the current context being validated.</span></span>

<span data-ttu-id="d8943-248">Nella tabella seguente vengono descritti i risultati della chiamata di questi metodi dopo aver chiamato uno dei metodi della classe <xref:System.Xml.Schema.XmlSchemaValidator> usata per convalidare elementi, attributi e contenuto di un insieme di informazioni XML.</span><span class="sxs-lookup"><span data-stu-id="d8943-248">The following table describes the results of calling these methods after calling one of the methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class used to validate elements, attributes, and content in an XML infoset.</span></span>

|<span data-ttu-id="d8943-249">Metodo</span><span class="sxs-lookup"><span data-stu-id="d8943-249">Method</span></span>|<span data-ttu-id="d8943-250">GetExpectedParticles</span><span class="sxs-lookup"><span data-stu-id="d8943-250">GetExpectedParticles</span></span>|<span data-ttu-id="d8943-251">GetExpectedAttributes</span><span class="sxs-lookup"><span data-stu-id="d8943-251">GetExpectedAttributes</span></span>|<span data-ttu-id="d8943-252">AddSchema</span><span class="sxs-lookup"><span data-stu-id="d8943-252">AddSchema</span></span>|
|------------|--------------------------|---------------------------|---------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>|<span data-ttu-id="d8943-253">Se viene chiamato il metodo predefinito <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà una matrice contenente tutti gli elementi globali.</span><span class="sxs-lookup"><span data-stu-id="d8943-253">If the default <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method is called, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an array containing all global elements.</span></span><br /><br /> <span data-ttu-id="d8943-254">Se il metodo di overload <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> che accetta un tipo <xref:System.Xml.Schema.XmlSchemaObject> come parametro viene chiamato per inizializzare la convalida parziale di un elemento, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà solo l'elemento con cui viene inizializzato l'oggetto <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-254">If the overloaded <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter is called to initialize partial validation of an element, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns only the element to which the <xref:System.Xml.Schema.XmlSchemaValidator> object was initialized.</span></span>|<span data-ttu-id="d8943-255">Se viene chiamato il metodo predefinito <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà una matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="d8943-255">If the default <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method is called, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="d8943-256">Se il metodo di overload <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> che accetta un tipo <xref:System.Xml.Schema.XmlSchemaObject> come parametro viene chiamato per inizializzare la convalida parziale di un attributo, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà solo l'attributo con cui viene inizializzato l'oggetto <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-256">If the overload of the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter is called to initialize partial validation of an attribute, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns only the attribute to which the <xref:System.Xml.Schema.XmlSchemaValidator> object was initialized.</span></span>|<span data-ttu-id="d8943-257">Aggiunge lo schema al tipo <xref:System.Xml.Schema.XmlSchemaSet> dell'oggetto <xref:System.Xml.Schema.XmlSchemaValidator> se non si verificano errori di pre-elaborazione.</span><span class="sxs-lookup"><span data-stu-id="d8943-257">Adds the schema to the <xref:System.Xml.Schema.XmlSchemaSet> of the <xref:System.Xml.Schema.XmlSchemaValidator> object if it has no preprocessing errors.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|<span data-ttu-id="d8943-258">Se l'elemento di contesto è valido, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà la sequenza di elementi prevista come elementi figlio dell'elemento di contesto.</span><span class="sxs-lookup"><span data-stu-id="d8943-258">If the context element is valid, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as children of the context element.</span></span><br /><br /> <span data-ttu-id="d8943-259">Se l'elemento di contesto è non valido, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà una matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="d8943-259">If the context element is invalid, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span>|<span data-ttu-id="d8943-260">Se l'elemento di contesto è valido e se non è stata effettuata in precedenza alcuna chiamata a <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà un elenco di tutti gli attributi definiti nell'elemento di contesto.</span><span class="sxs-lookup"><span data-stu-id="d8943-260">If the context element is valid, and if no call to <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> has been previously made, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns a list of all the attributes defined on the context element.</span></span><br /><br /> <span data-ttu-id="d8943-261">Se alcuni attributi sono già stati convalidati, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà un elenco degli attributi rimanenti da convalidare.</span><span class="sxs-lookup"><span data-stu-id="d8943-261">If some attributes have already been validated, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns a list of the remaining attributes to be validated.</span></span><br /><br /> <span data-ttu-id="d8943-262">Se l'elemento di contesto è non valido, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà una matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="d8943-262">If the context element is invalid, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span>|<span data-ttu-id="d8943-263">Come sopra.</span><span class="sxs-lookup"><span data-stu-id="d8943-263">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|<span data-ttu-id="d8943-264">Se l'attributo di contesto è un attributo di primo livello, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà una matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="d8943-264">If the context attribute is a top-level attribute, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="d8943-265">In caso contrario, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà la sequenza di elementi prevista come primo elemento figlio dell'elemento di contesto.</span><span class="sxs-lookup"><span data-stu-id="d8943-265">Otherwise <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as the first child of the context element.</span></span>|<span data-ttu-id="d8943-266">Se l'attributo di contesto è un attributo di primo livello, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà una matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="d8943-266">If the context attribute is a top-level attribute, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="d8943-267">In caso contrario, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà l'elenco degli attributi rimanenti da convalidare.</span><span class="sxs-lookup"><span data-stu-id="d8943-267">Otherwise <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns the list of remaining attributes to be validated.</span></span>|<span data-ttu-id="d8943-268">Come sopra.</span><span class="sxs-lookup"><span data-stu-id="d8943-268">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>|<span data-ttu-id="d8943-269"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituisce la sequenza di elementi prevista come primo elemento figlio dell'elemento di contesto.</span><span class="sxs-lookup"><span data-stu-id="d8943-269"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as the first child of the context element.</span></span>|<span data-ttu-id="d8943-270">Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituisce un elenco degli attributi obbligatori e facoltativi che devono ancora essere convalidati per l'elemento di contesto.</span><span class="sxs-lookup"><span data-stu-id="d8943-270"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns a list of the required and optional attributes that are yet to be validated for the context element.</span></span>|<span data-ttu-id="d8943-271">Come sopra.</span><span class="sxs-lookup"><span data-stu-id="d8943-271">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|<span data-ttu-id="d8943-272"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituisce la sequenza di elementi prevista come primo elemento figlio dell'elemento di contesto.</span><span class="sxs-lookup"><span data-stu-id="d8943-272"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as the first child of the context element.</span></span>|<span data-ttu-id="d8943-273">Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituisce una matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="d8943-273"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span>|<span data-ttu-id="d8943-274">Come sopra.</span><span class="sxs-lookup"><span data-stu-id="d8943-274">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|<span data-ttu-id="d8943-275">Se contentType dell'elemento di contesto è Mixed, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà la sequenza di elementi prevista nella posizione successiva.</span><span class="sxs-lookup"><span data-stu-id="d8943-275">If the context element's contentType is Mixed, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected in the next position.</span></span><br /><br /> <span data-ttu-id="d8943-276">Se contentType dell'elemento di contesto è TextOnly o Empty, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà una matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="d8943-276">If the context element's contentType is TextOnly or Empty, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="d8943-277">Se contentType dell'elemento di contesto è ElementOnly, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà la sequenza di elementi prevista nella posizione successiva. Tuttavia, si è già verificato un errore di convalida.</span><span class="sxs-lookup"><span data-stu-id="d8943-277">If the context element's contentType is ElementOnly, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected in the next position but a validation error has already occurred.</span></span>|<span data-ttu-id="d8943-278">Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituisce un elenco degli attributi non convalidati per l'elemento di contesto.</span><span class="sxs-lookup"><span data-stu-id="d8943-278"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns the context element's list of attributes not validated.</span></span>|<span data-ttu-id="d8943-279">Come sopra.</span><span class="sxs-lookup"><span data-stu-id="d8943-279">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|<span data-ttu-id="d8943-280">Se lo spazio vuoto di contesto è uno spazio vuoto di primo livello, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà una matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="d8943-280">If the context white-space is top-level white-space, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="d8943-281">In caso contrario, il comportamento del metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> sarà lo stesso di <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8943-281">Otherwise the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method's behavior is the same as in <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span></span>|<span data-ttu-id="d8943-282">Se lo spazio vuoto di contesto è uno spazio vuoto di primo livello, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà una matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="d8943-282">If the context white-space is top-level white-space, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="d8943-283">In caso contrario, il comportamento del metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> sarà lo stesso di <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8943-283">Otherwise the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method's behavior is the same as in <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span></span>|<span data-ttu-id="d8943-284">Come sopra.</span><span class="sxs-lookup"><span data-stu-id="d8943-284">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|<span data-ttu-id="d8943-285">Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituisce la sequenza di elementi prevista dopo l'elemento di contesto, ovvero gli eventuali elementi di pari livello.</span><span class="sxs-lookup"><span data-stu-id="d8943-285"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected after the context element (possible siblings).</span></span>|<span data-ttu-id="d8943-286">Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituisce un elenco degli attributi non convalidati per l'elemento di contesto.</span><span class="sxs-lookup"><span data-stu-id="d8943-286"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns the context element's list of attributes not validated.</span></span><br /><br /> <span data-ttu-id="d8943-287">Se l'elemento di contesto non presenta un elemento padre, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà un elenco vuoto. L'elemento di contesto è l'elemento padre dell'elemento corrente in cui è stato chiamato <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8943-287">If the context element has no parent then <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty list (the context element is the parent of the current element on which <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> was called).</span></span>|<span data-ttu-id="d8943-288">Come sopra.</span><span class="sxs-lookup"><span data-stu-id="d8943-288">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|<span data-ttu-id="d8943-289">Come per <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8943-289">Same as <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span></span>|<span data-ttu-id="d8943-290">Come per <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8943-290">Same as <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span></span>|<span data-ttu-id="d8943-291">Come sopra.</span><span class="sxs-lookup"><span data-stu-id="d8943-291">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|<span data-ttu-id="d8943-292">Restituisce una matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="d8943-292">Returns an empty array.</span></span>|<span data-ttu-id="d8943-293">Restituisce una matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="d8943-293">Returns an empty array.</span></span>|<span data-ttu-id="d8943-294">Come sopra.</span><span class="sxs-lookup"><span data-stu-id="d8943-294">Same as above.</span></span>|

> [!NOTE]
> <span data-ttu-id="d8943-295">La chiamata dei metodi descritti nella tabella precedente non influisce sul valore restituito dalle diverse proprietà della classe <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="d8943-295">The values returned by the various properties of the <xref:System.Xml.Schema.XmlSchemaValidator> class are not altered by calling any of the methods in the above table.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8943-296">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8943-296">See also</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator>

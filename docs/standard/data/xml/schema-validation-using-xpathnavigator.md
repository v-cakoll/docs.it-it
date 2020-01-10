---
title: Convalida dello schema con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 81fa0e41-d9c9-46f0-b22b-50da839c77f5
ms.openlocfilehash: bfcbf7306e896af54808c49e25f95d0631f5bcc0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710206"
---
# <a name="schema-validation-using-xpathnavigator"></a><span data-ttu-id="ac043-102">Convalida dello schema con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="ac043-102">Schema Validation using XPathNavigator</span></span>
<span data-ttu-id="ac043-103">La classe <xref:System.Xml.XmlDocument> consente di convalidare il contenuto XML di un oggetto <xref:System.Xml.XmlDocument> in due modi diversi.</span><span class="sxs-lookup"><span data-stu-id="ac043-103">Using the <xref:System.Xml.XmlDocument> class, you can validate the XML content contained in an <xref:System.Xml.XmlDocument> object in two ways.</span></span> <span data-ttu-id="ac043-104">Il primo modo prevede la convalida del contenuto XML mediante un oggetto di convalida <xref:System.Xml.XmlReader>, mentre il secondo modo prevede l'uso del metodo <xref:System.Xml.XmlDocument.Validate%2A> della classe <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="ac043-104">The first way is to validate the XML content using a validating <xref:System.Xml.XmlReader> object and the second way is to use the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="ac043-105">È inoltre possibile eseguire la convalida di sola lettura del contenuto XML usando la classe <xref:System.Xml.XPath.XPathDocument>.</span><span class="sxs-lookup"><span data-stu-id="ac043-105">You can also perform read-only validation of XML content using the <xref:System.Xml.XPath.XPathDocument> class.</span></span>  
  
## <a name="validating-xml-data"></a><span data-ttu-id="ac043-106">Convalida di dati XML</span><span class="sxs-lookup"><span data-stu-id="ac043-106">Validating XML Data</span></span>  
 <span data-ttu-id="ac043-107">Per impostazione predefinita, la classe <xref:System.Xml.XmlDocument> non consente di convalidare un documento XML mediante la DTD (Document Type Definition) o lo schema XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="ac043-107">The <xref:System.Xml.XmlDocument> class does not validate an XML document using either DTD or XML schema definition language (XSD) schema validation by default.</span></span> <span data-ttu-id="ac043-108">Tale classe consente soltanto di verificare che il documento XML sia in formato corretto.</span><span class="sxs-lookup"><span data-stu-id="ac043-108">It only verifies that the XML document is well formed.</span></span>  
  
 <span data-ttu-id="ac043-109">Nel primo modo, il documento XML viene convalidato durante il caricamento in un oggetto <xref:System.Xml.XmlDocument> usando un oggetto di convalida <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="ac043-109">The first way to validate an XML document is to validate the document as it is loaded into an <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="ac043-110">Nel secondo modo, il documento XML non tipizzato in precedenza viene convalidato usando il metodo <xref:System.Xml.XmlDocument.Validate%2A> della classe <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="ac043-110">The second way is to validate a previously untyped XML document using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="ac043-111">In entrambi i casi, le modifiche apportate al documento XML convalidato possono essere convalidate di nuovo usando il metodo <xref:System.Xml.XmlDocument.Validate%2A> della classe <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="ac043-111">In both cases, changes to the validated XML document can be revalidated using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span>  
  
### <a name="validating-a-document-as-it-is-loaded"></a><span data-ttu-id="ac043-112">Convalida di un documento durante il caricamento</span><span class="sxs-lookup"><span data-stu-id="ac043-112">Validating a Document as it is Loaded</span></span>  
 <span data-ttu-id="ac043-113">Un oggetto di convalida <xref:System.Xml.XmlReader> viene creato passando un oggetto <xref:System.Xml.XmlReaderSettings> al metodo <xref:System.Xml.XmlReader.Create%2A> della classe <xref:System.Xml.XmlReader> che accetta un oggetto <xref:System.Xml.XmlReaderSettings> come parametro.</span><span class="sxs-lookup"><span data-stu-id="ac043-113">A validating <xref:System.Xml.XmlReader> object is created by passing an <xref:System.Xml.XmlReaderSettings> object to the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class that takes an <xref:System.Xml.XmlReaderSettings> object as a parameter.</span></span> <span data-ttu-id="ac043-114">Nell'oggetto <xref:System.Xml.XmlReaderSettings> passato come parametro è presente una proprietà <xref:System.Xml.XmlReaderSettings.ValidationType%2A> impostata su `Schema` e un XML Schema per il documento XML contenuto nell'oggetto <xref:System.Xml.XmlDocument> aggiunto alla relativa proprietà <xref:System.Xml.XmlReaderSettings.Schemas%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac043-114">The <xref:System.Xml.XmlReaderSettings> object passed as a parameter has a <xref:System.Xml.XmlReaderSettings.ValidationType%2A> property set to `Schema` and an XML Schema for the XML document contained in the <xref:System.Xml.XmlDocument> object added to its <xref:System.Xml.XmlReaderSettings.Schemas%2A> property.</span></span> <span data-ttu-id="ac043-115">L'oggetto di convalida <xref:System.Xml.XmlReader> viene quindi usato per creare l'oggetto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="ac043-115">The validating <xref:System.Xml.XmlReader> object is then used to create the <xref:System.Xml.XmlDocument> object.</span></span>  
  
 <span data-ttu-id="ac043-116">Nell'esempio seguente viene convalidato il `contosoBooks.xml` file durante il caricamento nel <xref:System.Xml.XmlDocument> creando il <xref:System.Xml.XmlDocument> utilizzando un oggetto di convalida dell'oggetto <xref:System.Xml.XmlReader> oggetto.</span><span class="sxs-lookup"><span data-stu-id="ac043-116">The following example validates the `contosoBooks.xml` file as it is loaded into the <xref:System.Xml.XmlDocument> object by creating the <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="ac043-117">Dal momento che il documento XML è valido in base al relativo schema, non verrà generato alcun errore o avviso di convalida dello schema.</span><span class="sxs-lookup"><span data-stu-id="ac043-117">Because the XML document is valid according to its schema, no schema validation errors or warnings are generated.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Schema  
Imports System.Xml.XPath  
  
Class ValidatingReaderExample  
  
    Shared Sub Main(ByVal args() As String)  
  
        Try  
            Dim settings As XmlReaderSettings = New XmlReaderSettings()  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
            settings.ValidationType = ValidationType.Schema  
  
            Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
            Dim document As XmlDocument = New XmlDocument()  
            document.Load(reader)  
            Dim navigator As XPathNavigator = document.CreateNavigator()  
  
        Catch e As Exception  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message)  
        End Try  
  
    End Sub  
  
    Shared Sub SchemaValidationHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
        Select Case e.Severity  
            Case XmlSeverityType.Error  
                Console.WriteLine("Schema Validation Error: {0}", e.Message)  
                Exit Sub  
            Case XmlSeverityType.Warning  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message)  
                Exit Sub  
        End Select  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Schema;  
using System.Xml.XPath;  
  
class ValidatingReaderExample  
{  
    static void Main(string[] args)  
    {  
        try  
        {  
            XmlReaderSettings settings = new XmlReaderSettings();  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
            settings.ValidationType = ValidationType.Schema;  
  
            XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
            XmlDocument document = new XmlDocument();  
            document.Load(reader);  
            XPathNavigator navigator = document.CreateNavigator();  
        }  
        catch (Exception e)  
        {  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message);  
        }  
    }  
  
    static void SchemaValidationHandler(object sender, ValidationEventArgs e)  
    {  
        switch (e.Severity)  
        {  
            case XmlSeverityType.Error:  
                Console.WriteLine("Schema Validation Error: {0}", e.Message);  
                break;  
            case XmlSeverityType.Warning:  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message);  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="ac043-118">Nell'esempio il file `contosoBooks.xml` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="ac043-118">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="ac043-119">Anche il file `contosoBooks.xsd` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="ac043-119">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
 <span data-ttu-id="ac043-120">Nell'esempio precedente verrà generata un'eccezione <xref:System.Xml.Schema.XmlSchemaValidationException> quando si chiama <xref:System.Xml.XmlDocument.Load%2A> se il tipo di qualsiasi attributo o elemento non corrisponde al tipo specificato nello schema di convalida.</span><span class="sxs-lookup"><span data-stu-id="ac043-120">In the above example, an <xref:System.Xml.Schema.XmlSchemaValidationException> will be thrown when <xref:System.Xml.XmlDocument.Load%2A> is called if any attribute or element type does not match the corresponding type specified in the validating schema.</span></span> <span data-ttu-id="ac043-121">Se <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> è impostato sull'oggetto <xref:System.Xml.XmlReader> di convalida, verrà chiamato <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> ogni volta in cui viene individuato un tipo non valido.</span><span class="sxs-lookup"><span data-stu-id="ac043-121">If a <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> is set on the validating <xref:System.Xml.XmlReader>, the <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> will get called whenever an invalid type is encountered.</span></span>  
  
 <span data-ttu-id="ac043-122">Verrà generata un'eccezione <xref:System.Xml.Schema.XmlSchemaException> quando <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> accede a un attributo o un elemento la cui proprietà `invalid` è impostata su <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="ac043-122">An <xref:System.Xml.Schema.XmlSchemaException> will be thrown when an attribute or element with <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> set to `invalid` is accessed by the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="ac043-123">È possibile usare la proprietà <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> per determinare se un singolo attributo o elemento è valido quando si accede ad attributi o elementi tramite <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="ac043-123">The <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> property can be used to determine whether or not an individual attribute or element is valid when accessing attributes or elements with the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ac043-124">Quando un documento XML viene caricato in un oggetto <xref:System.Xml.XmlDocument> a cui è associato uno schema che definisce dei valori predefiniti, questi vengono considerati dall'oggetto <xref:System.Xml.XmlDocument> come se fossero contenuti nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="ac043-124">When an XML document is loaded into an <xref:System.Xml.XmlDocument> object with an associated schema that defines default values, the <xref:System.Xml.XmlDocument> object treats these defaults as if they appeared in the XML document.</span></span> <span data-ttu-id="ac043-125">Ciò significa che la proprietà <xref:System.Xml.XPath.XPathNavigator.IsEmptyElement%2A> restituisce sempre `false` per un elemento che è stato modificato dallo schema, anche se nel documento XML era stato scritto come elemento vuoto.</span><span class="sxs-lookup"><span data-stu-id="ac043-125">This means that the <xref:System.Xml.XPath.XPathNavigator.IsEmptyElement%2A> property  always returns `false` for an element that was defaulted from the schema, even if in the XML document it was written as an empty element.</span></span>  
  
### <a name="validating-a-document-using-the-validate-method"></a><span data-ttu-id="ac043-126">Convalida di un documento con il metodo Validate</span><span class="sxs-lookup"><span data-stu-id="ac043-126">Validating a Document using the Validate Method</span></span>  
 <span data-ttu-id="ac043-127">Il metodo <xref:System.Xml.XmlDocument.Validate%2A> della classe <xref:System.Xml.XmlDocument> consente di convalidare il documento XML contenuto in un oggetto <xref:System.Xml.XmlDocument> in base agli schemi specificati nella proprietà <xref:System.Xml.XmlDocument> dell'oggetto <xref:System.Xml.XmlDocument.Schemas%2A> e di aumentare l'infoset.</span><span class="sxs-lookup"><span data-stu-id="ac043-127">The <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class validates the XML document contained in an <xref:System.Xml.XmlDocument> object against the schemas specified in the <xref:System.Xml.XmlDocument> object's <xref:System.Xml.XmlDocument.Schemas%2A> property and performs infoset augmentation.</span></span> <span data-ttu-id="ac043-128">Il risultato è la sostituzione di un documento XML non tipizzato in precedenza nell'oggetto <xref:System.Xml.XmlDocument> con un documento tipizzato.</span><span class="sxs-lookup"><span data-stu-id="ac043-128">The result is a previously untyped XML document in the <xref:System.Xml.XmlDocument> object replaced with a typed document.</span></span>  
  
 <span data-ttu-id="ac043-129">Per segnalare gli errori e gli avvisi di convalida dello schema, nell'oggetto <xref:System.Xml.XmlDocument> viene usato il delegato <xref:System.Xml.Schema.ValidationEventHandler> passato come parametro al metodo <xref:System.Xml.XmlDocument.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac043-129">The <xref:System.Xml.XmlDocument> object reports schema validation errors and warnings using the <xref:System.Xml.Schema.ValidationEventHandler> delegate passed as a parameter to the <xref:System.Xml.XmlDocument.Validate%2A> method.</span></span>  
  
 <span data-ttu-id="ac043-130">Nell'esempio seguente viene convalidato il file `contosoBooks.xml` contenuto nell'oggetto <xref:System.Xml.XmlDocument> in base allo schema `contosoBooks.xsd` contenuto nella proprietà <xref:System.Xml.XmlDocument> dell'oggetto <xref:System.Xml.XmlDocument.Schemas%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac043-130">The following example validates the `contosoBooks.xml` file contained in the <xref:System.Xml.XmlDocument> object against the `contosoBooks.xsd` schema contained in the <xref:System.Xml.XmlDocument> object's <xref:System.Xml.XmlDocument.Schemas%2A> property.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Schema  
Imports System.Xml.XPath  
  
Class ValidateExample  
  
    Shared Sub Main(ByVal args() As String)  
  
        Dim document As XmlDocument = New XmlDocument()  
        document.Load("contosoBooks.xml")  
        Dim navigator As XPathNavigator = document.CreateNavigator()  
  
        document.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
        Dim validation As ValidationEventHandler = New ValidationEventHandler(AddressOf SchemaValidationHandler)  
  
        document.Validate(validation)  
  
    End Sub  
  
    Shared Sub SchemaValidationHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
        Select Case e.Severity  
            Case XmlSeverityType.Error  
                Console.WriteLine("Schema Validation Error: {0}", e.Message)  
                Exit Sub  
            Case XmlSeverityType.Warning  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message)  
                Exit Sub  
        End Select  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Schema;  
using System.Xml.XPath;  
  
class ValidateExample  
{  
    static void Main(string[] args)  
    {  
        XmlDocument document = new XmlDocument();  
        document.Load("contosoBooks.xml");  
        XPathNavigator navigator = document.CreateNavigator();  
  
        document.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
        ValidationEventHandler validation = new ValidationEventHandler(SchemaValidationHandler);  
  
        document.Validate(validation);  
    }  
  
    static void SchemaValidationHandler(object sender, ValidationEventArgs e)  
    {  
        switch (e.Severity)  
        {  
            case XmlSeverityType.Error:  
                Console.WriteLine("Schema Validation Error: {0}", e.Message);  
                break;  
            case XmlSeverityType.Warning:  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message);  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="ac043-131">Nell'esempio il file `contosoBooks.xml` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="ac043-131">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="ac043-132">Anche il file `contosoBooks.xsd` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="ac043-132">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
### <a name="validating-modifications"></a><span data-ttu-id="ac043-133">Convalida delle modifiche</span><span class="sxs-lookup"><span data-stu-id="ac043-133">Validating Modifications</span></span>  
 <span data-ttu-id="ac043-134">Dopo aver apportato delle modifiche a un documento XML, è possibile convalidare le modifiche in base allo schema per il documento XML usando il metodo <xref:System.Xml.XmlDocument.Validate%2A> della classe <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="ac043-134">After modifications are made to an XML document, you can validate the modifications against the schema for the XML document using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="ac043-135">Nell'esempio seguente viene convalidato il `contosoBooks.xml` file durante il caricamento nel <xref:System.Xml.XmlDocument> creando il <xref:System.Xml.XmlDocument> utilizzando un oggetto di convalida dell'oggetto <xref:System.Xml.XmlReader> oggetto.</span><span class="sxs-lookup"><span data-stu-id="ac043-135">The following example validates the `contosoBooks.xml` file as it is loaded into the <xref:System.Xml.XmlDocument> object by creating the <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="ac043-136">Il documento XML viene convalidato correttamente durante il caricamento e non viene generato alcun errore o avviso di convalida dello schema.</span><span class="sxs-lookup"><span data-stu-id="ac043-136">The XML document is validated successfully as it is loaded without generating any schema validation errors or warnings.</span></span> <span data-ttu-id="ac043-137">Nell'esempio vengono quindi apportate due modifiche al documento XML che risultano non valide in base allo schema `contosoBooks.xsd`.</span><span class="sxs-lookup"><span data-stu-id="ac043-137">The example then makes two modifications to the XML document that are invalid according to the `contosoBooks.xsd` schema.</span></span> <span data-ttu-id="ac043-138">Nella prima modifica viene inserito un elemento figlio non valido che genera un errore di convalida dello schema. Nella seconda modifica, invece, il valore di un nodo tipizzato viene impostato su un valore non valido in base al tipo del nodo e viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ac043-138">The first modification inserts an invalid child element resulting in a schema validation error, and the second modification sets the value of a typed node to a value that is invalid according to the type of the node resulting in an exception.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Schema  
Imports System.Xml.XPath  
  
Class ValidatingReaderExample  
  
    Shared Sub Main(ByVal args() As String)  
  
        Try  
            Dim settings As XmlReaderSettings = New XmlReaderSettings()  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
            settings.ValidationType = ValidationType.Schema  
  
            Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
            Dim document As XmlDocument = New XmlDocument()  
            document.Load(reader)  
            Dim navigator As XPathNavigator = document.CreateNavigator()  
  
            Dim validation As ValidationEventHandler = New ValidationEventHandler(AddressOf SchemaValidationHandler)  
  
            navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
            navigator.MoveToChild("book", "http://www.contoso.com/books")  
            navigator.MoveToChild("author", "http://www.contoso.com/books")  
  
            navigator.AppendChild("<title>Book Title</title>")  
  
            document.Validate(validation)  
  
            navigator.MoveToParent()  
            navigator.MoveToChild("price", "http://www.contoso.com/books")  
            navigator.SetTypedValue(DateTime.Now)  
        Catch e As Exception  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message)  
        End Try  
  
    End Sub  
  
    Shared Sub SchemaValidationHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
        Select Case e.Severity  
            Case XmlSeverityType.Error  
                Console.WriteLine("Schema Validation Error: {0}", e.Message)  
                Exit Sub  
            Case XmlSeverityType.Warning  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message)  
                Exit Sub  
        End Select  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Schema;  
using System.Xml.XPath;  
  
class ValidatingReaderExample  
{  
    static void Main(string[] args)  
    {  
        try  
        {  
            XmlReaderSettings settings = new XmlReaderSettings();  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
            settings.ValidationType = ValidationType.Schema;  
  
            XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
            XmlDocument document = new XmlDocument();  
            document.Load(reader);  
            XPathNavigator navigator = document.CreateNavigator();  
  
            ValidationEventHandler validation = new ValidationEventHandler(SchemaValidationHandler);  
  
            navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
            navigator.MoveToChild("book", "http://www.contoso.com/books");  
            navigator.MoveToChild("author", "http://www.contoso.com/books");  
  
            navigator.AppendChild("<title>Book Title</title>");  
  
            document.Validate(validation);  
  
            navigator.MoveToParent();  
            navigator.MoveToChild("price", "http://www.contoso.com/books");  
            navigator.SetTypedValue(DateTime.Now);  
        }  
        catch (Exception e)  
        {  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message);  
        }  
    }  
  
    static void SchemaValidationHandler(object sender, ValidationEventArgs e)  
    {  
        switch (e.Severity)  
        {  
            case XmlSeverityType.Error:  
                Console.WriteLine("Schema Validation Error: {0}", e.Message);  
                break;  
            case XmlSeverityType.Warning:  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message);  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="ac043-139">Nell'esempio il file `contosoBooks.xml` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="ac043-139">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="ac043-140">Anche il file `contosoBooks.xsd` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="ac043-140">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
 <span data-ttu-id="ac043-141">Nell'esempio precedente, vengono apportate due modifiche al documento XML contenuto nell'oggetto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="ac043-141">In the example above, two modifications are made to the XML document contained in the <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="ac043-142">Durante il caricamento del documento XML, se fossero stati rilevati errori di convalida dello schema, sarebbero stati gestiti dal gestore eventi di convalida e darebbero stati scritti nella console.</span><span class="sxs-lookup"><span data-stu-id="ac043-142">As the XML document was loaded, any schema validation errors encountered would have been handled by the validation event handler method and written to the console.</span></span>  
  
 <span data-ttu-id="ac043-143">In questo esempio, gli errori di convalida sono stati introdotti dopo il caricamento del documento XML e sono stati rilevati usando il metodo <xref:System.Xml.XmlDocument.Validate%2A> della classe <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="ac043-143">In this example, the validation errors were introduced after the XML document was loaded and were found using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="ac043-144">Le modifiche effettuate usando il metodo <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> della classe <xref:System.Xml.XPath.XPathNavigator> hanno restituito un tipo <xref:System.InvalidCastException> poiché il nuovo valore non era valido in base al tipo di schema del nodo.</span><span class="sxs-lookup"><span data-stu-id="ac043-144">Modifications made using the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class resulted in an <xref:System.InvalidCastException> because the new value was invalid according to the schema type of the node.</span></span>  
  
 <span data-ttu-id="ac043-145">Per altre informazioni sulla modifica dei valori mediante il metodo <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>, vedere l'argomento [Modifica dei dati XML con XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="ac043-145">For more information about modifying values using the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method, see the [Modify XML Data using XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md) topic.</span></span>  
  
### <a name="read-only-validation"></a><span data-ttu-id="ac043-146">Convalida di sola lettura</span><span class="sxs-lookup"><span data-stu-id="ac043-146">Read-Only Validation</span></span>  
 <span data-ttu-id="ac043-147">La classe <xref:System.Xml.XPath.XPathDocument> è una rappresentazione in memoria e di sola lettura di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="ac043-147">The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory representation of an XML document.</span></span> <span data-ttu-id="ac043-148">Le classi <xref:System.Xml.XPath.XPathDocument> e <xref:System.Xml.XmlDocument> consentono di creare oggetti <xref:System.Xml.XPath.XPathNavigator> per esplorare e modificare i documenti XML.</span><span class="sxs-lookup"><span data-stu-id="ac043-148">Both the <xref:System.Xml.XPath.XPathDocument> class and the <xref:System.Xml.XmlDocument> class create <xref:System.Xml.XPath.XPathNavigator> objects to navigate and edit XML documents.</span></span> <span data-ttu-id="ac043-149">Dal momento che la classe <xref:System.Xml.XPath.XPathDocument> è di sola lettura, gli oggetti <xref:System.Xml.XPath.XPathNavigator> restituiti dagli oggetti <xref:System.Xml.XPath.XPathDocument> non sono in grado di modificare il documento XML contenuto nell'oggetto <xref:System.Xml.XPath.XPathDocument>.</span><span class="sxs-lookup"><span data-stu-id="ac043-149">Because the <xref:System.Xml.XPath.XPathDocument> class is a read-only class, <xref:System.Xml.XPath.XPathNavigator> object's returned from <xref:System.Xml.XPath.XPathDocument> objects cannot edit the XML document contained in the <xref:System.Xml.XPath.XPathDocument> object.</span></span>  
  
 <span data-ttu-id="ac043-150">In caso di convalida, è possibile creare un oggetto <xref:System.Xml.XPath.XPathDocument> nello stesso modo in cui si crea un oggetto <xref:System.Xml.XmlDocument> usando un oggetto di convalida <xref:System.Xml.XmlReader> come descritto in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ac043-150">In the case of validation, you can create an <xref:System.Xml.XPath.XPathDocument> object just like you create an <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object as described earlier in this topic.</span></span> <span data-ttu-id="ac043-151">L'oggetto <xref:System.Xml.XPath.XPathDocument> consente di convalidare il documento XML durante il caricamento; tuttavia, dal momento che non è possibile modificare i dati XML nell'oggetto <xref:System.Xml.XPath.XPathDocument>, non sarà possibile eseguire di nuovo la convalida del documento XML.</span><span class="sxs-lookup"><span data-stu-id="ac043-151">The <xref:System.Xml.XPath.XPathDocument> object validates the XML document as it is loaded, but because you cannot edit the XML data in the <xref:System.Xml.XPath.XPathDocument> object, you cannot revalidate the XML document.</span></span>  
  
 <span data-ttu-id="ac043-152">Per altre informazioni sulla creazioni di oggetti <xref:System.Xml.XPath.XPathNavigator> modificabili e in sola lettura, vedere l'argomento [Lettura di dati XML con XPathDocument e XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).</span><span class="sxs-lookup"><span data-stu-id="ac043-152">For more information about read-only and editable <xref:System.Xml.XPath.XPathNavigator> objects, see the [Reading XML Data using XPathDocument and XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac043-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac043-153">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="ac043-154">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="ac043-154">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="ac043-155">Lettura di dati XML con XPathDocument e XmlDocument</span><span class="sxs-lookup"><span data-stu-id="ac043-155">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)
- [<span data-ttu-id="ac043-156">Selezione, valutazione e corrispondenza di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="ac043-156">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="ac043-157">Accesso ai dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="ac043-157">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="ac043-158">Modifica di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="ac043-158">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)

---
title: Controllo della serializzazione XML mediante attributi
description: Gli attributi possono essere utilizzati per controllare la serializzazione XML di un oggetto o per creare un flusso XML alternativo dallo stesso set di classi.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, serializing
- XML serialization, examples
- derived classes, serializing
- arrays, serializing
- XML serialization, attributes
- preventing serialization
- attributes [.NET Framework], XML serialization
- serialization, examples
- serialization, attributes
ms.assetid: 47d4c39d-30e1-4c7b-8a2e-301325390647
ms.openlocfilehash: 79c5541b4c384e91fbec8c8f1b2130887e79a252
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289681"
---
# <a name="controlling-xml-serialization-using-attributes"></a><span data-ttu-id="d7d50-103">Controllo della serializzazione XML mediante attributi</span><span class="sxs-lookup"><span data-stu-id="d7d50-103">Controlling XML Serialization Using Attributes</span></span>

<span data-ttu-id="d7d50-104">Gli attributi possono essere utilizzati per controllare la serializzazione XML di un oggetto o per creare un flusso XML alternativo dallo stesso set di classi.</span><span class="sxs-lookup"><span data-stu-id="d7d50-104">Attributes can be used to control the XML serialization of an object or to create an alternate XML stream from the same set of classes.</span></span> <span data-ttu-id="d7d50-105">Per altri dettagli sulla creazione di un flusso XML alternativo, vedere [Procedura: Specificare un nome di elemento alternativo per un flusso XML](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).</span><span class="sxs-lookup"><span data-stu-id="d7d50-105">For more details about creating an alternate XML stream, see [How to: Specify an Alternate Element Name for an XML Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d7d50-106">Se il codice XML generato deve essere conforme alla sezione 5 del documento World Wide Web Consortium (W3C) denominato [Simple Object Access Protocol (SOAP) 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/), utilizzare gli attributi elencati negli [attributi che controllano la serializzazione SOAP codificata](attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="d7d50-106">If the XML generated must conform to section 5 of the World Wide Web Consortium (W3C) document titled [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/), use the attributes listed in [Attributes That Control Encoded SOAP Serialization](attributes-that-control-encoded-soap-serialization.md).</span></span>

<span data-ttu-id="d7d50-107">Per impostazione predefinita, un nome di elemento XML è determinato dal nome della classe o del membro.</span><span class="sxs-lookup"><span data-stu-id="d7d50-107">By default, an XML element name is determined by the class or member name.</span></span> <span data-ttu-id="d7d50-108">In una classe semplice denominata `Book` , un campo denominato `ISBN` produrrà un tag di elemento XML \<ISBN> , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d7d50-108">In a simple class named `Book`, a field named `ISBN` will produce an XML element tag \<ISBN>, as shown in the following example.</span></span>

```vb
Public Class Book
    Public ISBN As String
End Class
' When an instance of the Book class is serialized, it might
' produce this XML:
' <ISBN>1234567890</ISBN>.
```

```csharp
public class Book
{
    public string ISBN;
}
// When an instance of the Book class is serialized, it might
// produce this XML:
// <ISBN>1234567890</ISBN>.
```

<span data-ttu-id="d7d50-109">Questo comportamento predefinito può essere modificato se si vuole assegnare un nuovo nome all'elemento.</span><span class="sxs-lookup"><span data-stu-id="d7d50-109">This default behavior can be changed if you want to give the element a new name.</span></span> <span data-ttu-id="d7d50-110">Il codice riportato di seguito mostra il modo in cui un attributo svolge tale funzione impostando la proprietà <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> di una classe <xref:System.Xml.Serialization.XmlElementAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d7d50-110">The following code shows how an attribute enables this by setting the <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> property of a <xref:System.Xml.Serialization.XmlElementAttribute>.</span></span>

```vb
Public Class TaxRates
   < XmlElement(ElementName = "TaxRate")> _
    Public ReturnTaxRate As Decimal
End Class
```

```csharp
public class TaxRates {
    [XmlElement(ElementName = "TaxRate")]
    public decimal ReturnTaxRate;
}
```

<span data-ttu-id="d7d50-111">Per altre informazioni sugli attributi, vedere [Attributi](../attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="d7d50-111">For more information about attributes, see [Attributes](../attributes/index.md).</span></span> <span data-ttu-id="d7d50-112">Per l'elenco degli attributi che controllano la serializzazione XML, vedere [Attributi per il controllo della serializzazione XML](attributes-that-control-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="d7d50-112">For a list of attributes that control XML serialization, see [Attributes That Control XML Serialization](attributes-that-control-xml-serialization.md).</span></span>

## <a name="controlling-array-serialization"></a><span data-ttu-id="d7d50-113">Controllo della serializzazione di matrice</span><span class="sxs-lookup"><span data-stu-id="d7d50-113">Controlling Array Serialization</span></span>

<span data-ttu-id="d7d50-114">Gli attributi <xref:System.Xml.Serialization.XmlArrayAttribute> e <xref:System.Xml.Serialization.XmlArrayItemAttribute> sono progettati per controllare la serializzazione delle matrici.</span><span class="sxs-lookup"><span data-stu-id="d7d50-114">The <xref:System.Xml.Serialization.XmlArrayAttribute> and the <xref:System.Xml.Serialization.XmlArrayItemAttribute> attributes are designed to control the serialization of arrays.</span></span> <span data-ttu-id="d7d50-115">Tramite l'utilizzo di questi attributi, è possibile controllare il nome dell'elemento, lo spazio dei nomi e tipo di dati XML Schema (XSD) (come definito nel documento intitolato "XML Schema Part 2: Datatypes" del World Wide Web Consortium [www.w3.org]).</span><span class="sxs-lookup"><span data-stu-id="d7d50-115">Using these attributes, you can control the element name, namespace, and XML Schema (XSD) data type (as defined in the World Wide Web Consortium [www.w3.org] document titled "XML Schema Part 2: Datatypes").</span></span> <span data-ttu-id="d7d50-116">È inoltre possibile specificare i tipi che possono essere inclusi in una matrice.</span><span class="sxs-lookup"><span data-stu-id="d7d50-116">You can also specify the types that can be included in an array.</span></span>

<span data-ttu-id="d7d50-117"><xref:System.Xml.Serialization.XmlArrayAttribute> determinerà le proprietà dell'elemento XML di inclusione risultante dalla serializzazione di una matrice.</span><span class="sxs-lookup"><span data-stu-id="d7d50-117">The <xref:System.Xml.Serialization.XmlArrayAttribute> will determine the properties of the enclosing XML element that results when an array is serialized.</span></span> <span data-ttu-id="d7d50-118">Ad esempio, la serializzazione della matrice riportata di seguito, per impostazione predefinita comporterà la creazione di un elemento XML denominato `Employees`.</span><span class="sxs-lookup"><span data-stu-id="d7d50-118">For example, by default, serializing the array below will result in an XML element named `Employees`.</span></span> <span data-ttu-id="d7d50-119">L'elemento `Employees` conterrà una serie di elementi denominati dopo il tipo di matrice `Employee`.</span><span class="sxs-lookup"><span data-stu-id="d7d50-119">The `Employees` element will contain a series of elements named after the array type `Employee`.</span></span>

```vb
Public Class Group
    Public Employees() As Employee
End Class
Public Class Employee
    Public Name As String
End Class
```

```csharp
public class Group {
    public Employee[] Employees;
}
public class Employee {
    public string Name;
}
```

<span data-ttu-id="d7d50-120">Un'istanza serializzata potrebbe assomigliare agli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d7d50-120">A serialized instance might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</Employees>
</Group>
```

<span data-ttu-id="d7d50-121">Tramite l'applicazione di un attributo <xref:System.Xml.Serialization.XmlArrayAttribute>, è possibile modificare il nome dell'elemento XML, come segue.</span><span class="sxs-lookup"><span data-stu-id="d7d50-121">By applying a <xref:System.Xml.Serialization.XmlArrayAttribute>, you can change the name of the XML element, as follows.</span></span>

```vb
Public Class Group
    <XmlArray("TeamMembers")> _
    Public Employees() As Employee
End Class
```

```csharp
public class Group {
    [XmlArray("TeamMembers")]
    public Employee[] Employees;
}
```

<span data-ttu-id="d7d50-122">L'XML risultante potrebbe assomigliare agli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d7d50-122">The resulting XML might resemble the following.</span></span>

```xml
<Group>
<TeamMembers>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</TeamMembers>
</Group>
```

<span data-ttu-id="d7d50-123"><xref:System.Xml.Serialization.XmlArrayItemAttribute>, d'altra parte, controlla il modo in cui vengono serializzati gli elementi contenuti nella matrice.</span><span class="sxs-lookup"><span data-stu-id="d7d50-123">The <xref:System.Xml.Serialization.XmlArrayItemAttribute>, on the other hand, controls how the items contained in the array are serialized.</span></span> <span data-ttu-id="d7d50-124">Notare che l'attributo viene applicato al campo che restituisce la matrice.</span><span class="sxs-lookup"><span data-stu-id="d7d50-124">Note that the attribute is applied to the field returning the array.</span></span>

```vb
Public Class Group
    <XmlArrayItem("MemberName")> _
    Public Employee() As Employees
End Class
```

```csharp
public class Group {
    [XmlArrayItem("MemberName")]
    public Employee[] Employees;
}
```

<span data-ttu-id="d7d50-125">L'XML risultante potrebbe assomigliare agli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d7d50-125">The resulting XML might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <MemberName>Haley</MemberName>
</Employees>
</Group>
```

## <a name="serializing-derived-classes"></a><span data-ttu-id="d7d50-126">Serializzazione delle classi derivate</span><span class="sxs-lookup"><span data-stu-id="d7d50-126">Serializing Derived Classes</span></span>

<span data-ttu-id="d7d50-127">Un altro utilizzo di <xref:System.Xml.Serialization.XmlArrayItemAttribute> è quello di consentire la serializzazione di classi derivate.</span><span class="sxs-lookup"><span data-stu-id="d7d50-127">Another use of the <xref:System.Xml.Serialization.XmlArrayItemAttribute> is to allow the serialization of derived classes.</span></span> <span data-ttu-id="d7d50-128">Ad esempio, al precedente esempio è possibile aggiungere un'altra classe denominata `Manager` che deriva da `Employee`.</span><span class="sxs-lookup"><span data-stu-id="d7d50-128">For example, another class named `Manager` that derives from `Employee` can be added to the previous example.</span></span> <span data-ttu-id="d7d50-129">Se non si applica <xref:System.Xml.Serialization.XmlArrayItemAttribute>, il codice provocherà un errore in fase di esecuzione perché il tipo di classe derivata non verrà riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d7d50-129">If you do not apply the <xref:System.Xml.Serialization.XmlArrayItemAttribute>, the code will fail at run time because the derived class type will not be recognized.</span></span> <span data-ttu-id="d7d50-130">Per risolvere questo problema, applicare due volte l'attributo, impostando ogni volta la proprietà <xref:System.Xml.Serialization.XmlArrayItemAttribute.Type%2A> per ogni tipo accettabile (base e derivato).</span><span class="sxs-lookup"><span data-stu-id="d7d50-130">To remedy this, apply the attribute twice, each time setting the <xref:System.Xml.Serialization.XmlArrayItemAttribute.Type%2A> property for each acceptable type (base and derived).</span></span>

```vb
Public Class Group
    <XmlArrayItem(Type:=GetType(Employee)), _
    XmlArrayItem(Type:=GetType(Manager))> _
    Public Employees() As Employee
End Class
Public Class Employee
    Public Name As String
End Class
Public Class Manager
Inherits Employee
    Public Level As Integer
End Class
```

```csharp
public class Group {
    [XmlArrayItem(Type = typeof(Employee)),
    XmlArrayItem(Type = typeof(Manager))]
    public Employee[] Employees;
}
public class Employee {
    public string Name;
}
public class Manager:Employee {
    public int Level;
}
```

<span data-ttu-id="d7d50-131">Un'istanza serializzata potrebbe assomigliare agli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d7d50-131">A serialized instance might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <Employee>
        <Name>Haley</Name>
    </Employee>
    <Employee xsi:type = "Manager">
        <Name>Ann</Name>
        <Level>3</Level>
    </Employee>
</Employees>
</Group>
```

## <a name="serializing-an-array-as-a-sequence-of-elements"></a><span data-ttu-id="d7d50-132">Serializzazione di una matrice come sequenza di elementi</span><span class="sxs-lookup"><span data-stu-id="d7d50-132">Serializing an Array as a Sequence of Elements</span></span>

<span data-ttu-id="d7d50-133">È possibile anche serializzare una matrice come un'unica sequenza di elementi XML applicando un attributo <xref:System.Xml.Serialization.XmlElementAttribute> al campo che restituisce la matrice nel modo riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d7d50-133">You can also serialize an array as a flat sequence of XML elements by applying a <xref:System.Xml.Serialization.XmlElementAttribute> to the field returning the array as follows.</span></span>

```vb
Public Class Group
    <XmlElement> _
    Public Employees() As Employee
End Class
```

```csharp
public class Group {
    [XmlElement]
    public Employee[] Employees;
}
```

<span data-ttu-id="d7d50-134">Un'istanza serializzata potrebbe assomigliare agli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d7d50-134">A serialized instance might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <Name>Haley</Name>
</Employees>
<Employees>
    <Name>Noriko</Name>
</Employees>
<Employees>
    <Name>Marco</Name>
</Employees>
</Group>
```

<span data-ttu-id="d7d50-135">Un altro modo per differenziare i due flussi XML è quello di utilizzare lo strumento XML Schema Definition per generare i file del documento XML Schema (XSD) dal codice compilato.</span><span class="sxs-lookup"><span data-stu-id="d7d50-135">Another way to differentiate the two XML streams is to use the XML Schema Definition tool to generate the XML Schema (XSD) document files from the compiled code.</span></span> <span data-ttu-id="d7d50-136">Per ulteriori informazioni sull'utilizzo dello strumento, vedere [lo strumento XML Schema Definition e la serializzazione XML](the-xml-schema-definition-tool-and-xml-serialization.md). Quando al campo non viene applicato alcun attributo, lo schema descrive l'elemento nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="d7d50-136">(For more details on using the tool, see [The XML Schema Definition Tool and XML Serialization](the-xml-schema-definition-tool-and-xml-serialization.md).) When no attribute is applied to the field, the schema describes the element in the following manner.</span></span>

```xml
<xs:element minOccurs="0" maxOccurs ="1" name="Employees" type="ArrayOfEmployee" />
```

<span data-ttu-id="d7d50-137">Se al campo è applicato l'attributo <xref:System.Xml.Serialization.XmlElementAttribute>, lo schema risultante descrive l'elemento nel modo riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d7d50-137">When the <xref:System.Xml.Serialization.XmlElementAttribute> is applied to the field, the resulting schema describes the element as follows.</span></span>

```xml
<xs:element minOccurs="0" maxOccurs="unbounded" name="Employees" type="Employee" />
```

## <a name="serializing-an-arraylist"></a><span data-ttu-id="d7d50-138">Serializzazione di un ArrayList</span><span class="sxs-lookup"><span data-stu-id="d7d50-138">Serializing an ArrayList</span></span>

<span data-ttu-id="d7d50-139">La classe <xref:System.Collections.ArrayList> contiene una raccolta di oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="d7d50-139">The <xref:System.Collections.ArrayList> class can contain a collection of diverse objects.</span></span> <span data-ttu-id="d7d50-140">È quindi possibile utilizzare una classe <xref:System.Collections.ArrayList> allo stesso modo con cui si utilizza una matrice.</span><span class="sxs-lookup"><span data-stu-id="d7d50-140">You can therefore use a <xref:System.Collections.ArrayList> much as you use an array.</span></span> <span data-ttu-id="d7d50-141">Anziché creare un campo che restituisca una matrice di oggetti tipizzati, è tuttavia possibile creare un campo che restituisca un solo <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="d7d50-141">Instead of creating a field that returns an array of typed objects, however, you can create a field that returns a single <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="d7d50-142">Tuttavia, così come avviene con le matrici, è necessario informare <xref:System.Xml.Serialization.XmlSerializer> dei tipi di oggetti contenuti in <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="d7d50-142">However, as with arrays, you must inform the <xref:System.Xml.Serialization.XmlSerializer> of the types of objects the <xref:System.Collections.ArrayList> contains.</span></span> <span data-ttu-id="d7d50-143">A tale scopo, assegnare più istanze di <xref:System.Xml.Serialization.XmlElementAttribute> al campo, come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d7d50-143">To accomplish this, assign multiple instances of the <xref:System.Xml.Serialization.XmlElementAttribute> to the field, as shown in the following example.</span></span>

```vb
Public Class Group
    <XmlElement(Type:=GetType(Employee)), _
    XmlElement(Type:=GetType(Manager))> _
    Public Info As ArrayList
End Class
```

```csharp
public class Group {
    [XmlElement(Type = typeof(Employee)),
    XmlElement(Type = typeof(Manager))]
    public ArrayList Info;
}
```

## <a name="controlling-serialization-of-classes-using-xmlrootattribute-and-xmltypeattribute"></a><span data-ttu-id="d7d50-144">Controllo della serializzazione di classi tramite XmlRootAttribute e XmlTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="d7d50-144">Controlling Serialization of Classes Using XmlRootAttribute and XmlTypeAttribute</span></span>

<span data-ttu-id="d7d50-145">Esistono due attributi applicabili a una classe (e solo a una classe): <xref:System.Xml.Serialization.XmlRootAttribute> e <xref:System.Xml.Serialization.XmlTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d7d50-145">There are two attributes that can be applied to a class (and only a class): <xref:System.Xml.Serialization.XmlRootAttribute> and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span> <span data-ttu-id="d7d50-146">Questi attributi sono molto simili.</span><span class="sxs-lookup"><span data-stu-id="d7d50-146">These attributes are very similar.</span></span> <span data-ttu-id="d7d50-147"><xref:System.Xml.Serialization.XmlRootAttribute> può essere applicato a una sola classe, ovvero alla classe che, se serializzata, rappresenta l'elemento di apertura e chiusura del documento XML, in altre parole, l'elemento principale.</span><span class="sxs-lookup"><span data-stu-id="d7d50-147">The <xref:System.Xml.Serialization.XmlRootAttribute> can be applied to only one class: the class that, when serialized, represents the XML document's opening and closing element—in other words, the root element.</span></span> <span data-ttu-id="d7d50-148"><xref:System.Xml.Serialization.XmlTypeAttribute>, invece, può essere applicato a qualsiasi classe, inclusa la classe radice.</span><span class="sxs-lookup"><span data-stu-id="d7d50-148">The <xref:System.Xml.Serialization.XmlTypeAttribute>, on the other hand, can be applied to any class, including the root class.</span></span>

<span data-ttu-id="d7d50-149">Ad esempio, negli esempi precedenti, la classe `Group` è la classe radice e tutte le sue proprietà e i campi pubblici diventano gli elementi XML trovati nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="d7d50-149">For example, in the previous examples, the `Group` class is the root class, and all its public fields and properties become the XML elements found in the XML document.</span></span> <span data-ttu-id="d7d50-150">Pertanto, può essere presente un solo nodo radice.</span><span class="sxs-lookup"><span data-stu-id="d7d50-150">Therefore, there can be only one root class.</span></span> <span data-ttu-id="d7d50-151">Tramite l'applicazione di <xref:System.Xml.Serialization.XmlRootAttribute>, è possibile controllare il flusso XML generato da <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d7d50-151">By applying the <xref:System.Xml.Serialization.XmlRootAttribute>, you can control the XML stream generated by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="d7d50-152">Ad esempio, è possibile modificare il nome dell'elemento e lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d7d50-152">For example, you can change the element name and namespace.</span></span>

<span data-ttu-id="d7d50-153"><xref:System.Xml.Serialization.XmlTypeAttribute> consente di controllare lo schema dell'XML generato.</span><span class="sxs-lookup"><span data-stu-id="d7d50-153">The <xref:System.Xml.Serialization.XmlTypeAttribute> allows you to control the schema of the generated XML.</span></span> <span data-ttu-id="d7d50-154">Questa funzionalità risulta utile quando è necessario pubblicare lo schema tramite un servizio Web XML.</span><span class="sxs-lookup"><span data-stu-id="d7d50-154">This capability is useful when you need to publish the schema through an XML Web service.</span></span> <span data-ttu-id="d7d50-155">Nell'esempio riportato di seguito, viene applicato sia <xref:System.Xml.Serialization.XmlTypeAttribute> che <xref:System.Xml.Serialization.XmlRootAttribute> alla stessa classe.</span><span class="sxs-lookup"><span data-stu-id="d7d50-155">The following example applies both the <xref:System.Xml.Serialization.XmlTypeAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the same class.</span></span>

```vb
<XmlRoot("NewGroupName"), _
XmlType("NewTypeName")> _
Public Class Group
    Public Employees() As Employee
End Class
```

```csharp
[XmlRoot("NewGroupName")]
[XmlType("NewTypeName")]
public class Group {
    public Employee[] Employees;
}
```

<span data-ttu-id="d7d50-156">Se questa classe è compilata e viene utilizzato lo strumento XML Schema Definition per generare lo schema, viene creato il seguente XML che descrive `Group`.</span><span class="sxs-lookup"><span data-stu-id="d7d50-156">If this class is compiled, and the XML Schema Definition tool is used to generate its schema, you would find the following XML describing `Group`.</span></span>

```xml
<xs:element name="NewGroupName" type="NewTypeName" />
```

<span data-ttu-id="d7d50-157">Al contrario, se si fosse dovuta serializzare un'istanza della classe, nel documento XML si sarebbe trovato solo `NewGroupName`.</span><span class="sxs-lookup"><span data-stu-id="d7d50-157">In contrast, if you were to serialize an instance of the class, only `NewGroupName` would be found in the XML document.</span></span>

```xml
<NewGroupName>
    . . .
</NewGroupName>
```

## <a name="preventing-serialization-with-the-xmlignoreattribute"></a><span data-ttu-id="d7d50-158">Come impedire la serializzazione con XmlIgnoreAttribute</span><span class="sxs-lookup"><span data-stu-id="d7d50-158">Preventing Serialization with the XmlIgnoreAttribute</span></span>

<span data-ttu-id="d7d50-159">Potrebbero presentarsi delle situazioni in cui un campo o una proprietà pubblica non necessitano della serializzazione.</span><span class="sxs-lookup"><span data-stu-id="d7d50-159">There might be situations when a public property or field does not need to be serialized.</span></span> <span data-ttu-id="d7d50-160">Ad esempio, un campo o una proprietà possono essere utilizzati per contenere metadati.</span><span class="sxs-lookup"><span data-stu-id="d7d50-160">For example, a field or property could be used to contain metadata.</span></span> <span data-ttu-id="d7d50-161">In tali casi, applicare <xref:System.Xml.Serialization.XmlIgnoreAttribute> al campo o alla proprietà e <xref:System.Xml.Serialization.XmlSerializer> permetterà di ignorarli.</span><span class="sxs-lookup"><span data-stu-id="d7d50-161">In such cases, apply the <xref:System.Xml.Serialization.XmlIgnoreAttribute> to the field or property and the <xref:System.Xml.Serialization.XmlSerializer> will skip over it.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7d50-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7d50-162">See also</span></span>

- [<span data-ttu-id="d7d50-163">Attributi che controllano la serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="d7d50-163">Attributes That Control XML Serialization</span></span>](attributes-that-control-xml-serialization.md)
- [<span data-ttu-id="d7d50-164">Attributi che controllano la serializzazione SOAP codificata</span><span class="sxs-lookup"><span data-stu-id="d7d50-164">Attributes That Control Encoded SOAP Serialization</span></span>](attributes-that-control-encoded-soap-serialization.md)
- [<span data-ttu-id="d7d50-165">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="d7d50-165">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="d7d50-166">Esempi di serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="d7d50-166">Examples of XML Serialization</span></span>](examples-of-xml-serialization.md)
- [<span data-ttu-id="d7d50-167">Procedura: specificare un nome di elemento alternativo per un flusso XML</span><span class="sxs-lookup"><span data-stu-id="d7d50-167">How to: Specify an Alternate Element Name for an XML Stream</span></span>](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [<span data-ttu-id="d7d50-168">Procedura: serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="d7d50-168">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="d7d50-169">Procedura: Deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="d7d50-169">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)

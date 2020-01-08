---
title: Panoramica della classe XAttribute (C#)
ms.date: 07/20/2015
ms.assetid: 5a630f24-f9ad-400e-831e-c14ebfc9e142
ms.openlocfilehash: 7a806314664c6319fc45cff0dddedbe38027059d
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635665"
---
# <a name="xattribute-class-overview-c"></a><span data-ttu-id="f25d5-102">Panoramica della classe XAttribute (C#)</span><span class="sxs-lookup"><span data-stu-id="f25d5-102">XAttribute Class Overview (C#)</span></span>
<span data-ttu-id="f25d5-103">Gli attributi sono coppie nome/valore associate a un elemento.</span><span class="sxs-lookup"><span data-stu-id="f25d5-103">Attributes are name/value pairs that are associated with an element.</span></span> <span data-ttu-id="f25d5-104">La classe <xref:System.Xml.Linq.XAttribute> rappresenta gli attributi XML.</span><span class="sxs-lookup"><span data-stu-id="f25d5-104">The <xref:System.Xml.Linq.XAttribute> class represents XML attributes.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="f25d5-105">Panoramica di</span><span class="sxs-lookup"><span data-stu-id="f25d5-105">Overview</span></span>  
 <span data-ttu-id="f25d5-106">Le modalità di utilizzo degli attributi in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sono simili a quelle degli elementi.</span><span class="sxs-lookup"><span data-stu-id="f25d5-106">Working with attributes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is similar to working with elements.</span></span> <span data-ttu-id="f25d5-107">I relativi costruttori sono simili.</span><span class="sxs-lookup"><span data-stu-id="f25d5-107">Their constructors are similar.</span></span> <span data-ttu-id="f25d5-108">I metodi usati per recuperare le relative raccolte sono simili.</span><span class="sxs-lookup"><span data-stu-id="f25d5-108">The methods that you use to retrieve collections of them are similar.</span></span> <span data-ttu-id="f25d5-109">Un'espressione di query LINQ per una raccolta di attributi ha un aspetto molto simile a un'espressione di query LINQ per una raccolta di elementi.</span><span class="sxs-lookup"><span data-stu-id="f25d5-109">A LINQ query expression for a collection of attributes looks very similar to a LINQ query expression for a collection of elements.</span></span>  
  
 <span data-ttu-id="f25d5-110">L'ordine con cui gli attributi vengono aggiunti a un elemento viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="f25d5-110">The order in which attributes were added to an element is preserved.</span></span> <span data-ttu-id="f25d5-111">Quando si scorrono gli attributi, questi vengono visualizzati nell'ordine in cui sono stati aggiunti.</span><span class="sxs-lookup"><span data-stu-id="f25d5-111">That is, when you iterate through the attributes, you see them in the same order that they were added.</span></span>  
  
## <a name="the-xattribute-constructor"></a><span data-ttu-id="f25d5-112">Costruttore XAttribute</span><span class="sxs-lookup"><span data-stu-id="f25d5-112">The XAttribute Constructor</span></span>  
 <span data-ttu-id="f25d5-113">Il seguente costruttore della classe <xref:System.Xml.Linq.XAttribute> è quello usato più comunemente:</span><span class="sxs-lookup"><span data-stu-id="f25d5-113">The following constructor of the <xref:System.Xml.Linq.XAttribute> class is the one that you will most commonly use:</span></span>  
  
|<span data-ttu-id="f25d5-114">Costruttore</span><span class="sxs-lookup"><span data-stu-id="f25d5-114">Constructor</span></span>|<span data-ttu-id="f25d5-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f25d5-115">Description</span></span>|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|<span data-ttu-id="f25d5-116">Crea un oggetto <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f25d5-116">Creates an <xref:System.Xml.Linq.XAttribute> object.</span></span> <span data-ttu-id="f25d5-117">L'argomento `name` specifica il nome dell'attributo, mentre `content` ne specifica il contenuto.</span><span class="sxs-lookup"><span data-stu-id="f25d5-117">The `name` argument specifies the name of the attribute; `content` specifies the content of the attribute.</span></span>|  
  
### <a name="creating-an-element-with-an-attribute"></a><span data-ttu-id="f25d5-118">Creazione di un elemento con un attributo</span><span class="sxs-lookup"><span data-stu-id="f25d5-118">Creating an Element with an Attribute</span></span>  
 <span data-ttu-id="f25d5-119">Nel codice seguente è illustrata l'attività comune di creazione di un elemento che contiene un attributo:</span><span class="sxs-lookup"><span data-stu-id="f25d5-119">The following code shows the common task of creating an element that contains an attribute:</span></span>  
  
```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 <span data-ttu-id="f25d5-120">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="f25d5-120">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a><span data-ttu-id="f25d5-121">Costruzione funzionale di attributi</span><span class="sxs-lookup"><span data-stu-id="f25d5-121">Functional Construction of Attributes</span></span>  
 <span data-ttu-id="f25d5-122">È possibile costruire oggetti <xref:System.Xml.Linq.XAttribute> in linea con la costruzione di oggetti <xref:System.Xml.Linq.XElement>, come descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="f25d5-122">You can construct <xref:System.Xml.Linq.XAttribute> objects in-line with the construction of <xref:System.Xml.Linq.XElement> objects, as follows:</span></span>  
  
```csharp  
XElement c = new XElement("Customers",  
    new XElement("Customer",  
        new XElement("Name", "John Doe"),  
        new XElement("PhoneNumbers",  
            new XElement("Phone",  
                new XAttribute("type", "home"),  
                "555-555-5555"),  
            new XElement("Phone",  
                new XAttribute("type", "work"),  
                "666-666-6666")  
        )  
    )  
);  
Console.WriteLine(c);  
```  
  
 <span data-ttu-id="f25d5-123">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="f25d5-123">This example produces the following output:</span></span>  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a><span data-ttu-id="f25d5-124">Attributi non nodi</span><span class="sxs-lookup"><span data-stu-id="f25d5-124">Attributes Are Not Nodes</span></span>  
 <span data-ttu-id="f25d5-125">Esistono alcune differenze tra attributi ed elementi.</span><span class="sxs-lookup"><span data-stu-id="f25d5-125">There are some differences between attributes and elements.</span></span> <span data-ttu-id="f25d5-126">Gli oggetti <xref:System.Xml.Linq.XAttribute> non rappresentano nodi nell'albero XML,</span><span class="sxs-lookup"><span data-stu-id="f25d5-126"><xref:System.Xml.Linq.XAttribute> objects are not nodes in the XML tree.</span></span> <span data-ttu-id="f25d5-127">ma sono coppie nome/valore associate a un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="f25d5-127">They are name/value pairs associated with an XML element.</span></span> <span data-ttu-id="f25d5-128">A differenza del modello DOM (Document Object Model), questa definizione rispecchia maggiormente la struttura del codice XML.</span><span class="sxs-lookup"><span data-stu-id="f25d5-128">In contrast to the Document Object Model (DOM), this more closely reflects the structure of XML.</span></span> <span data-ttu-id="f25d5-129">Sebbene gli oggetti <xref:System.Xml.Linq.XAttribute> non siano effettivamente nodi dell'albero XML, le modalità di utilizzo degli oggetti <xref:System.Xml.Linq.XAttribute> sono molto simili a quelle degli oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="f25d5-129">Although <xref:System.Xml.Linq.XAttribute> objects are not actually nodes in the XML tree, working with <xref:System.Xml.Linq.XAttribute> objects is very similar to working with <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="f25d5-130">Questa distinzione è di fondamentale importanza solo per gli sviluppatori che scrivono codice che riguarda gli alberi XML a livello di nodo.</span><span class="sxs-lookup"><span data-stu-id="f25d5-130">This distinction is primarily important only to developers who are writing code that works with XML trees at the node level.</span></span> <span data-ttu-id="f25d5-131">Non interessa quindi la maggior parte degli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="f25d5-131">Many developers will not be concerned with this distinction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f25d5-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f25d5-132">See also</span></span>

- [<span data-ttu-id="f25d5-133">Panoramica della programmazione con LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="f25d5-133">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)

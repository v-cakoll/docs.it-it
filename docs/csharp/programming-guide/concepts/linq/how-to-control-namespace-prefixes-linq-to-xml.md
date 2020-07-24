---
title: Come controllare i prefissi degli spazi dei nomi (C#) (LINQ to XML)
description: Informazioni su come controllare i prefissi degli spazi dei nomi durante la serializzazione di un albero XML in LINQ to XML in C#. Alcune situazioni richiedono il controllo dei prefissi degli spazi dei nomi.
ms.date: 07/20/2015
ms.assetid: 64de5186-b81a-4ddd-8327-8693df59a01b
ms.openlocfilehash: b0c5cbfa7488f3a7105595830ef6765e6bfb1f12
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105302"
---
# <a name="how-to-control-namespace-prefixes-c-linq-to-xml"></a><span data-ttu-id="dd602-104">Come controllare i prefissi degli spazi dei nomi (C#) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="dd602-104">How to control namespace prefixes (C#) (LINQ to XML)</span></span>
<span data-ttu-id="dd602-105">In questo argomento viene descritto come controllare i prefissi degli spazi dei nomi durante la serializzazione di un albero XML.</span><span class="sxs-lookup"><span data-stu-id="dd602-105">This topic describes how you can control namespace prefixes when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="dd602-106">In molte situazioni non è necessario controllare i prefissi degli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dd602-106">In many situations, it is not necessary to control namespace prefixes.</span></span>  
  
 <span data-ttu-id="dd602-107">Tuttavia, determinati strumenti di programmazione XML richiedono il controllo specifico dei prefissi degli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dd602-107">However, certain XML programming tools require specific control of namespace prefixes.</span></span> <span data-ttu-id="dd602-108">Ad esempio, si potrebbe stare modificando un foglio di stile XSLT o un documento XAML contenente espressioni XPath incorporate che fanno riferimento a prefissi di spazi dei nomi specifici; in questo caso è importante che il documento sia serializzato con tali prefissi specifici.</span><span class="sxs-lookup"><span data-stu-id="dd602-108">For example, you might be manipulating an XSLT style sheet or a XAML document that contains embedded XPath expressions that refer to specific namespace prefixes; in this case, it is important that the document be serialized with those specific prefixes.</span></span>  
  
 <span data-ttu-id="dd602-109">Ciò rappresenta il motivo più comune per il controllo dei prefissi degli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dd602-109">This is the most common reason for controlling namespace prefixes.</span></span>  
  
 <span data-ttu-id="dd602-110">Il controllo dei prefissi degli spazi dei nomi viene richiesto anche quando si desidera che gli utenti modifichino manualmente il documento XML e si desidera creare prefissi che l'utente può digitare con maggior comodità.</span><span class="sxs-lookup"><span data-stu-id="dd602-110">Another common reason for controlling namespace prefixes is that you want users to edit the XML document manually, and you want to create namespace prefixes that are convenient for the user to type.</span></span> <span data-ttu-id="dd602-111">Ad esempio, se si intende generare un documento XSD,</span><span class="sxs-lookup"><span data-stu-id="dd602-111">For example, you might be generating an XSD document.</span></span> <span data-ttu-id="dd602-112">le convenzioni degli schemi consigliano l'uso di `xs` o `xsd` come prefisso per lo spazio dei nomi dello schema.</span><span class="sxs-lookup"><span data-stu-id="dd602-112">Conventions for schemas suggest that you use either `xs` or `xsd` as the prefix for the schema namespace.</span></span>  
  
 <span data-ttu-id="dd602-113">Per controllare i prefissi degli spazi dei nomi, si inseriscono attributi che dichiarano gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dd602-113">To control namespace prefixes, you insert attributes that declare namespaces.</span></span> <span data-ttu-id="dd602-114">Se si dichiarano gli spazi dei nomi con prefissi specifici, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] tenterà di rispettare tali prefissi durante la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="dd602-114">If you declare the namespaces with specific prefixes, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will attempt to honor the namespace prefixes when serializing.</span></span>  
  
 <span data-ttu-id="dd602-115">Per creare un attributo che dichiara uno spazio dei nomi con un prefisso, viene creato un attributo in cui lo spazio dei nomi del nome dell'attributo è <xref:System.Xml.Linq.XNamespace.Xmlns%2A> e il nome dell'attributo è il prefisso dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dd602-115">To create an attribute that declares a namespace with a prefix, you create an attribute where the namespace of the name of the attribute is <xref:System.Xml.Linq.XNamespace.Xmlns%2A>, and the name of the attribute is the namespace prefix.</span></span> <span data-ttu-id="dd602-116">Il valore dell'attributo è l'URI dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dd602-116">The value of the attribute is the URI of the namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd602-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd602-117">Example</span></span>  
 <span data-ttu-id="dd602-118">In questo esempio vengono dichiarati due spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dd602-118">This example declares two namespaces.</span></span> <span data-ttu-id="dd602-119">Viene specificato che lo spazio dei nomi `http://www.adventure-works.com` ha il prefisso `aw` e lo spazio dei nomi `www.fourthcoffee.com` ha il prefisso `fc`.</span><span class="sxs-lookup"><span data-stu-id="dd602-119">It specifies that the `http://www.adventure-works.com` namespace has the prefix of `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="dd602-120">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="dd602-120">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd602-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd602-121">See also</span></span>

- [<span data-ttu-id="dd602-122">Panoramica degli spazi dei nomi (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="dd602-122">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)

---
title: 'Procedura: Controllare i prefissi dello spazio dei nomi (C#) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 64de5186-b81a-4ddd-8327-8693df59a01b
ms.openlocfilehash: 4664be2661e54782598345886029835108934955
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714032"
---
# <a name="how-to-control-namespace-prefixes-c-linq-to-xml"></a><span data-ttu-id="1c569-102">Procedura: Controllare i prefissi dello spazio dei nomi (C#) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="1c569-102">How to: Control Namespace Prefixes (C#) (LINQ to XML)</span></span>
<span data-ttu-id="1c569-103">In questo argomento viene descritto come controllare i prefissi degli spazi dei nomi durante la serializzazione di un albero XML.</span><span class="sxs-lookup"><span data-stu-id="1c569-103">This topic describes how you can control namespace prefixes when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="1c569-104">In molte situazioni non è necessario controllare i prefissi degli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1c569-104">In many situations, it is not necessary to control namespace prefixes.</span></span>  
  
 <span data-ttu-id="1c569-105">Tuttavia, determinati strumenti di programmazione XML richiedono il controllo specifico dei prefissi degli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1c569-105">However, certain XML programming tools require specific control of namespace prefixes.</span></span> <span data-ttu-id="1c569-106">Ad esempio, si potrebbe stare modificando un foglio di stile XSLT o un documento XAML contenente espressioni XPath incorporate che fanno riferimento a prefissi di spazi dei nomi specifici; in questo caso è importante che il documento sia serializzato con tali prefissi specifici.</span><span class="sxs-lookup"><span data-stu-id="1c569-106">For example, you might be manipulating an XSLT style sheet or a XAML document that contains embedded XPath expressions that refer to specific namespace prefixes; in this case, it is important that the document be serialized with those specific prefixes.</span></span>  
  
 <span data-ttu-id="1c569-107">Ciò rappresenta il motivo più comune per il controllo dei prefissi degli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1c569-107">This is the most common reason for controlling namespace prefixes.</span></span>  
  
 <span data-ttu-id="1c569-108">Il controllo dei prefissi degli spazi dei nomi viene richiesto anche quando si desidera che gli utenti modifichino manualmente il documento XML e si desidera creare prefissi che l'utente può digitare con maggior comodità.</span><span class="sxs-lookup"><span data-stu-id="1c569-108">Another common reason for controlling namespace prefixes is that you want users to edit the XML document manually, and you want to create namespace prefixes that are convenient for the user to type.</span></span> <span data-ttu-id="1c569-109">Ad esempio, se si intende generare un documento XSD,</span><span class="sxs-lookup"><span data-stu-id="1c569-109">For example, you might be generating an XSD document.</span></span> <span data-ttu-id="1c569-110">le convenzioni degli schemi consigliano l'uso di `xs` o `xsd` come prefisso per lo spazio dei nomi dello schema.</span><span class="sxs-lookup"><span data-stu-id="1c569-110">Conventions for schemas suggest that you use either `xs` or `xsd` as the prefix for the schema namespace.</span></span>  
  
 <span data-ttu-id="1c569-111">Per controllare i prefissi degli spazi dei nomi, si inseriscono attributi che dichiarano gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1c569-111">To control namespace prefixes, you insert attributes that declare namespaces.</span></span> <span data-ttu-id="1c569-112">Se si dichiarano gli spazi dei nomi con prefissi specifici, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] tenterà di rispettare tali prefissi durante la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="1c569-112">If you declare the namespaces with specific prefixes, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will attempt to honor the namespace prefixes when serializing.</span></span>  
  
 <span data-ttu-id="1c569-113">Per creare un attributo che dichiara uno spazio dei nomi con un prefisso, viene creato un attributo in cui lo spazio dei nomi del nome dell'attributo è <xref:System.Xml.Linq.XNamespace.Xmlns%2A> e il nome dell'attributo è il prefisso dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1c569-113">To create an attribute that declares a namespace with a prefix, you create an attribute where the namespace of the name of the attribute is <xref:System.Xml.Linq.XNamespace.Xmlns%2A>, and the name of the attribute is the namespace prefix.</span></span> <span data-ttu-id="1c569-114">Il valore dell'attributo è l'URI dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1c569-114">The value of the attribute is the URI of the namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c569-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c569-115">Example</span></span>  
 <span data-ttu-id="1c569-116">In questo esempio vengono dichiarati due spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1c569-116">This example declares two namespaces.</span></span> <span data-ttu-id="1c569-117">Viene specificato che lo spazio dei nomi `http://www.adventure-works.com` ha il prefisso `aw` e lo spazio dei nomi `www.fourthcoffee.com` ha il prefisso `fc`.</span><span class="sxs-lookup"><span data-stu-id="1c569-117">It specifies that the `http://www.adventure-works.com` namespace has the prefix of `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
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
  
 <span data-ttu-id="1c569-118">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="1c569-118">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c569-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c569-119">See also</span></span>

- [<span data-ttu-id="1c569-120">Uso degli spazi dei nomi XML (C#)</span><span class="sxs-lookup"><span data-stu-id="1c569-120">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)

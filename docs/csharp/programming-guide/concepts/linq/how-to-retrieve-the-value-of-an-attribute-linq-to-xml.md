---
title: 'Procedura: Recuperare il valore di un attributo (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
ms.openlocfilehash: 224ba9ba47d68afd7c29d0f33fe20d290d0b5ef5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319127"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a><span data-ttu-id="75ba2-102">Procedura: Recuperare il valore di un attributo (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="75ba2-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="75ba2-103">In questo argomento viene illustrato come ottenere il valore di attributi.</span><span class="sxs-lookup"><span data-stu-id="75ba2-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="75ba2-104">Per eseguire questa operazione, è possibile scegliere tra due alternative. È possibile eseguire il cast di un <xref:System.Xml.Linq.XAttribute> al tipo desiderato; l'operatore di conversione esplicito converte quindi il contenuto dell'elemento o dell'attributo al tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="75ba2-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="75ba2-105">In alternativa, è possibile usare la proprietà <xref:System.Xml.Linq.XAttribute.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="75ba2-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="75ba2-106">L'esecuzione del cast costituisce in genere l'approccio migliore.</span><span class="sxs-lookup"><span data-stu-id="75ba2-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="75ba2-107">Se si esegue il cast dell'attributo a un tipo nullable, sarà più semplice scrivere il codice quando si recupera il valore di un attributo che potrebbe o meno esistere.</span><span class="sxs-lookup"><span data-stu-id="75ba2-107">If you cast the attribute to a nullable type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="75ba2-108">Per esempi di questa tecnica, vedere [Procedura: Recuperare il valore di un elemento (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="75ba2-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="75ba2-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="75ba2-109">Example</span></span>  
 <span data-ttu-id="75ba2-110">Per recuperare il valore di un attributo, è sufficiente eseguire il cast dell'oggetto <xref:System.Xml.Linq.XAttribute> al tipo desiderato.</span><span class="sxs-lookup"><span data-stu-id="75ba2-110">To retrieve the value of an attribute, you just cast the <xref:System.Xml.Linq.XAttribute> object to your desired type.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="75ba2-111">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="75ba2-111">This example produces the following output:</span></span>  
  
```  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="75ba2-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="75ba2-112">Example</span></span>  
 <span data-ttu-id="75ba2-113">Nell'esempio seguente viene illustrato come recuperare il valore di un attributo quando l'attributo è in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="75ba2-113">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="75ba2-114">Per altre informazioni, vedere [Uso degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="75ba2-114">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="75ba2-115">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="75ba2-115">This example produces the following output:</span></span>  
  
```  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="75ba2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75ba2-116">See Also</span></span>  
 [<span data-ttu-id="75ba2-117">Assi LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="75ba2-117">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)

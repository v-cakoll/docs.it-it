---
title: 'Procedura: Recuperare il valore di un attributo (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: 48ad3c0ab079012793fd9eea89d52fc3a7b1698f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397804"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="f963d-102">Procedura: recuperare il valore di un attributo (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f963d-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="f963d-103">In questo argomento viene illustrato come ottenere il valore di attributi.</span><span class="sxs-lookup"><span data-stu-id="f963d-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="f963d-104">Per eseguire questa operazione, è possibile scegliere tra due alternative. È possibile eseguire il cast di un <xref:System.Xml.Linq.XAttribute> al tipo desiderato; l'operatore di conversione esplicito converte quindi il contenuto dell'elemento o dell'attributo al tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="f963d-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="f963d-105">In alternativa, è possibile usare la proprietà <xref:System.Xml.Linq.XAttribute.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="f963d-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="f963d-106">L'esecuzione del cast costituisce in genere l'approccio migliore.</span><span class="sxs-lookup"><span data-stu-id="f963d-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="f963d-107">Se si esegue il cast dell'attributo a un tipo di valore Nullable, il codice è più semplice da scrivere quando si recupera il valore di un attributo che potrebbe o meno esistere.</span><span class="sxs-lookup"><span data-stu-id="f963d-107">If you cast the attribute to a nullable value type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="f963d-108">Per esempi di questa tecnica, vedere [procedura: recuperare il valore di un elemento (LINQ to XML) (Visual Basic)](how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f963d-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)](how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f963d-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="f963d-109">Example</span></span>  
 <span data-ttu-id="f963d-110">In Visual Basic è possibile usare la proprietà integrata dell'attributo per recuperare il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="f963d-110">In Visual Basic, you can use the integrated attribute property to retrieve the value of an attribute.</span></span>  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="f963d-111">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="f963d-111">This example produces the following output:</span></span>  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="f963d-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="f963d-112">Example</span></span>  
 <span data-ttu-id="f963d-113">In Visual Basic è possibile usare la proprietà integrata dell'attributo per impostare il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="f963d-113">In Visual Basic, you can use the integrated attribute property to set the value of an attribute.</span></span> <span data-ttu-id="f963d-114">Se inoltre si usa la proprietà integrata dell'attributo per impostare il valore di un attributo non esistente, l'attributo verrà creato.</span><span class="sxs-lookup"><span data-stu-id="f963d-114">Further, if you use the integrated attribute property to set the value of an attribute that does not exist, the attribute will be created.</span></span>  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="f963d-115">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="f963d-115">This example produces the following output:</span></span>  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a><span data-ttu-id="f963d-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="f963d-116">Example</span></span>  
 <span data-ttu-id="f963d-117">Nell'esempio seguente viene illustrato come recuperare il valore di un attributo quando l'attributo è in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f963d-117">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="f963d-118">Per ulteriori informazioni, vedere [Cenni preliminari sugli spazi dei nomi (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f963d-118">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root aw:Attr="abcde"/>  
        Dim str As String = root.@aw:Attr  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="f963d-119">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="f963d-119">This example produces the following output:</span></span>  
  
```console  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="f963d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f963d-120">See also</span></span>

- [<span data-ttu-id="f963d-121">Assi LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f963d-121">LINQ to XML Axes (Visual Basic)</span></span>](linq-to-xml-axes.md)

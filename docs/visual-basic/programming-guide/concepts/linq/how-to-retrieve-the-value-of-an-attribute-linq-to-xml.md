---
title: 'Procedura: recuperare il valore di un attributo (LINQ to XML) (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 6ecc1368832b9c98efeae65c95438efb80f164f6
ms.contentlocale: it-it
ms.lasthandoff: 06/01/2017


---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="c6d0a-102">Procedura: recuperare il valore di un attributo (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6d0a-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="c6d0a-103">In questo argomento viene illustrato come ottenere il valore di attributi.</span><span class="sxs-lookup"><span data-stu-id="c6d0a-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="c6d0a-104">Esistono due modi: È possibile eseguire il cast un <xref:System.Xml.Linq.XAttribute>al tipo desiderato; l'operatore di conversione esplicito converte quindi il contenuto dell'elemento o attributo al tipo specificato.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="c6d0a-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="c6d0a-105">In alternativa, è possibile utilizzare il <xref:System.Xml.Linq.XAttribute.Value%2A>proprietà.</xref:System.Xml.Linq.XAttribute.Value%2A></span><span class="sxs-lookup"><span data-stu-id="c6d0a-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="c6d0a-106">L'esecuzione del cast costituisce in genere l'approccio migliore.</span><span class="sxs-lookup"><span data-stu-id="c6d0a-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="c6d0a-107">Se si esegue il cast dell'attributo a un tipo nullable, sarà più semplice scrivere il codice quando si recupera il valore di un attributo che potrebbe o meno esistere.</span><span class="sxs-lookup"><span data-stu-id="c6d0a-107">If you cast the attribute to a nullable type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="c6d0a-108">Per esempi di questa tecnica, vedere [procedura: recuperare il valore di un elemento (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c6d0a-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6d0a-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="c6d0a-109">Example</span></span>  
 <span data-ttu-id="c6d0a-110">In Visual Basic è possibile usare la proprietà integrata dell'attributo per recuperare il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="c6d0a-110">In Visual Basic, you can use the integrated attribute property to retrieve the value of an attribute.</span></span>  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="c6d0a-111">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="c6d0a-111">This example produces the following output:</span></span>  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="c6d0a-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="c6d0a-112">Example</span></span>  
 <span data-ttu-id="c6d0a-113">In Visual Basic è possibile usare la proprietà integrata dell'attributo per impostare il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="c6d0a-113">In Visual Basic, you can use the integrated attribute property to set the value of an attribute.</span></span> <span data-ttu-id="c6d0a-114">Se inoltre si usa la proprietà integrata dell'attributo per impostare il valore di un attributo non esistente, l'attributo verrà creato.</span><span class="sxs-lookup"><span data-stu-id="c6d0a-114">Further, if you use the integrated attribute property to set the value of an attribute that does not exist, the attribute will be created.</span></span>  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="c6d0a-115">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="c6d0a-115">This example produces the following output:</span></span>  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a><span data-ttu-id="c6d0a-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="c6d0a-116">Example</span></span>  
 <span data-ttu-id="c6d0a-117">Nell'esempio seguente viene illustrato come recuperare il valore di un attributo quando l'attributo è in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c6d0a-117">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="c6d0a-118">Per ulteriori informazioni, vedere [utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="c6d0a-118">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
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
  
 <span data-ttu-id="c6d0a-119">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="c6d0a-119">This example produces the following output:</span></span>  
  
```  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6d0a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6d0a-120">See Also</span></span>  
 [<span data-ttu-id="c6d0a-121">Assi LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6d0a-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)

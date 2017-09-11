---
title: 'Procedura: creare un documento con spazi dei nomi (LINQ to XML) (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: cc5b0d4d-360c-4ada-94fa-2d2916e989be
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 60206722fff1d10c8368cbdd24ec6ca15dd207be
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-a-document-with-namespaces-linq-to-xml-visual-basic"></a><span data-ttu-id="8361a-102">Procedura: creare un documento con spazi dei nomi (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8361a-102">How to: Create a Document with Namespaces (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="8361a-103">In questo argomento viene illustrato come creare un documento con spazi dei nomi in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8361a-103">This topic shows how to create a document with namespaces in Visual Basic.</span></span>  
  
 <span data-ttu-id="8361a-104">Quando si usano valori letterali XML in Visual Basic, gli utenti possono definire un unico spazio dei nomi XML predefinito globale.</span><span class="sxs-lookup"><span data-stu-id="8361a-104">When using XML literals in Visual Basic, users can define one global default XML namespace.</span></span> <span data-ttu-id="8361a-105">Tale spazio dei nomi è quello predefinito sia per i valori letterali XML che per le proprietà XML.</span><span class="sxs-lookup"><span data-stu-id="8361a-105">This namespace is the default namespace for both XML literals and XML properties.</span></span> <span data-ttu-id="8361a-106">Lo spazio dei nomi XML predefinito può essere definito a livello di progetto o di file.</span><span class="sxs-lookup"><span data-stu-id="8361a-106">The default XML namespace can be defined at either the project level or the file level.</span></span> <span data-ttu-id="8361a-107">Se viene definito a livello di file, sostituisce quello predefinito a livello di progetto.</span><span class="sxs-lookup"><span data-stu-id="8361a-107">If it is defined at the file level, it overrides the default namespace at the project level.</span></span>  
  
 <span data-ttu-id="8361a-108">È inoltre possibile definire altri spazi dei nomi e specificarne i prefissi.</span><span class="sxs-lookup"><span data-stu-id="8361a-108">You can also define other namespaces, and specify the namespace prefixes for those namespaces.</span></span>  
  
 <span data-ttu-id="8361a-109">Per definire spazi dei nomi predefiniti e spazi dei nomi con prefissi, usare la parola chiave `Imports`.</span><span class="sxs-lookup"><span data-stu-id="8361a-109">You define both default namespaces and namespaces with a prefix by using the `Imports` keyword.</span></span>  
  
 <span data-ttu-id="8361a-110">Per ulteriori informazioni, vedere [Introduzione ai valori letterali XML in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-xml-literals.md).</span><span class="sxs-lookup"><span data-stu-id="8361a-110">For more information, see [Introduction to XML Literals in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-xml-literals.md).</span></span>  
  
 <span data-ttu-id="8361a-111">Notare che lo spazio dei nomi XML predefinito si applica solo agli elementi e non agli attributi.</span><span class="sxs-lookup"><span data-stu-id="8361a-111">Note that the default XML namespace only applies to elements and not to attributes.</span></span> <span data-ttu-id="8361a-112">Per impostazione predefinita, gli attributi non sono inclusi in nessuno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8361a-112">Attributes are by default always in no namespace.</span></span> <span data-ttu-id="8361a-113">È tuttavia possibile usare un prefisso dello spazio dei nomi per inserire un attributo in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8361a-113">However, you can use a namespace prefix to put an attribute in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8361a-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="8361a-114">Example</span></span>  
 <span data-ttu-id="8361a-115">In questo esempio viene creato un documento contenente uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8361a-115">This example creates a document that contains a namespace.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child aw:Att="attvalue"/>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="8361a-116">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="8361a-116">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child aw:Att="attvalue" />  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="8361a-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="8361a-117">Example</span></span>  
 <span data-ttu-id="8361a-118">In questo esempio viene creato un documento contenente due spazi dei nomi, uno dei quali è quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="8361a-118">This example creates a document that contains two namespaces, one of which is the default namespace.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child Att="attvalue"/>  
                <fc:Child2>child2 content</fc:Child2>  
            </Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="8361a-119">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="8361a-119">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns:fc="www.fourthcoffee.com" xmlns="http://www.adventure-works.com">  
  <Child Att="attvalue" />  
  <fc:Child2>child2 content</fc:Child2>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="8361a-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="8361a-120">Example</span></span>  
 <span data-ttu-id="8361a-121">Nell'esempio seguente viene creato un documento contenente più spazi dei nomi, tutti con prefisso.</span><span class="sxs-lookup"><span data-stu-id="8361a-121">The following example creates a document that contains multiple namespaces, both with namespace prefixes.</span></span>  
  
 <span data-ttu-id="8361a-122">Quando si serializza un albero XML, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] genera dichiarazioni degli spazi dei nomi in base alle necessità in modo che ogni elemento venga inserito nel relativo spazio dei nomi definito.</span><span class="sxs-lookup"><span data-stu-id="8361a-122">When serializing an XML tree, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] emits namespace declarations as required so that each element is in its designated namespace.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="8361a-123">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="8361a-123">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8361a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8361a-124">See Also</span></span>  
 [<span data-ttu-id="8361a-125">Utilizzo di spazi dei nomi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8361a-125">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)

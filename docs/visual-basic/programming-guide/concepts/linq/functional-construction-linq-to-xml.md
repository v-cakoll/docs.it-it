---
title: Costruzione funzionale (LINQ to XML) (Visual Basic) | Documenti di Microsoft
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
ms.assetid: feac4273-39ab-43ae-bab7-4059c807a785
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
ms.openlocfilehash: b88b67aca337b893f9f276c8e4a6589b6946069b
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="functional-construction-linq-to-xml-visual-basic"></a><span data-ttu-id="526b0-102">Costruzione funzionale (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="526b0-102">Functional Construction (LINQ to XML) (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="526b0-103">fornisce un potente strumento per creare elementi XML chiamati *costruzione funzionale*.</span><span class="sxs-lookup"><span data-stu-id="526b0-103"> provides a powerful way to create XML elements called *functional construction*.</span></span> <span data-ttu-id="526b0-104">Per costruzione funzionale si intende la possibilità di creare una struttura ad albero XML in un'unica istruzione.</span><span class="sxs-lookup"><span data-stu-id="526b0-104">Functional construction is the ability to create an XML tree in a single statement.</span></span>  
  
 <span data-ttu-id="526b0-105">Diverse funzionalità importanti dell'interfaccia di programmazione [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] consentono la costruzione funzionale:</span><span class="sxs-lookup"><span data-stu-id="526b0-105">There are several key features of the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] programming interface that enable functional construction:</span></span>  
  
-   <span data-ttu-id="526b0-106">Il <xref:System.Xml.Linq.XElement>costruttore accetta vari tipi di argomenti per il contenuto.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="526b0-106">The <xref:System.Xml.Linq.XElement> constructor takes various types of arguments for content.</span></span> <span data-ttu-id="526b0-107">Ad esempio, è possibile passare un altro <xref:System.Xml.Linq.XElement>oggetto, che diventa un elemento figlio.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="526b0-107">For example, you can pass another <xref:System.Xml.Linq.XElement> object, which becomes a child element.</span></span> <span data-ttu-id="526b0-108">È possibile passare un <xref:System.Xml.Linq.XAttribute>oggetto, che diventa un attributo dell'elemento.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="526b0-108">You can pass an <xref:System.Xml.Linq.XAttribute> object, which becomes an attribute of the element.</span></span> <span data-ttu-id="526b0-109">Oppure è possibile passare qualsiasi altro tipo di oggetto, che viene convertito in una stringa e diventa il contenuto di testo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="526b0-109">Or you can pass any other type of object, which is converted to a string and becomes the text content of the element.</span></span>  
  
-   <span data-ttu-id="526b0-110">Il <xref:System.Xml.Linq.XElement>costruttore accetta un `params` matrice di tipo <xref:System.Object>, in modo che è possibile passare qualsiasi numero di oggetti al costruttore.</xref:System.Object> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="526b0-110">The <xref:System.Xml.Linq.XElement> constructor takes a `params` array of type <xref:System.Object>, so that you can pass any number of objects to the constructor.</span></span> <span data-ttu-id="526b0-111">In questo modo è possibile creare un elemento con contenuto complesso.</span><span class="sxs-lookup"><span data-stu-id="526b0-111">This enables you to create an element that has complex content.</span></span>  
  
-   <span data-ttu-id="526b0-112">Se un oggetto implementa <xref:System.Collections.Generic.IEnumerable%601>, la raccolta nell'oggetto viene enumerata e vengono aggiunti tutti gli elementi nella raccolta.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="526b0-112">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="526b0-113">Se la raccolta contiene <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XAttribute>oggetti, ogni elemento nella raccolta viene aggiunto separatamente.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="526b0-113">If the collection contains <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="526b0-114">Questo è importante perché consente di passare i risultati di una [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query al costruttore.</span><span class="sxs-lookup"><span data-stu-id="526b0-114">This is important because it lets you pass the results of a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query to the constructor.</span></span>  
  
 <span data-ttu-id="526b0-115">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="526b0-115">The following is an example:</span></span>  
  
 <span data-ttu-id="526b0-116">Queste funzionalità consentono di scrivere codice utilizzando i valori letterali XML per creare una struttura ad albero XML, nonché di scrivere codice che utilizza i risultati di [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] esegue una query quando si crea una struttura ad albero XML:</span><span class="sxs-lookup"><span data-stu-id="526b0-116">These features enable you to write code using XML literals to create an XML tree, and also to write code that uses the results of [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries when you create an XML tree:</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where CInt(el) > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 <span data-ttu-id="526b0-117">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="526b0-117">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="526b0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="526b0-118">See Also</span></span>  
 [<span data-ttu-id="526b0-119">Creazione di strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="526b0-119">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)

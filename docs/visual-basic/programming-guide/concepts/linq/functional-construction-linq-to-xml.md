---
title: Costruzione funzionale (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: feac4273-39ab-43ae-bab7-4059c807a785
ms.openlocfilehash: f42cd6f31134c5f4c7d6a75f38997b2be0c317f3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398064"
---
# <a name="functional-construction-linq-to-xml-visual-basic"></a><span data-ttu-id="b876f-102">Costruzione funzionale (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b876f-102">Functional Construction (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="b876f-103">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è disponibile una potente funzionalità per la creazione di elementi XML, denominata *costruzione funzionale*.</span><span class="sxs-lookup"><span data-stu-id="b876f-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides a powerful way to create XML elements called *functional construction*.</span></span> <span data-ttu-id="b876f-104">Per costruzione funzionale si intende la possibilità di creare una struttura ad albero XML in un'unica istruzione.</span><span class="sxs-lookup"><span data-stu-id="b876f-104">Functional construction is the ability to create an XML tree in a single statement.</span></span>  
  
 <span data-ttu-id="b876f-105">Diverse funzionalità importanti dell'interfaccia di programmazione [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consentono la costruzione funzionale:</span><span class="sxs-lookup"><span data-stu-id="b876f-105">There are several key features of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface that enable functional construction:</span></span>  
  
- <span data-ttu-id="b876f-106">Il costruttore <xref:System.Xml.Linq.XElement> accetta vari tipi di argomenti come contenuto.</span><span class="sxs-lookup"><span data-stu-id="b876f-106">The <xref:System.Xml.Linq.XElement> constructor takes various types of arguments for content.</span></span> <span data-ttu-id="b876f-107">Ad esempio, è possibile passare un altro oggetto <xref:System.Xml.Linq.XElement>, che diventa un elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="b876f-107">For example, you can pass another <xref:System.Xml.Linq.XElement> object, which becomes a child element.</span></span> <span data-ttu-id="b876f-108">È possibile passare un oggetto <xref:System.Xml.Linq.XAttribute>, che diventa un attributo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="b876f-108">You can pass an <xref:System.Xml.Linq.XAttribute> object, which becomes an attribute of the element.</span></span> <span data-ttu-id="b876f-109">Oppure è possibile passare qualsiasi altro tipo di oggetto, che viene convertito in una stringa e diventa il contenuto di testo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="b876f-109">Or you can pass any other type of object, which is converted to a string and becomes the text content of the element.</span></span>  
  
- <span data-ttu-id="b876f-110">Il costruttore <xref:System.Xml.Linq.XElement> accetta una matrice `params` di tipo <xref:System.Object>, quindi è possibile passare qualsiasi numero di oggetti.</span><span class="sxs-lookup"><span data-stu-id="b876f-110">The <xref:System.Xml.Linq.XElement> constructor takes a `params` array of type <xref:System.Object>, so that you can pass any number of objects to the constructor.</span></span> <span data-ttu-id="b876f-111">In questo modo è possibile creare un elemento con contenuto complesso.</span><span class="sxs-lookup"><span data-stu-id="b876f-111">This enables you to create an element that has complex content.</span></span>  
  
- <span data-ttu-id="b876f-112">Se un oggetto implementa <xref:System.Collections.Generic.IEnumerable%601>, la raccolta nell'oggetto viene enumerata e vengono aggiunti tutti gli elementi della raccolta.</span><span class="sxs-lookup"><span data-stu-id="b876f-112">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="b876f-113">Se la raccolta contiene oggetti <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>, ogni elemento della raccolta viene aggiunto separatamente.</span><span class="sxs-lookup"><span data-stu-id="b876f-113">If the collection contains <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="b876f-114">Questo è importante perché consente di passare i risultati di una query LINQ al costruttore.</span><span class="sxs-lookup"><span data-stu-id="b876f-114">This is important because it lets you pass the results of a LINQ query to the constructor.</span></span>  
  
 <span data-ttu-id="b876f-115">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="b876f-115">The following is an example:</span></span>  
  
 <span data-ttu-id="b876f-116">Queste funzionalità consentono di scrivere codice usando valori letterali XML per creare un albero XML e anche di scrivere codice che usa i risultati delle query LINQ quando si crea un albero XML:</span><span class="sxs-lookup"><span data-stu-id="b876f-116">These features enable you to write code using XML literals to create an XML tree, and also to write code that uses the results of LINQ queries when you create an XML tree:</span></span>  
  
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
  
 <span data-ttu-id="b876f-117">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="b876f-117">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b876f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b876f-118">See also</span></span>

- [<span data-ttu-id="b876f-119">Creazione di strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b876f-119">Creating XML Trees (Visual Basic)</span></span>](creating-xml-trees.md)

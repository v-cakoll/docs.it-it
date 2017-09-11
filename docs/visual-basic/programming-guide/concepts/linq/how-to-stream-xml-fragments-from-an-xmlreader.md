---
title: 'Procedura: flusso di frammenti XML da un XmlReader (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: f67ce598-4a12-4dcb-9a07-24deca02a111
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c9c60bb4730ef6569390f76f63c40a2cbd1c9524
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-visual-basic"></a><span data-ttu-id="6e10e-102">Procedura: flusso di frammenti XML da un XmlReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e10e-102">How to: Stream XML Fragments from an XmlReader (Visual Basic)</span></span>
<span data-ttu-id="6e10e-103">Quando è necessario elaborare file XML di grandi dimensioni, potrebbe risultare impossibile caricare in memoria l'intero albero XML.</span><span class="sxs-lookup"><span data-stu-id="6e10e-103">When you have to process large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="6e10e-104">Questo argomento viene illustrato come eseguire il flusso di frammenti tramite un <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="6e10e-104">This topic shows how to stream fragments using an <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="6e10e-105">Uno dei modi più efficaci per usare un <xref:System.Xml.XmlReader>leggere <xref:System.Xml.Linq.XElement>oggetti consiste nello scrivere un metodo dell'asse personalizzato.</xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="6e10e-105">One of the most effective ways to use an <xref:System.Xml.XmlReader> to read <xref:System.Xml.Linq.XElement> objects is to write your own custom axis method.</span></span> <span data-ttu-id="6e10e-106">Un metodo dell'asse restituisce in genere una raccolta, ad esempio <xref:System.Collections.Generic.IEnumerable%601>di <xref:System.Xml.Linq.XElement>, come illustrato nell'esempio di questo argomento.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="6e10e-106">An axis method typically returns a collection such as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, as shown in the example in this topic.</span></span> <span data-ttu-id="6e10e-107">Nel metodo dell'asse personalizzato, dopo aver creato il frammento XML chiamando il <xref:System.Xml.Linq.XNode.ReadFrom%2A>metodo, restituire la raccolta usando `yield return`.</xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="6e10e-107">In the custom axis method, after you create the XML fragment by calling the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method, return the collection using `yield return`.</span></span> <span data-ttu-id="6e10e-108">In questo modo si fornisce la semantica di esecuzione posticipata al metodo dell'asse personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6e10e-108">This provides deferred execution semantics to your custom axis method.</span></span>  
  
 <span data-ttu-id="6e10e-109">Quando si crea un albero XML da un <xref:System.Xml.XmlReader>oggetto, il <xref:System.Xml.XmlReader>deve essere posizionato su un elemento.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="6e10e-109">When you create an XML tree from an <xref:System.Xml.XmlReader> object, the <xref:System.Xml.XmlReader> must be positioned on an element.</span></span> <span data-ttu-id="6e10e-110">Il <xref:System.Xml.Linq.XNode.ReadFrom%2A>metodo non restituisce fino a quando non letto il tag di chiusura dell'elemento.</xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="6e10e-110">The <xref:System.Xml.Linq.XNode.ReadFrom%2A> method does not return until it has read the close tag of the element.</span></span>  
  
 <span data-ttu-id="6e10e-111">Se si desidera creare un albero parziale, è possibile creare un'istanza di un <xref:System.Xml.XmlReader>, posizionare il lettore sul nodo che si desidera convertire in un <xref:System.Xml.Linq.XElement>struttura ad albero e quindi creare il <xref:System.Xml.Linq.XElement>oggetto.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="6e10e-111">If you want to create a partial tree, you can instantiate an <xref:System.Xml.XmlReader>, position the reader on the node that you want to convert to an <xref:System.Xml.Linq.XElement> tree, and then create the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
 <span data-ttu-id="6e10e-112">L'argomento [procedura: flusso di frammenti XML con accesso a informazioni di intestazione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) contiene informazioni e un esempio su come trasmettere un documento più complesso.</span><span class="sxs-lookup"><span data-stu-id="6e10e-112">The topic [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) contains information and an example on how to stream a more complex document.</span></span>  
  
 <span data-ttu-id="6e10e-113">L'argomento [procedura: eseguire lo Streaming Transform di grandi dimensioni documenti XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) contiene un esempio dell'utilizzo di LINQ to XML per trasformare documenti XML molto grandi mantenendo un footprint di memoria di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="6e10e-113">The topic [How to: Perform Streaming Transform of Large XML Documents (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) contains an example of using LINQ to XML to transform extremely large XML documents while maintaining a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e10e-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e10e-114">Example</span></span>  
 <span data-ttu-id="6e10e-115">In questo esempio viene creato un metodo dell'asse personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6e10e-115">This example creates a custom axis method.</span></span> <span data-ttu-id="6e10e-116">È possibile sottoporlo a query tramite una query [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e10e-116">You can query it by using a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query.</span></span> <span data-ttu-id="6e10e-117">Il metodo dell'asse personalizzato `StreamRootChildDoc` è progettato specificamente per leggere un documento contenente un elemento `Child` ripetuto.</span><span class="sxs-lookup"><span data-stu-id="6e10e-117">The custom axis method, `StreamRootChildDoc`, is a method that is designed specifically to read a document that has a repeating `Child` element.</span></span>  
  
<span data-ttu-id="6e10e-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="6e10e-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="6e10e-119">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="6e10e-119">This example produces the following output:</span></span>  
  
<span data-ttu-id="6e10e-120"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="6e10e-120"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="6e10e-121">In questo esempio il documento di origine è molto piccolo.</span><span class="sxs-lookup"><span data-stu-id="6e10e-121">In this example, the source document is very small.</span></span> <span data-ttu-id="6e10e-122">Tuttavia, anche contenesse milioni di elementi `Child`, il footprint di memoria di questo esempio sarebbe comunque ridotto.</span><span class="sxs-lookup"><span data-stu-id="6e10e-122">However, even if there were millions of `Child` elements, this example would still have a small memory footprint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e10e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e10e-123">See Also</span></span>  
 <span data-ttu-id="6e10e-124">[Procedura dettagliata: Implementazione di IEnumerable(Of T) in Visual Basic](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md) </span><span class="sxs-lookup"><span data-stu-id="6e10e-124">[Walkthrough: Implementing IEnumerable(Of T) in Visual Basic](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md) </span></span>  
<span data-ttu-id="6e10e-125"> [Analisi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)</span><span class="sxs-lookup"><span data-stu-id="6e10e-125"> [Parsing XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)</span></span>

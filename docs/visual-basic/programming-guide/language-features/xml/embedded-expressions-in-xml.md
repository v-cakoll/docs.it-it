---
title: Espressioni incorporate in XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: 525fa04db86a299d88e1612aac76d014f35124eb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922626"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="6cff8-102">Espressioni incorporate in XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6cff8-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="6cff8-103">Le espressioni incorporate consentono di creare valori letterali XML contenenti espressioni che vengono valutate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6cff8-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="6cff8-104">La sintassi per un'espressione incorporata `<%=` è `expression` `%>`, che corrisponde alla sintassi utilizzata in ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6cff8-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in ASP.NET.</span></span>  
  
 <span data-ttu-id="6cff8-105">È ad esempio possibile creare un valore letterale elemento XML, combinando espressioni incorporate con contenuto di testo letterale.</span><span class="sxs-lookup"><span data-stu-id="6cff8-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 <span data-ttu-id="6cff8-106">Se `isbnNumber` contiene l'intero 12345 e `modifiedDate` contiene la data 3/5/2006, quando viene eseguito questo codice, il valore di `book` è:</span><span class="sxs-lookup"><span data-stu-id="6cff8-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="6cff8-107">Posizione e convalida dell'espressione incorporata</span><span class="sxs-lookup"><span data-stu-id="6cff8-107">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="6cff8-108">Le espressioni incorporate possono essere visualizzate solo in determinate posizioni all'interno di espressioni letterali XML.</span><span class="sxs-lookup"><span data-stu-id="6cff8-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="6cff8-109">Il percorso dell'espressione controlla i tipi che l'espressione può restituire `Nothing` e il modo in cui viene gestito.</span><span class="sxs-lookup"><span data-stu-id="6cff8-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="6cff8-110">Nella tabella seguente vengono descritti i percorsi e i tipi di espressioni incorporate consentiti.</span><span class="sxs-lookup"><span data-stu-id="6cff8-110">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="6cff8-111">Posizione nel valore letterale</span><span class="sxs-lookup"><span data-stu-id="6cff8-111">Location in literal</span></span>|<span data-ttu-id="6cff8-112">Tipo di espressione</span><span class="sxs-lookup"><span data-stu-id="6cff8-112">Type of expression</span></span>|<span data-ttu-id="6cff8-113">Gestione di`Nothing`</span><span class="sxs-lookup"><span data-stu-id="6cff8-113">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="6cff8-114">Nome elemento XML</span><span class="sxs-lookup"><span data-stu-id="6cff8-114">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="6cff8-115">Errore</span><span class="sxs-lookup"><span data-stu-id="6cff8-115">Error</span></span>|  
|<span data-ttu-id="6cff8-116">Contenuto elemento XML</span><span class="sxs-lookup"><span data-stu-id="6cff8-116">XML element content</span></span>|<span data-ttu-id="6cff8-117">`Object`o matrice di`Object`</span><span class="sxs-lookup"><span data-stu-id="6cff8-117">`Object` or array of `Object`</span></span>|<span data-ttu-id="6cff8-118">Ignorato</span><span class="sxs-lookup"><span data-stu-id="6cff8-118">Ignored</span></span>|  
|<span data-ttu-id="6cff8-119">Nome attributo elemento XML</span><span class="sxs-lookup"><span data-stu-id="6cff8-119">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="6cff8-120">Errore, a meno che anche il valore dell'attributo non sia`Nothing`</span><span class="sxs-lookup"><span data-stu-id="6cff8-120">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="6cff8-121">Valore dell'attributo dell'elemento XML</span><span class="sxs-lookup"><span data-stu-id="6cff8-121">XML element attribute value</span></span>|`Object`|<span data-ttu-id="6cff8-122">Dichiarazione di attributo ignorata</span><span class="sxs-lookup"><span data-stu-id="6cff8-122">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="6cff8-123">Attributo elemento XML</span><span class="sxs-lookup"><span data-stu-id="6cff8-123">XML element attribute</span></span>|<span data-ttu-id="6cff8-124"><xref:System.Xml.Linq.XAttribute>o una raccolta di<xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="6cff8-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="6cff8-125">Ignorato</span><span class="sxs-lookup"><span data-stu-id="6cff8-125">Ignored</span></span>|  
|<span data-ttu-id="6cff8-126">Elemento radice del documento XML</span><span class="sxs-lookup"><span data-stu-id="6cff8-126">XML document root element</span></span>|<span data-ttu-id="6cff8-127"><xref:System.Xml.Linq.XElement>o una raccolta di <xref:System.Xml.Linq.XElement> un oggetto e un numero arbitrario di <xref:System.Xml.Linq.XProcessingInstruction> oggetti e <xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="6cff8-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="6cff8-128">Ignorato</span><span class="sxs-lookup"><span data-stu-id="6cff8-128">Ignored</span></span>|  
  
- <span data-ttu-id="6cff8-129">Esempio di espressione incorporata in un nome di elemento XML:</span><span class="sxs-lookup"><span data-stu-id="6cff8-129">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- <span data-ttu-id="6cff8-130">Esempio di espressione incorporata nel contenuto di un elemento XML:</span><span class="sxs-lookup"><span data-stu-id="6cff8-130">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- <span data-ttu-id="6cff8-131">Esempio di espressione incorporata in un nome di attributo dell'elemento XML:</span><span class="sxs-lookup"><span data-stu-id="6cff8-131">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- <span data-ttu-id="6cff8-132">Esempio di espressione incorporata in un valore di attributo dell'elemento XML:</span><span class="sxs-lookup"><span data-stu-id="6cff8-132">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- <span data-ttu-id="6cff8-133">Esempio di espressione incorporata in un attributo dell'elemento XML:</span><span class="sxs-lookup"><span data-stu-id="6cff8-133">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- <span data-ttu-id="6cff8-134">Esempio di espressione incorporata in un elemento radice di un documento XML:</span><span class="sxs-lookup"><span data-stu-id="6cff8-134">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 <span data-ttu-id="6cff8-135">Se si abilita `Option Strict`, il compilatore verifica che il tipo di ogni espressione incorporata venga ampliato al tipo richiesto.</span><span class="sxs-lookup"><span data-stu-id="6cff8-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="6cff8-136">L'unica eccezione riguarda l'elemento radice di un documento XML, che viene verificato quando viene eseguito il codice.</span><span class="sxs-lookup"><span data-stu-id="6cff8-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="6cff8-137">Se si compila senza `Option Strict`, è possibile incorporare espressioni di `Object` tipo e il relativo tipo viene verificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6cff8-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="6cff8-138">Nelle posizioni in cui il contenuto è facoltativo, le espressioni `Nothing` incorporate che contengono vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="6cff8-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="6cff8-139">Ciò significa che non è necessario verificare che il contenuto dell'elemento, i valori di attributo e gli elementi `Nothing` della matrice non siano prima di usare un valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="6cff8-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="6cff8-140">I valori obbligatori, ad esempio i nomi degli elementi e `Nothing`degli attributi, non possono essere.</span><span class="sxs-lookup"><span data-stu-id="6cff8-140">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="6cff8-141">Per ulteriori informazioni sull'utilizzo di un'espressione incorporata in un particolare tipo di valore letterale, vedere valore letterale [documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [valore letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="6cff8-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="6cff8-142">Regole di ambito</span><span class="sxs-lookup"><span data-stu-id="6cff8-142">Scoping Rules</span></span>  
 <span data-ttu-id="6cff8-143">Il compilatore converte ogni valore letterale XML in una chiamata del costruttore per il tipo di valore letterale appropriato.</span><span class="sxs-lookup"><span data-stu-id="6cff8-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="6cff8-144">Il contenuto letterale e le espressioni incorporate in un valore letterale XML vengono passati come argomenti al costruttore.</span><span class="sxs-lookup"><span data-stu-id="6cff8-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="6cff8-145">Ciò significa che tutte le Visual Basic gli elementi di programmazione disponibili per un valore letterale XML sono disponibili anche per le espressioni incorporate.</span><span class="sxs-lookup"><span data-stu-id="6cff8-145">This means that all Visual Basic programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="6cff8-146">All'interno di un valore letterale XML è possibile accedere ai prefissi degli spazi `Imports` dei nomi XML dichiarati con l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="6cff8-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="6cff8-147">È possibile dichiarare un nuovo prefisso dello spazio dei nomi XML o ombreggiare un prefisso dello spazio dei nomi XML esistente in `xmlns` un elemento usando l'attributo.</span><span class="sxs-lookup"><span data-stu-id="6cff8-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="6cff8-148">Il nuovo spazio dei nomi è disponibile per i nodi figlio dell'elemento, ma non per i valori letterali XML nelle espressioni incorporate.</span><span class="sxs-lookup"><span data-stu-id="6cff8-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6cff8-149">Quando si dichiara un prefisso dello spazio dei nomi XML `xmlns` usando l'attributo Namespace, il valore dell'attributo deve essere una stringa costante.</span><span class="sxs-lookup"><span data-stu-id="6cff8-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="6cff8-150">In questo senso, l'utilizzo `xmlns` dell'attributo è simile all' `Imports` utilizzo dell'istruzione per dichiarare uno spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="6cff8-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="6cff8-151">Non è possibile usare un'espressione incorporata per specificare il valore dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="6cff8-151">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cff8-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cff8-152">See also</span></span>

- [<span data-ttu-id="6cff8-153">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6cff8-153">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="6cff8-154">Valore letterale di documento XML</span><span class="sxs-lookup"><span data-stu-id="6cff8-154">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="6cff8-155">Valore letterale elemento XML</span><span class="sxs-lookup"><span data-stu-id="6cff8-155">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="6cff8-156">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="6cff8-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="6cff8-157">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="6cff8-157">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="6cff8-158">Cenni preliminari sui valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="6cff8-158">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)

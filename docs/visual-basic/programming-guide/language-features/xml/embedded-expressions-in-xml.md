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
ms.openlocfilehash: f99735df2512fd4b1477bab9126e18f5afbbfa8c
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932929"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="8b061-102">Espressioni incorporate in XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b061-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="8b061-103">Le espressioni incorporate consentono di creare valori letterali XML che contengono espressioni valutate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8b061-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="8b061-104">Sintassi dell'espressione incorporata `<%=` `expression` `%>`, che è la stessa sintassi utilizzata [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b061-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span></span>  
  
 <span data-ttu-id="8b061-105">Ad esempio, è possibile creare un elemento XML letterale, se si combinano espressioni incorporate con contenuto di testo letterale.</span><span class="sxs-lookup"><span data-stu-id="8b061-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]  
  
 <span data-ttu-id="8b061-106">Se `isbnNumber` contiene l'intero 12345 e `modifiedDate` contiene la data 3 o 5/2006, quando viene eseguito questo codice, il valore di `book` è:</span><span class="sxs-lookup"><span data-stu-id="8b061-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="8b061-107">Convalida e la posizione di espressione incorporata</span><span class="sxs-lookup"><span data-stu-id="8b061-107">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="8b061-108">Le espressioni incorporate possono apparire solo in alcune posizioni all'interno di espressioni letterali XML.</span><span class="sxs-lookup"><span data-stu-id="8b061-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="8b061-109">Può restituire la posizione nell'espressione controlla quali tipi di espressione e in che modo `Nothing` viene gestita.</span><span class="sxs-lookup"><span data-stu-id="8b061-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="8b061-110">Nella tabella seguente descrive le posizioni consentite e tipi di espressioni incorporate.</span><span class="sxs-lookup"><span data-stu-id="8b061-110">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="8b061-111">Posizione nel valore letterale</span><span class="sxs-lookup"><span data-stu-id="8b061-111">Location in literal</span></span>|<span data-ttu-id="8b061-112">Tipo di espressione</span><span class="sxs-lookup"><span data-stu-id="8b061-112">Type of expression</span></span>|<span data-ttu-id="8b061-113">È possibile gestire `Nothing`</span><span class="sxs-lookup"><span data-stu-id="8b061-113">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="8b061-114">Nome dell'elemento XML</span><span class="sxs-lookup"><span data-stu-id="8b061-114">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="8b061-115">Error</span><span class="sxs-lookup"><span data-stu-id="8b061-115">Error</span></span>|  
|<span data-ttu-id="8b061-116">Contenuto dell'elemento XML</span><span class="sxs-lookup"><span data-stu-id="8b061-116">XML element content</span></span>|<span data-ttu-id="8b061-117">`Object` o una matrice di `Object`</span><span class="sxs-lookup"><span data-stu-id="8b061-117">`Object` or array of `Object`</span></span>|<span data-ttu-id="8b061-118">Ignorato</span><span class="sxs-lookup"><span data-stu-id="8b061-118">Ignored</span></span>|  
|<span data-ttu-id="8b061-119">Nome attributo dell'elemento XML</span><span class="sxs-lookup"><span data-stu-id="8b061-119">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="8b061-120">Errore, a meno che non è anche il valore dell'attributo `Nothing`</span><span class="sxs-lookup"><span data-stu-id="8b061-120">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="8b061-121">Valore di attributo dell'elemento XML</span><span class="sxs-lookup"><span data-stu-id="8b061-121">XML element attribute value</span></span>|`Object`|<span data-ttu-id="8b061-122">Dichiarazione di attributo ignorato</span><span class="sxs-lookup"><span data-stu-id="8b061-122">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="8b061-123">Attributo dell'elemento XML</span><span class="sxs-lookup"><span data-stu-id="8b061-123">XML element attribute</span></span>|<span data-ttu-id="8b061-124"><xref:System.Xml.Linq.XAttribute> oppure una raccolta di <xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="8b061-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="8b061-125">Ignorato</span><span class="sxs-lookup"><span data-stu-id="8b061-125">Ignored</span></span>|  
|<span data-ttu-id="8b061-126">Elemento radice del documento XML</span><span class="sxs-lookup"><span data-stu-id="8b061-126">XML document root element</span></span>|<span data-ttu-id="8b061-127"><xref:System.Xml.Linq.XElement> o una raccolta di uno <xref:System.Xml.Linq.XElement> oggetto e un numero arbitrario di <xref:System.Xml.Linq.XProcessingInstruction> e <xref:System.Xml.Linq.XComment> oggetti</span><span class="sxs-lookup"><span data-stu-id="8b061-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="8b061-128">Ignorato</span><span class="sxs-lookup"><span data-stu-id="8b061-128">Ignored</span></span>|  
  
-   <span data-ttu-id="8b061-129">Esempio di un'espressione incorporata in un nome di elemento XML:</span><span class="sxs-lookup"><span data-stu-id="8b061-129">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]  
  
-   <span data-ttu-id="8b061-130">Esempio di un'espressione incorporata nel contenuto di un elemento XML:</span><span class="sxs-lookup"><span data-stu-id="8b061-130">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]  
  
-   <span data-ttu-id="8b061-131">Esempio di un'espressione incorporata in un nome di attributo dell'elemento XML:</span><span class="sxs-lookup"><span data-stu-id="8b061-131">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]  
  
-   <span data-ttu-id="8b061-132">Esempio di un'espressione incorporata in un valore attributo dell'elemento XML:</span><span class="sxs-lookup"><span data-stu-id="8b061-132">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]  
  
-   <span data-ttu-id="8b061-133">Esempio di un'espressione incorporata in un attributo dell'elemento XML:</span><span class="sxs-lookup"><span data-stu-id="8b061-133">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]  
  
-   <span data-ttu-id="8b061-134">Esempio di un'espressione incorporata in un elemento radice del documento XML:</span><span class="sxs-lookup"><span data-stu-id="8b061-134">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]  
  
 <span data-ttu-id="8b061-135">Se si abilita `Option Strict`, il compilatore controlla che il tipo di ogni espressione incorporata può ampliarsi nel tipo richiesto.</span><span class="sxs-lookup"><span data-stu-id="8b061-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="8b061-136">L'unica eccezione è per l'elemento radice di un documento XML, che viene verificato durante l'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="8b061-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="8b061-137">Se esegue la compilazione senza `Option Strict`, è possibile incorporare le espressioni di tipo `Object` e il tipo viene verificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8b061-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="8b061-138">In località in cui il contenuto è facoltativo, che contengono espressioni incorporate `Nothing` vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="8b061-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="8b061-139">Ciò significa che non è necessario controllare il contenuto dell'elemento, i valori di attributo, e gli elementi della matrice non sono `Nothing` prima di usare un valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="8b061-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="8b061-140">Necessari valori, ad esempio nomi di elementi e attributi, non possono essere `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="8b061-140">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="8b061-141">Per altre informazioni sull'uso di un'espressione incorporata in un particolare tipo di valore letterale, vedere [letterale di documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="8b061-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="8b061-142">Regole di ambito</span><span class="sxs-lookup"><span data-stu-id="8b061-142">Scoping Rules</span></span>  
 <span data-ttu-id="8b061-143">Il compilatore converte ogni valore letterale XML in una chiamata al costruttore per il tipo di valore letterale appropriato.</span><span class="sxs-lookup"><span data-stu-id="8b061-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="8b061-144">Il contenuto letterale ed espressioni incorporate in un valore letterale XML vengono passate come argomenti al costruttore.</span><span class="sxs-lookup"><span data-stu-id="8b061-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="8b061-145">Ciò significa che tutti i Visual Basic elementi di programmazione disponibili per un valore letterale XML sono inoltre disponibili per le espressioni incorporate.</span><span class="sxs-lookup"><span data-stu-id="8b061-145">This means that all Visual Basic programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="8b061-146">All'interno di un valore letterale XML, è possibile accedere lo spazio dei nomi XML prefissi dichiarati con la `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="8b061-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="8b061-147">È possibile dichiarare un nuovo prefisso dello spazio dei nomi XML oppure nascondere un prefisso dello spazio dei nomi XML esistente, in un elemento usando la `xmlns` attributo.</span><span class="sxs-lookup"><span data-stu-id="8b061-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="8b061-148">Il nuovo spazio dei nomi è disponibile per i nodi figlio di quell'elemento, ma non per i valori letterali XML in espressioni incorporate.</span><span class="sxs-lookup"><span data-stu-id="8b061-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b061-149">Quando si dichiara un prefisso dello spazio dei nomi XML usando la `xmlns` namespace (attributo), il valore dell'attributo deve essere una stringa costante.</span><span class="sxs-lookup"><span data-stu-id="8b061-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="8b061-150">A questo proposito, utilizzando il `xmlns` attributo è simile all'utilizzo di `Imports` dichiarare uno spazio dei nomi XML dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="8b061-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="8b061-151">È possibile usare un'espressione incorporata per specificare il valore dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="8b061-151">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b061-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b061-152">See Also</span></span>  
 [<span data-ttu-id="8b061-153">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8b061-153">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="8b061-154">Valore letterale di documento XML</span><span class="sxs-lookup"><span data-stu-id="8b061-154">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [<span data-ttu-id="8b061-155">Valore letterale elemento XML</span><span class="sxs-lookup"><span data-stu-id="8b061-155">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="8b061-156">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="8b061-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="8b061-157">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="8b061-157">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="8b061-158">Cenni preliminari sui valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="8b061-158">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)

---
title: Le espressioni incorporate in XML (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.XmlEmbeddedExpression
dev_langs:
- VB
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d24a49f2fa6fd66fe6e4c7724bd4298d65fb7a59
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="69135-102">Espressioni incorporate in XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69135-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="69135-103">Espressioni incorporate consentono di creare valori letterali XML che contengono espressioni vengono valutate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="69135-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="69135-104">La sintassi per un'espressione incorporata è `<%=` `expression` `%>`, che è la stessa sintassi utilizzata in [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].</span><span class="sxs-lookup"><span data-stu-id="69135-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].</span></span>  
  
 <span data-ttu-id="69135-105">Ad esempio, è possibile creare un elemento XML letterale, la combinazione di espressioni incorporate con contenuto di testo letterale.</span><span class="sxs-lookup"><span data-stu-id="69135-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 <span data-ttu-id="69135-106">[!code-vb[VbXMLSamples&#27;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="69135-106">[!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]</span></span>  
  
 <span data-ttu-id="69135-107">Se `isbnNumber` contiene il valore integer 12345 e `modifiedDate` contiene la data 3/5/2006, quando viene eseguito questo codice, il valore di `book` è:</span><span class="sxs-lookup"><span data-stu-id="69135-107">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="69135-108">Convalida e la posizione di espressione incorporata</span><span class="sxs-lookup"><span data-stu-id="69135-108">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="69135-109">Espressioni incorporate possono apparire solo in determinate posizioni all'interno di espressioni letterali XML.</span><span class="sxs-lookup"><span data-stu-id="69135-109">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="69135-110">Può restituire la posizione nell'espressione controlla quali tipi di espressione e come `Nothing` viene gestita.</span><span class="sxs-lookup"><span data-stu-id="69135-110">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="69135-111">Nella tabella seguente vengono descritti i percorsi consentiti e i tipi di espressioni incorporate.</span><span class="sxs-lookup"><span data-stu-id="69135-111">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="69135-112">Posizione nel valore letterale</span><span class="sxs-lookup"><span data-stu-id="69135-112">Location in literal</span></span>|<span data-ttu-id="69135-113">Tipo di espressione</span><span class="sxs-lookup"><span data-stu-id="69135-113">Type of expression</span></span>|<span data-ttu-id="69135-114">Gestione di`Nothing`</span><span class="sxs-lookup"><span data-stu-id="69135-114">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="69135-115">Nome dell'elemento XML</span><span class="sxs-lookup"><span data-stu-id="69135-115">XML element name</span></span>|<span data-ttu-id="69135-116"><xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="69135-116"><xref:System.Xml.Linq.XName></span></span>|<span data-ttu-id="69135-117">Errore</span><span class="sxs-lookup"><span data-stu-id="69135-117">Error</span></span>|  
|<span data-ttu-id="69135-118">Contenuto dell'elemento XML</span><span class="sxs-lookup"><span data-stu-id="69135-118">XML element content</span></span>|<span data-ttu-id="69135-119">`Object`o una matrice di`Object`</span><span class="sxs-lookup"><span data-stu-id="69135-119">`Object` or array of `Object`</span></span>|<span data-ttu-id="69135-120">Ignorato</span><span class="sxs-lookup"><span data-stu-id="69135-120">Ignored</span></span>|  
|<span data-ttu-id="69135-121">Nome di attributo dell'elemento XML</span><span class="sxs-lookup"><span data-stu-id="69135-121">XML element attribute name</span></span>|<span data-ttu-id="69135-122"><xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="69135-122"><xref:System.Xml.Linq.XName></span></span>|<span data-ttu-id="69135-123">L'errore, a meno che non è il valore dell'attributo`Nothing`</span><span class="sxs-lookup"><span data-stu-id="69135-123">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="69135-124">Valore di attributo dell'elemento XML</span><span class="sxs-lookup"><span data-stu-id="69135-124">XML element attribute value</span></span>|`Object`|<span data-ttu-id="69135-125">Dichiarazione di attributo ignorata.</span><span class="sxs-lookup"><span data-stu-id="69135-125">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="69135-126">Attributo dell'elemento XML</span><span class="sxs-lookup"><span data-stu-id="69135-126">XML element attribute</span></span>|<span data-ttu-id="69135-127"><xref:System.Xml.Linq.XAttribute>o una raccolta di<xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="69135-127"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="69135-128">Ignorato</span><span class="sxs-lookup"><span data-stu-id="69135-128">Ignored</span></span>|  
|<span data-ttu-id="69135-129">Elemento radice del documento XML</span><span class="sxs-lookup"><span data-stu-id="69135-129">XML document root element</span></span>|<span data-ttu-id="69135-130"><xref:System.Xml.Linq.XElement>o una raccolta di un <xref:System.Xml.Linq.XElement>oggetto e un numero arbitrario di <xref:System.Xml.Linq.XProcessingInstruction> <xref:System.Xml.Linq.XComment>oggetti</xref:System.Xml.Linq.XComment> e</xref:System.Xml.Linq.XProcessingInstruction> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="69135-130"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="69135-131">Ignorato</span><span class="sxs-lookup"><span data-stu-id="69135-131">Ignored</span></span>|  
  
-   <span data-ttu-id="69135-132">Esempio di un'espressione incorporata in un nome di elemento XML:</span><span class="sxs-lookup"><span data-stu-id="69135-132">Example of an embedded expression in an XML element name:</span></span>  
  
     <span data-ttu-id="69135-133">[!code-vb[VbXMLSamples n.&32;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="69135-133">[!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]</span></span>  
  
-   <span data-ttu-id="69135-134">Esempio di un'espressione incorporata nel contenuto di un elemento XML:</span><span class="sxs-lookup"><span data-stu-id="69135-134">Example of an embedded expression in the content of an XML element:</span></span>  
  
     <span data-ttu-id="69135-135">[!code-vb[VbXMLSamples n.&33;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="69135-135">[!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]</span></span>  
  
-   <span data-ttu-id="69135-136">Esempio di un'espressione incorporata in un nome di attributo dell'elemento XML:</span><span class="sxs-lookup"><span data-stu-id="69135-136">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     <span data-ttu-id="69135-137">[!code-vb[VbXMLSamples&#34;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="69135-137">[!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]</span></span>  
  
-   <span data-ttu-id="69135-138">Esempio di un'espressione incorporata in un valore di attributo di elemento XML:</span><span class="sxs-lookup"><span data-stu-id="69135-138">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     <span data-ttu-id="69135-139">[!code-vb[VbXMLSamples&#35;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="69135-139">[!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]</span></span>  
  
-   <span data-ttu-id="69135-140">Esempio di un'espressione incorporata in un attributo dell'elemento XML:</span><span class="sxs-lookup"><span data-stu-id="69135-140">Example of an embedded expression in an XML element attribute:</span></span>  
  
     <span data-ttu-id="69135-141">[!code-vb[VbXMLSamples&#36;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="69135-141">[!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]</span></span>  
  
-   <span data-ttu-id="69135-142">Esempio di un'espressione incorporata in un elemento radice del documento XML:</span><span class="sxs-lookup"><span data-stu-id="69135-142">Example of an embedded expression in an XML document root element:</span></span>  
  
     <span data-ttu-id="69135-143">[!code-vb[VbXMLSamples&#37;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="69135-143">[!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]</span></span>  
  
 <span data-ttu-id="69135-144">Se si abilita `Option Strict`, il compilatore controlla che il tipo di ogni espressione incorporata può ampliarsi nel tipo richiesto.</span><span class="sxs-lookup"><span data-stu-id="69135-144">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="69135-145">L'unica eccezione è per l'elemento radice di un documento XML, che viene verificato durante l'esecuzione di codice.</span><span class="sxs-lookup"><span data-stu-id="69135-145">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="69135-146">Se esegue la compilazione senza `Option Strict`, è possibile incorporare espressioni di tipo `Object` e il tipo viene verificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="69135-146">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="69135-147">Nelle posizioni in cui il contenuto facoltativo, le espressioni incorporate che contengono `Nothing` vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="69135-147">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="69135-148">Questo significa che non è necessario controllare il contenuto dell'elemento, i valori di attributo, e non sono elementi di matrice `Nothing` prima di utilizzare un valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="69135-148">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="69135-149">Richiesta non possono essere valori, ad esempio nomi di elementi e attributi, `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="69135-149">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="69135-150">Per ulteriori informazioni sull'utilizzo di un'espressione incorporata in un determinato tipo di valore letterale, vedere [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="69135-150">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="69135-151">Regole di ambito</span><span class="sxs-lookup"><span data-stu-id="69135-151">Scoping Rules</span></span>  
 <span data-ttu-id="69135-152">Il compilatore converte ogni valore letterale XML in una chiamata al costruttore per il tipo di valore letterale appropriato.</span><span class="sxs-lookup"><span data-stu-id="69135-152">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="69135-153">Il contenuto effettivo ed espressioni incorporate in un valore letterale XML vengono passate come argomenti al costruttore.</span><span class="sxs-lookup"><span data-stu-id="69135-153">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="69135-154">Ciò significa che tutti [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] elementi di programmazione disponibili per un valore letterale XML sono inoltre disponibili per le espressioni incorporate.</span><span class="sxs-lookup"><span data-stu-id="69135-154">This means that all [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="69135-155">All'interno di un valore letterale XML, è possibile accedere lo spazio dei nomi XML prefissi dichiarati con la `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="69135-155">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="69135-156">È possibile dichiarare un nuovo prefisso dello spazio dei nomi XML o nascondere un prefisso dello spazio dei nomi XML esistente, in un elemento utilizzando il `xmlns` attributo.</span><span class="sxs-lookup"><span data-stu-id="69135-156">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="69135-157">Il nuovo spazio dei nomi è disponibile per i nodi figlio di tale elemento, ma non a valori letterali XML in espressioni incorporate.</span><span class="sxs-lookup"><span data-stu-id="69135-157">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69135-158">Quando si dichiara un prefisso dello spazio dei nomi XML utilizzando il `xmlns` attributo dello spazio dei nomi, il valore dell'attributo deve essere una stringa costante.</span><span class="sxs-lookup"><span data-stu-id="69135-158">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="69135-159">In questo caso, l'utilizzo di `xmlns` attributo è simile all'utilizzo di `Imports` istruzione per dichiarare uno spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="69135-159">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="69135-160">È possibile utilizzare un'espressione incorporata per specificare il valore dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="69135-160">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69135-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69135-161">See Also</span></span>  
 <span data-ttu-id="69135-162">[Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="69135-162">[Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="69135-163"> [Valore letterale documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span><span class="sxs-lookup"><span data-stu-id="69135-163"> [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span></span>  
<span data-ttu-id="69135-164"> [Valore letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="69135-164"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="69135-165"> [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="69135-165"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="69135-166"> [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="69135-166"> [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="69135-167"> [Cenni preliminari sui valori letterali XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)</span><span class="sxs-lookup"><span data-stu-id="69135-167"> [XML Literals Overview](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)</span></span>

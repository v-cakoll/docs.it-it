---
title: Valore letterale elemento XML (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
caps.latest.revision: "32"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: de5825a6af1dd1b93c3c85651125cf817dc564f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="a2071-102">Valore letterale elemento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2071-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="a2071-103">Un valore letterale che rappresenta un <xref:System.Xml.Linq.XElement> oggetto.</span><span class="sxs-lookup"><span data-stu-id="a2071-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2071-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2071-104">Syntax</span></span>  
  
```xml  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a><span data-ttu-id="a2071-105">Parti</span><span class="sxs-lookup"><span data-stu-id="a2071-105">Parts</span></span>  
  
-   `<`  
  
     <span data-ttu-id="a2071-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a2071-106">Required.</span></span> <span data-ttu-id="a2071-107">Apre il tag iniziale dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="a2071-107">Opens the starting element tag.</span></span>  
  
-   `name`  
  
     <span data-ttu-id="a2071-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a2071-108">Required.</span></span> <span data-ttu-id="a2071-109">Nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="a2071-109">Name of the element.</span></span> <span data-ttu-id="a2071-110">Il formato è uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2071-110">The format is one of the following:</span></span>  
  
    -   <span data-ttu-id="a2071-111">Testo letterale per il nome dell'elemento del form `[ePrefix:]eName`, dove:</span><span class="sxs-lookup"><span data-stu-id="a2071-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>  
  
        |<span data-ttu-id="a2071-112">Parte</span><span class="sxs-lookup"><span data-stu-id="a2071-112">Part</span></span>|<span data-ttu-id="a2071-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2071-113">Description</span></span>|  
        |---|---|  
        |`ePrefix`|<span data-ttu-id="a2071-114">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a2071-114">Optional.</span></span> <span data-ttu-id="a2071-115">Prefisso dello spazio dei nomi XML per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="a2071-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="a2071-116">Deve essere uno spazio dei nomi XML globale definito con un `Imports` istruzione nel file o a livello di progetto, o uno spazio dei nomi XML locale definito in questo elemento o un elemento padre.</span><span class="sxs-lookup"><span data-stu-id="a2071-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`eName`|<span data-ttu-id="a2071-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a2071-117">Required.</span></span> <span data-ttu-id="a2071-118">Nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="a2071-118">Name of the element.</span></span> <span data-ttu-id="a2071-119">Il formato è uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2071-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="a2071-120">-Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="a2071-120">-   Literal text.</span></span> <span data-ttu-id="a2071-121">Vedere [i nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="a2071-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="a2071-122">-Espressione incorporata del formato `<%= eNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="a2071-122">-   Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="a2071-123">Il tipo di `eNameExp` deve essere `String` o un tipo convertibile in modo implicito per <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="a2071-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
  
    -   <span data-ttu-id="a2071-124">Espressione incorporata del formato `<%= nameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="a2071-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="a2071-125">Il tipo di `nameExp` deve essere `String` o un tipo convertibile in modo implicito <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="a2071-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="a2071-126">Un'espressione incorporata non è consentita in un tag di chiusura di un elemento.</span><span class="sxs-lookup"><span data-stu-id="a2071-126">An embedded expression is not allowed in a closing tag of an element.</span></span>  
  
-   `attributeList`  
  
     <span data-ttu-id="a2071-127">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a2071-127">Optional.</span></span> <span data-ttu-id="a2071-128">Elenco di attributi dichiarati nel valore letterale.</span><span class="sxs-lookup"><span data-stu-id="a2071-128">List of attributes declared in the literal.</span></span>  
  
     `attribute [ attribute ... ]`  
  
     <span data-ttu-id="a2071-129">Ogni `attribute` ha una delle sintassi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2071-129">Each `attribute` has one of the following syntaxes:</span></span>  
  
    -   <span data-ttu-id="a2071-130">Attributo di assegnazione, nel formato `[aPrefix:]aName=aValue`, dove:</span><span class="sxs-lookup"><span data-stu-id="a2071-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>  
  
        |<span data-ttu-id="a2071-131">Parte</span><span class="sxs-lookup"><span data-stu-id="a2071-131">Part</span></span>|<span data-ttu-id="a2071-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2071-132">Description</span></span>|  
        |---|---|  
        |`aPrefix`|<span data-ttu-id="a2071-133">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a2071-133">Optional.</span></span> <span data-ttu-id="a2071-134">Prefisso dello spazio dei nomi XML per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="a2071-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="a2071-135">Deve essere uno spazio dei nomi XML globale definito con un `Imports` istruzione o uno spazio dei nomi XML locale definito in questo elemento o un elemento padre.</span><span class="sxs-lookup"><span data-stu-id="a2071-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`aName`|<span data-ttu-id="a2071-136">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a2071-136">Required.</span></span> <span data-ttu-id="a2071-137">Nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="a2071-137">Name of the attribute.</span></span> <span data-ttu-id="a2071-138">Il formato è uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2071-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="a2071-139">-Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="a2071-139">-   Literal text.</span></span> <span data-ttu-id="a2071-140">Vedere [i nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="a2071-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="a2071-141">-Espressione incorporata del formato `<%= aNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="a2071-141">-   Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="a2071-142">Il tipo di `aNameExp` deve essere `String` o un tipo convertibile in modo implicito per <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="a2071-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
        |`aValue`|<span data-ttu-id="a2071-143">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a2071-143">Optional.</span></span> <span data-ttu-id="a2071-144">Valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="a2071-144">Value of the attribute.</span></span> <span data-ttu-id="a2071-145">Il formato è uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2071-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="a2071-146">-Testo letterale, racchiuso tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="a2071-146">-   Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="a2071-147">-Espressione incorporata del formato `<%= aValueExp %>`.</span><span class="sxs-lookup"><span data-stu-id="a2071-147">-   Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="a2071-148">È consentito qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="a2071-148">Any type is allowed.</span></span>|  
  
    -   <span data-ttu-id="a2071-149">Espressione incorporata del formato `<%= aExp %>`.</span><span class="sxs-lookup"><span data-stu-id="a2071-149">Embedded expression of the form `<%= aExp %>`.</span></span>  
  
-   `/>`  
  
     <span data-ttu-id="a2071-150">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a2071-150">Optional.</span></span> <span data-ttu-id="a2071-151">Indica che l'elemento è un elemento vuoto, senza contenuto.</span><span class="sxs-lookup"><span data-stu-id="a2071-151">Indicates that the element is an empty element, without content.</span></span>  
  
-   `>`  
  
     <span data-ttu-id="a2071-152">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a2071-152">Required.</span></span> <span data-ttu-id="a2071-153">Termina il tag dell'elemento iniziale o vuoto.</span><span class="sxs-lookup"><span data-stu-id="a2071-153">Ends the beginning or empty element tag.</span></span>  
  
-   `elementContents`  
  
     <span data-ttu-id="a2071-154">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a2071-154">Optional.</span></span> <span data-ttu-id="a2071-155">Contenuto dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="a2071-155">Content of the element.</span></span>  
  
     `content [ content ... ]`  
  
     <span data-ttu-id="a2071-156">Ogni `content` può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2071-156">Each `content` can be one of the following:</span></span>  
  
    -   <span data-ttu-id="a2071-157">Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="a2071-157">Literal text.</span></span> <span data-ttu-id="a2071-158">Tutti gli spazi vuoti in `elementContents` diventano significativi se è presente del testo letterale.</span><span class="sxs-lookup"><span data-stu-id="a2071-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>  
  
    -   <span data-ttu-id="a2071-159">Espressione incorporata del formato `<%= contentExp %>`.</span><span class="sxs-lookup"><span data-stu-id="a2071-159">Embedded expression of the form `<%= contentExp %>`.</span></span>  
  
    -   <span data-ttu-id="a2071-160">Valore letterale elemento XML.</span><span class="sxs-lookup"><span data-stu-id="a2071-160">XML element literal.</span></span>  
  
    -   <span data-ttu-id="a2071-161">Valore letterale di commento XML.</span><span class="sxs-lookup"><span data-stu-id="a2071-161">XML comment literal.</span></span> <span data-ttu-id="a2071-162">Vedere [valore letterale di commento XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="a2071-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>  
  
    -   <span data-ttu-id="a2071-163">Istruzione di elaborazione XML.</span><span class="sxs-lookup"><span data-stu-id="a2071-163">XML processing instruction literal.</span></span> <span data-ttu-id="a2071-164">Vedere [valore letterale istruzione di elaborazione XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="a2071-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>  
  
    -   <span data-ttu-id="a2071-165">Valore letterale CDATA XML.</span><span class="sxs-lookup"><span data-stu-id="a2071-165">XML CDATA literal.</span></span> <span data-ttu-id="a2071-166">Vedere [valore letterale CDATA XML](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="a2071-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>  
  
-   `</[name]>`  
  
     <span data-ttu-id="a2071-167">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a2071-167">Optional.</span></span> <span data-ttu-id="a2071-168">Rappresenta il tag di chiusura per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="a2071-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="a2071-169">Facoltativo `name` parametro non è consentito quando è il risultato di un'espressione incorporata.</span><span class="sxs-lookup"><span data-stu-id="a2071-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2071-170">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a2071-170">Return Value</span></span>  
 <span data-ttu-id="a2071-171">Oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="a2071-171">An <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2071-172">Note</span><span class="sxs-lookup"><span data-stu-id="a2071-172">Remarks</span></span>  
 <span data-ttu-id="a2071-173">È possibile utilizzare la sintassi del valore letterale elemento XML per creare <xref:System.Xml.Linq.XElement> oggetti nel codice.</span><span class="sxs-lookup"><span data-stu-id="a2071-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2071-174">Un valore letterale XML può estendersi su più righe senza utilizzare caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="a2071-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="a2071-175">Questa funzionalità consente di copiare il contenuto da un documento XML e incollarlo direttamente in un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programma.</span><span class="sxs-lookup"><span data-stu-id="a2071-175">This feature enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 <span data-ttu-id="a2071-176">Le espressioni incorporate il formato `<%= exp %>` consentono di aggiungere informazioni dinamiche a un valore letterale elemento XML.</span><span class="sxs-lookup"><span data-stu-id="a2071-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="a2071-177">Per ulteriori informazioni, vedere [espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a2071-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="a2071-178">Il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore converte il valore letterale elemento XML in chiamate al <xref:System.Xml.Linq.XElement.%23ctor%2A> costruttore e, se necessario, il <xref:System.Xml.Linq.XAttribute.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="a2071-178">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="a2071-179">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="a2071-179">XML Namespaces</span></span>  
 <span data-ttu-id="a2071-180">Prefissi di spazio dei nomi XML sono utili quando è necessario creare valori letterali XML con elementi dallo spazio dei nomi stesso numero di volte nel codice.</span><span class="sxs-lookup"><span data-stu-id="a2071-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="a2071-181">È possibile utilizzare i prefissi dello spazio dei nomi XML globali, che può essere definito utilizzando il `Imports` istruzione o prefissi locali, che può essere definito utilizzando il `xmlns:xmlPrefix="xmlNamespace"` sintassi degli attributi.</span><span class="sxs-lookup"><span data-stu-id="a2071-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="a2071-182">Per ulteriori informazioni, vedere [istruzione Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="a2071-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
 <span data-ttu-id="a2071-183">In base alle regole di ambito per gli spazi dei nomi XML, i prefissi locali hanno la precedenza sui prefissi globali.</span><span class="sxs-lookup"><span data-stu-id="a2071-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="a2071-184">Tuttavia, se un valore letterale XML definisce uno spazio dei nomi XML, lo spazio dei nomi non è disponibile per le espressioni contenute in un'espressione incorporata.</span><span class="sxs-lookup"><span data-stu-id="a2071-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="a2071-185">L'espressione incorporata può accedere solo nomi XML globale.</span><span class="sxs-lookup"><span data-stu-id="a2071-185">The embedded expression can access only the global XML namespace.</span></span>  
  
 <span data-ttu-id="a2071-186">Il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore converte ogni spazio dei nomi XML globale viene utilizzato un valore letterale XML in una definizione locale dello spazio dei nomi nel codice generato.</span><span class="sxs-lookup"><span data-stu-id="a2071-186">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="a2071-187">Spazi dei nomi XML globali non utilizzati non vengono visualizzati nel codice generato.</span><span class="sxs-lookup"><span data-stu-id="a2071-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2071-188">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2071-188">Example</span></span>  
 <span data-ttu-id="a2071-189">Nell'esempio seguente viene illustrato come creare un elemento XML semplice che dispone di due elementi vuoti nidificati.</span><span class="sxs-lookup"><span data-stu-id="a2071-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>  
  
 [!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]  
  
 <span data-ttu-id="a2071-190">L'esempio mostra il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="a2071-190">The example displays the following text.</span></span> <span data-ttu-id="a2071-191">Si noti che il valore letterale mantiene la struttura degli elementi vuoti.</span><span class="sxs-lookup"><span data-stu-id="a2071-191">Notice that the literal preserves the structure of the empty elements.</span></span>  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a><span data-ttu-id="a2071-192">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2071-192">Example</span></span>  
 <span data-ttu-id="a2071-193">Nell'esempio seguente viene illustrato come utilizzare le espressioni incorporate per nome di un elemento e creare gli attributi.</span><span class="sxs-lookup"><span data-stu-id="a2071-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>  
  
 [!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]  
  
 <span data-ttu-id="a2071-194">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="a2071-194">This code displays the following text:</span></span>  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a><span data-ttu-id="a2071-195">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2071-195">Example</span></span>  
 <span data-ttu-id="a2071-196">Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="a2071-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="a2071-197">Quindi, il prefisso dello spazio dei nomi utilizzato per creare un file XML come valore letterale e consente di visualizzare il formato dell'elemento finale.</span><span class="sxs-lookup"><span data-stu-id="a2071-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]  
  
 <span data-ttu-id="a2071-198">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="a2071-198">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="a2071-199">Si noti che il compilatore converte il prefisso dello spazio dei nomi XML globali in una definizione del prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="a2071-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="a2071-200">Il \<ns:middle > elemento consente di ridefinire il prefisso dello spazio dei nomi XML per il \<ns:inner1 > elemento.</span><span class="sxs-lookup"><span data-stu-id="a2071-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="a2071-201">Tuttavia, il \<ns:inner2 > elemento Usa lo spazio dei nomi definito dal `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="a2071-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2071-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2071-202">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="a2071-203">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="a2071-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [<span data-ttu-id="a2071-204">Valore letterale di commento XML</span><span class="sxs-lookup"><span data-stu-id="a2071-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [<span data-ttu-id="a2071-205">Valore letterale CDATA XML</span><span class="sxs-lookup"><span data-stu-id="a2071-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)  
 [<span data-ttu-id="a2071-206">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="a2071-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="a2071-207">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a2071-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="a2071-208">Espressioni incorporate in XML</span><span class="sxs-lookup"><span data-stu-id="a2071-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [<span data-ttu-id="a2071-209">Istruzione Imports (spazio dei nomi XML)</span><span class="sxs-lookup"><span data-stu-id="a2071-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)

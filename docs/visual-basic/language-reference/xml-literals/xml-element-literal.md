---
title: Valore letterale elemento XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: 54ad162a1a720a1645a3b413e6518d2ccfd37bbe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595916"
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="4480e-102">Valore letterale elemento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4480e-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="4480e-103">Un valore letterale che rappresenta un <xref:System.Xml.Linq.XElement> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4480e-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4480e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4480e-104">Syntax</span></span>  
  
```xml  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a><span data-ttu-id="4480e-105">Parti</span><span class="sxs-lookup"><span data-stu-id="4480e-105">Parts</span></span>  
  
-   `<`  
  
     <span data-ttu-id="4480e-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4480e-106">Required.</span></span> <span data-ttu-id="4480e-107">Apre il tag dell'elemento iniziale.</span><span class="sxs-lookup"><span data-stu-id="4480e-107">Opens the starting element tag.</span></span>  
  
-   `name`  
  
     <span data-ttu-id="4480e-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4480e-108">Required.</span></span> <span data-ttu-id="4480e-109">Nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="4480e-109">Name of the element.</span></span> <span data-ttu-id="4480e-110">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="4480e-110">The format is one of the following:</span></span>  
  
    -   <span data-ttu-id="4480e-111">Testo letterale per il nome dell'elemento, nel formato `[ePrefix:]eName`, dove:</span><span class="sxs-lookup"><span data-stu-id="4480e-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>  
  
        |<span data-ttu-id="4480e-112">Parte</span><span class="sxs-lookup"><span data-stu-id="4480e-112">Part</span></span>|<span data-ttu-id="4480e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4480e-113">Description</span></span>|  
        |---|---|  
        |`ePrefix`|<span data-ttu-id="4480e-114">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4480e-114">Optional.</span></span> <span data-ttu-id="4480e-115">Prefisso dello spazio dei nomi XML per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="4480e-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="4480e-116">Deve essere uno spazio dei nomi XML globale definito con un `Imports` istruzione nel file o a livello di progetto, o uno spazio dei nomi XML locale definito in questo elemento o un elemento padre.</span><span class="sxs-lookup"><span data-stu-id="4480e-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`eName`|<span data-ttu-id="4480e-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4480e-117">Required.</span></span> <span data-ttu-id="4480e-118">Nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="4480e-118">Name of the element.</span></span> <span data-ttu-id="4480e-119">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="4480e-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="4480e-120">-Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="4480e-120">-   Literal text.</span></span> <span data-ttu-id="4480e-121">Visualizzare [nomi degli elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="4480e-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="4480e-122">-Espressione incorporata del form `<%= eNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="4480e-122">-   Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="4480e-123">Il tipo della `eNameExp` deve essere `String` o un tipo che è implicitamente convertibile in <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="4480e-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
  
    -   <span data-ttu-id="4480e-124">Espressione del form incorporata `<%= nameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="4480e-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="4480e-125">Il tipo della `nameExp` deve essere `String` o un tipo implicitamente convertibile in <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="4480e-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="4480e-126">Un'espressione incorporata non è consentita in un tag di chiusura di un elemento.</span><span class="sxs-lookup"><span data-stu-id="4480e-126">An embedded expression is not allowed in a closing tag of an element.</span></span>  
  
-   `attributeList`  
  
     <span data-ttu-id="4480e-127">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4480e-127">Optional.</span></span> <span data-ttu-id="4480e-128">Elenco degli attributi dichiarate nel valore letterale.</span><span class="sxs-lookup"><span data-stu-id="4480e-128">List of attributes declared in the literal.</span></span>  
  
     `attribute [ attribute ... ]`  
  
     <span data-ttu-id="4480e-129">Ogni `attribute` dispone di una delle sintassi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4480e-129">Each `attribute` has one of the following syntaxes:</span></span>  
  
    -   <span data-ttu-id="4480e-130">Assegnazione, nel formato attributo `[aPrefix:]aName=aValue`, dove:</span><span class="sxs-lookup"><span data-stu-id="4480e-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>  
  
        |<span data-ttu-id="4480e-131">Parte</span><span class="sxs-lookup"><span data-stu-id="4480e-131">Part</span></span>|<span data-ttu-id="4480e-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4480e-132">Description</span></span>|  
        |---|---|  
        |`aPrefix`|<span data-ttu-id="4480e-133">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4480e-133">Optional.</span></span> <span data-ttu-id="4480e-134">Prefisso dello spazio dei nomi XML per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="4480e-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="4480e-135">Deve essere uno spazio dei nomi XML globale definito con un `Imports` istruzione o uno spazio dei nomi XML locale definito in questo elemento o un elemento padre.</span><span class="sxs-lookup"><span data-stu-id="4480e-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`aName`|<span data-ttu-id="4480e-136">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4480e-136">Required.</span></span> <span data-ttu-id="4480e-137">Nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="4480e-137">Name of the attribute.</span></span> <span data-ttu-id="4480e-138">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="4480e-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="4480e-139">-Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="4480e-139">-   Literal text.</span></span> <span data-ttu-id="4480e-140">Visualizzare [nomi degli elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="4480e-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="4480e-141">-Espressione incorporata del form `<%= aNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="4480e-141">-   Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="4480e-142">Il tipo della `aNameExp` deve essere `String` o un tipo che è implicitamente convertibile in <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="4480e-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
        |`aValue`|<span data-ttu-id="4480e-143">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4480e-143">Optional.</span></span> <span data-ttu-id="4480e-144">Valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="4480e-144">Value of the attribute.</span></span> <span data-ttu-id="4480e-145">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="4480e-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="4480e-146">-Testo letterale, racchiuso tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="4480e-146">-   Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="4480e-147">-Espressione incorporata del form `<%= aValueExp %>`.</span><span class="sxs-lookup"><span data-stu-id="4480e-147">-   Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="4480e-148">È consentito qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="4480e-148">Any type is allowed.</span></span>|  
  
    -   <span data-ttu-id="4480e-149">Espressione del form incorporata `<%= aExp %>`.</span><span class="sxs-lookup"><span data-stu-id="4480e-149">Embedded expression of the form `<%= aExp %>`.</span></span>  
  
-   `/>`  
  
     <span data-ttu-id="4480e-150">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4480e-150">Optional.</span></span> <span data-ttu-id="4480e-151">Indica che l'elemento è un elemento vuoto, senza contenuto.</span><span class="sxs-lookup"><span data-stu-id="4480e-151">Indicates that the element is an empty element, without content.</span></span>  
  
-   `>`  
  
     <span data-ttu-id="4480e-152">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4480e-152">Required.</span></span> <span data-ttu-id="4480e-153">Termina il tag dell'elemento iniziale o vuoto.</span><span class="sxs-lookup"><span data-stu-id="4480e-153">Ends the beginning or empty element tag.</span></span>  
  
-   `elementContents`  
  
     <span data-ttu-id="4480e-154">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4480e-154">Optional.</span></span> <span data-ttu-id="4480e-155">Contenuto dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="4480e-155">Content of the element.</span></span>  
  
     `content [ content ... ]`  
  
     <span data-ttu-id="4480e-156">Ogni `content` può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="4480e-156">Each `content` can be one of the following:</span></span>  
  
    -   <span data-ttu-id="4480e-157">Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="4480e-157">Literal text.</span></span> <span data-ttu-id="4480e-158">Tutti gli spazi vuoti in `elementContents` diventa significativo se è presente del testo letterale.</span><span class="sxs-lookup"><span data-stu-id="4480e-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>  
  
    -   <span data-ttu-id="4480e-159">Espressione del form incorporata `<%= contentExp %>`.</span><span class="sxs-lookup"><span data-stu-id="4480e-159">Embedded expression of the form `<%= contentExp %>`.</span></span>  
  
    -   <span data-ttu-id="4480e-160">Valore letterale elemento XML.</span><span class="sxs-lookup"><span data-stu-id="4480e-160">XML element literal.</span></span>  
  
    -   <span data-ttu-id="4480e-161">Valore letterale di commento XML.</span><span class="sxs-lookup"><span data-stu-id="4480e-161">XML comment literal.</span></span> <span data-ttu-id="4480e-162">Visualizzare [valore letterale commento XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="4480e-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>  
  
    -   <span data-ttu-id="4480e-163">Istruzione di elaborazione XML.</span><span class="sxs-lookup"><span data-stu-id="4480e-163">XML processing instruction literal.</span></span> <span data-ttu-id="4480e-164">Visualizzare [valore letterale istruzione di elaborazione XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="4480e-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>  
  
    -   <span data-ttu-id="4480e-165">Valore letterale CDATA XML.</span><span class="sxs-lookup"><span data-stu-id="4480e-165">XML CDATA literal.</span></span> <span data-ttu-id="4480e-166">Visualizzare [valore letterale CDATA XML](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="4480e-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>  
  
-   `</[name]>`  
  
     <span data-ttu-id="4480e-167">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4480e-167">Optional.</span></span> <span data-ttu-id="4480e-168">Rappresenta il tag di chiusura per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="4480e-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="4480e-169">L'opzione facoltativa `name` parametro non è consentito quando è il risultato di un'espressione incorporata.</span><span class="sxs-lookup"><span data-stu-id="4480e-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4480e-170">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4480e-170">Return Value</span></span>  
 <span data-ttu-id="4480e-171">Oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="4480e-171">An <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4480e-172">Note</span><span class="sxs-lookup"><span data-stu-id="4480e-172">Remarks</span></span>  
 <span data-ttu-id="4480e-173">È possibile usare la sintassi del valore letterale elemento XML per creare <xref:System.Xml.Linq.XElement> gli oggetti nel codice.</span><span class="sxs-lookup"><span data-stu-id="4480e-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4480e-174">Un valore letterale XML può estendersi su più righe senza utilizzare caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="4480e-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="4480e-175">Questa funzionalità consente di copiare il contenuto da un documento XML e incollare il codice direttamente in un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4480e-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="4480e-176">Espressioni nel formato incorporate `<%= exp %>` consentono di aggiungere informazioni dinamiche a un valore letterale elemento XML.</span><span class="sxs-lookup"><span data-stu-id="4480e-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="4480e-177">Per altre informazioni, vedere [espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4480e-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="4480e-178">Il compilatore Visual Basic converte il valore letterale elemento XML in chiamate per il <xref:System.Xml.Linq.XElement.%23ctor%2A> costruttore e, se necessario, il <xref:System.Xml.Linq.XAttribute.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="4480e-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="4480e-179">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="4480e-179">XML Namespaces</span></span>  
 <span data-ttu-id="4480e-180">I prefissi dello spazio dei nomi XML sono utili quando è necessario creare valori letterali XML con gli elementi dallo spazio dei nomi stesso numero di volte nel codice.</span><span class="sxs-lookup"><span data-stu-id="4480e-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="4480e-181">È possibile usare i prefissi dello spazio dei nomi XML globali, che può essere definito usando la `Imports` istruzione o i prefissi locali, che può essere definito usando la `xmlns:xmlPrefix="xmlNamespace"` sintassi degli attributi.</span><span class="sxs-lookup"><span data-stu-id="4480e-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="4480e-182">Per altre informazioni, vedere [istruzione Imports (Namespace XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="4480e-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
 <span data-ttu-id="4480e-183">In conformità con le regole di ambito per gli spazi dei nomi XML, i prefissi locali hanno la precedenza sui prefissi globali.</span><span class="sxs-lookup"><span data-stu-id="4480e-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="4480e-184">Tuttavia, se un valore letterale XML definisce uno spazio dei nomi XML, tale spazio dei nomi non è disponibile per le espressioni contenute in un'espressione incorporata.</span><span class="sxs-lookup"><span data-stu-id="4480e-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="4480e-185">L'espressione incorporata può accedere solo i nomi XML globale.</span><span class="sxs-lookup"><span data-stu-id="4480e-185">The embedded expression can access only the global XML namespace.</span></span>  
  
 <span data-ttu-id="4480e-186">Il compilatore Visual Basic consente di convertire ogni spazio dei nomi XML globale che viene usato da un valore letterale XML in una definizione dello spazio dei nomi locali nel codice generato.</span><span class="sxs-lookup"><span data-stu-id="4480e-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="4480e-187">Spazi dei nomi XML globali non utilizzati non vengono visualizzati nel codice generato.</span><span class="sxs-lookup"><span data-stu-id="4480e-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4480e-188">Esempio</span><span class="sxs-lookup"><span data-stu-id="4480e-188">Example</span></span>  
 <span data-ttu-id="4480e-189">Nell'esempio seguente viene illustrato come creare un elemento XML semplice che dispone di due elementi vuoti annidati.</span><span class="sxs-lookup"><span data-stu-id="4480e-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>  
  
 [!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]  
  
 <span data-ttu-id="4480e-190">L'esempio visualizza il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="4480e-190">The example displays the following text.</span></span> <span data-ttu-id="4480e-191">Si noti che il valore letterale mantiene la struttura di elementi vuoti.</span><span class="sxs-lookup"><span data-stu-id="4480e-191">Notice that the literal preserves the structure of the empty elements.</span></span>  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a><span data-ttu-id="4480e-192">Esempio</span><span class="sxs-lookup"><span data-stu-id="4480e-192">Example</span></span>  
 <span data-ttu-id="4480e-193">Nell'esempio seguente viene illustrato come usare espressioni incorporate per nome di un elemento e creare gli attributi.</span><span class="sxs-lookup"><span data-stu-id="4480e-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>  
  
 [!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]  
  
 <span data-ttu-id="4480e-194">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="4480e-194">This code displays the following text:</span></span>  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a><span data-ttu-id="4480e-195">Esempio</span><span class="sxs-lookup"><span data-stu-id="4480e-195">Example</span></span>  
 <span data-ttu-id="4480e-196">Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="4480e-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="4480e-197">Quindi Usa il prefisso dello spazio dei nomi per creare un file XML letterale e visualizza il formato dell'elemento finale.</span><span class="sxs-lookup"><span data-stu-id="4480e-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]  
  
 <span data-ttu-id="4480e-198">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="4480e-198">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="4480e-199">Si noti che il compilatore converte il prefisso dello spazio dei nomi XML globali in una definizione del prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="4480e-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="4480e-200">Il \<ns:middle > elemento consente di ridefinire il prefisso dello spazio dei nomi XML per il \<ns:inner1 > elemento.</span><span class="sxs-lookup"><span data-stu-id="4480e-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="4480e-201">Tuttavia, il \<ns:inner2 > elemento utilizza lo spazio dei nomi definito dal `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4480e-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4480e-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4480e-202">See also</span></span>
- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="4480e-203">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="4480e-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="4480e-204">Valore letterale di commento XML</span><span class="sxs-lookup"><span data-stu-id="4480e-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="4480e-205">Valore letterale CDATA XML</span><span class="sxs-lookup"><span data-stu-id="4480e-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [<span data-ttu-id="4480e-206">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="4480e-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="4480e-207">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4480e-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="4480e-208">Espressioni incorporate in XML</span><span class="sxs-lookup"><span data-stu-id="4480e-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="4480e-209">Istruzione Imports (spazio dei nomi XML)</span><span class="sxs-lookup"><span data-stu-id="4480e-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)

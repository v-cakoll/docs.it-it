---
title: Valore letterale elemento XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: d6d900ca6868cfffe6b0e5b349321a79c5716c46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347034"
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="0613b-102">Valore letterale elemento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0613b-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="0613b-103">Valore letterale che rappresenta un oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="0613b-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="syntax"></a><span data-ttu-id="0613b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0613b-104">Syntax</span></span>

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a><span data-ttu-id="0613b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="0613b-105">Parts</span></span>

- `<`

  <span data-ttu-id="0613b-106">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="0613b-106">Required.</span></span> <span data-ttu-id="0613b-107">Apre il tag dell'elemento iniziale.</span><span class="sxs-lookup"><span data-stu-id="0613b-107">Opens the starting element tag.</span></span>

- `name`

  <span data-ttu-id="0613b-108">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="0613b-108">Required.</span></span> <span data-ttu-id="0613b-109">Nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="0613b-109">Name of the element.</span></span> <span data-ttu-id="0613b-110">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0613b-110">The format is one of the following:</span></span>

  - <span data-ttu-id="0613b-111">Testo letterale per il nome dell'elemento, nel formato `[ePrefix:]eName`, dove:</span><span class="sxs-lookup"><span data-stu-id="0613b-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>

    |<span data-ttu-id="0613b-112">Parte</span><span class="sxs-lookup"><span data-stu-id="0613b-112">Part</span></span>|<span data-ttu-id="0613b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0613b-113">Description</span></span>|
    |---|---|
    |`ePrefix`|<span data-ttu-id="0613b-114">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0613b-114">Optional.</span></span> <span data-ttu-id="0613b-115">Prefisso dello spazio dei nomi XML per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="0613b-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="0613b-116">Deve essere uno spazio dei nomi XML globale definito con un'istruzione `Imports` nel file o a livello di progetto o uno spazio dei nomi XML locale definito in questo elemento o in un elemento padre.</span><span class="sxs-lookup"><span data-stu-id="0613b-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`eName`|<span data-ttu-id="0613b-117">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="0613b-117">Required.</span></span> <span data-ttu-id="0613b-118">Nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="0613b-118">Name of the element.</span></span> <span data-ttu-id="0613b-119">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0613b-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="0613b-120">-Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="0613b-120">- Literal text.</span></span> <span data-ttu-id="0613b-121">Vedere [nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="0613b-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="0613b-122">-Espressione incorporata del form `<%= eNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="0613b-122">- Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="0613b-123">Il tipo di `eNameExp` deve essere `String` o un tipo convertibile in modo implicito in <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="0613b-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|

  - <span data-ttu-id="0613b-124">Espressione incorporata del form `<%= nameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="0613b-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="0613b-125">Il tipo di `nameExp` deve essere `String` o un tipo convertibile in modo implicito in <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="0613b-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="0613b-126">Espressione incorporata non consentita in un tag di chiusura di un elemento.</span><span class="sxs-lookup"><span data-stu-id="0613b-126">An embedded expression is not allowed in a closing tag of an element.</span></span>

- `attributeList`

  <span data-ttu-id="0613b-127">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0613b-127">Optional.</span></span> <span data-ttu-id="0613b-128">Elenco di attributi dichiarati nel valore letterale.</span><span class="sxs-lookup"><span data-stu-id="0613b-128">List of attributes declared in the literal.</span></span>

  `attribute [ attribute ... ]`

  <span data-ttu-id="0613b-129">Ogni `attribute` ha una delle seguenti sintassi:</span><span class="sxs-lookup"><span data-stu-id="0613b-129">Each `attribute` has one of the following syntaxes:</span></span>

  - <span data-ttu-id="0613b-130">Assegnazione di attributi, nel formato `[aPrefix:]aName=aValue`, dove:</span><span class="sxs-lookup"><span data-stu-id="0613b-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>

    |<span data-ttu-id="0613b-131">Parte</span><span class="sxs-lookup"><span data-stu-id="0613b-131">Part</span></span>|<span data-ttu-id="0613b-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0613b-132">Description</span></span>|
    |---|---|
    |`aPrefix`|<span data-ttu-id="0613b-133">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0613b-133">Optional.</span></span> <span data-ttu-id="0613b-134">Prefisso dello spazio dei nomi XML per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="0613b-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="0613b-135">Deve essere uno spazio dei nomi XML globale definito con un'istruzione `Imports` o uno spazio dei nomi XML locale definito in questo elemento o in un elemento padre.</span><span class="sxs-lookup"><span data-stu-id="0613b-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`aName`|<span data-ttu-id="0613b-136">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="0613b-136">Required.</span></span> <span data-ttu-id="0613b-137">Nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="0613b-137">Name of the attribute.</span></span> <span data-ttu-id="0613b-138">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0613b-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="0613b-139">-Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="0613b-139">- Literal text.</span></span> <span data-ttu-id="0613b-140">Vedere [nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="0613b-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="0613b-141">-Espressione incorporata del form `<%= aNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="0613b-141">- Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="0613b-142">Il tipo di `aNameExp` deve essere `String` o un tipo convertibile in modo implicito in <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="0613b-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|
    |`aValue`|<span data-ttu-id="0613b-143">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0613b-143">Optional.</span></span> <span data-ttu-id="0613b-144">Valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="0613b-144">Value of the attribute.</span></span> <span data-ttu-id="0613b-145">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0613b-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="0613b-146">-Testo letterale, racchiuso tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="0613b-146">- Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="0613b-147">-Espressione incorporata del form `<%= aValueExp %>`.</span><span class="sxs-lookup"><span data-stu-id="0613b-147">- Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="0613b-148">Qualsiasi tipo è consentito.</span><span class="sxs-lookup"><span data-stu-id="0613b-148">Any type is allowed.</span></span>|

  - <span data-ttu-id="0613b-149">Espressione incorporata del form `<%= aExp %>`.</span><span class="sxs-lookup"><span data-stu-id="0613b-149">Embedded expression of the form `<%= aExp %>`.</span></span>

- `/>`

  <span data-ttu-id="0613b-150">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0613b-150">Optional.</span></span> <span data-ttu-id="0613b-151">Indica che l'elemento è un elemento vuoto, senza contenuto.</span><span class="sxs-lookup"><span data-stu-id="0613b-151">Indicates that the element is an empty element, without content.</span></span>

- `>`

  <span data-ttu-id="0613b-152">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="0613b-152">Required.</span></span> <span data-ttu-id="0613b-153">Termina il tag dell'elemento iniziale o vuoto.</span><span class="sxs-lookup"><span data-stu-id="0613b-153">Ends the beginning or empty element tag.</span></span>

- `elementContents`

  <span data-ttu-id="0613b-154">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0613b-154">Optional.</span></span> <span data-ttu-id="0613b-155">Contenuto dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="0613b-155">Content of the element.</span></span>

  `content [ content ... ]`

  <span data-ttu-id="0613b-156">Ogni `content` può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0613b-156">Each `content` can be one of the following:</span></span>

  - <span data-ttu-id="0613b-157">Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="0613b-157">Literal text.</span></span> <span data-ttu-id="0613b-158">Tutti gli spazi vuoti in `elementContents` diventano significativi se è presente un testo letterale.</span><span class="sxs-lookup"><span data-stu-id="0613b-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>

  - <span data-ttu-id="0613b-159">Espressione incorporata del form `<%= contentExp %>`.</span><span class="sxs-lookup"><span data-stu-id="0613b-159">Embedded expression of the form `<%= contentExp %>`.</span></span>

  - <span data-ttu-id="0613b-160">Valore letterale elemento XML.</span><span class="sxs-lookup"><span data-stu-id="0613b-160">XML element literal.</span></span>

  - <span data-ttu-id="0613b-161">Valore letterale del commento XML.</span><span class="sxs-lookup"><span data-stu-id="0613b-161">XML comment literal.</span></span> <span data-ttu-id="0613b-162">Vedere [valore letterale del commento XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="0613b-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>

  - <span data-ttu-id="0613b-163">Valore letterale istruzione di elaborazione XML.</span><span class="sxs-lookup"><span data-stu-id="0613b-163">XML processing instruction literal.</span></span> <span data-ttu-id="0613b-164">Vedere [valore letterale istruzione di elaborazione XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="0613b-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>

  - <span data-ttu-id="0613b-165">Valore letterale CDATA XML.</span><span class="sxs-lookup"><span data-stu-id="0613b-165">XML CDATA literal.</span></span> <span data-ttu-id="0613b-166">Vedere [valore letterale CDATA XML](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="0613b-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>

- `</[name]>`

  <span data-ttu-id="0613b-167">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0613b-167">Optional.</span></span> <span data-ttu-id="0613b-168">Rappresenta il tag di chiusura per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="0613b-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="0613b-169">Il parametro facoltativo `name` non è consentito quando è il risultato di un'espressione incorporata.</span><span class="sxs-lookup"><span data-stu-id="0613b-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>

## <a name="return-value"></a><span data-ttu-id="0613b-170">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0613b-170">Return Value</span></span>

<span data-ttu-id="0613b-171">Oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="0613b-171">An <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="remarks"></a><span data-ttu-id="0613b-172">Note</span><span class="sxs-lookup"><span data-stu-id="0613b-172">Remarks</span></span>

<span data-ttu-id="0613b-173">È possibile utilizzare la sintassi dei valori letterali dell'elemento XML per creare <xref:System.Xml.Linq.XElement> oggetti nel codice.</span><span class="sxs-lookup"><span data-stu-id="0613b-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>

> [!NOTE]
> <span data-ttu-id="0613b-174">Un valore letterale XML può estendersi su più righe senza usare caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="0613b-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="0613b-175">Questa funzionalità consente di copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0613b-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>

<span data-ttu-id="0613b-176">Le espressioni incorporate del form `<%= exp %>` consentono di aggiungere informazioni dinamiche a un valore letterale elemento XML.</span><span class="sxs-lookup"><span data-stu-id="0613b-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="0613b-177">Per ulteriori informazioni, vedere [espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0613b-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>

<span data-ttu-id="0613b-178">Il compilatore Visual Basic converte il valore letterale dell'elemento XML in chiamate al costruttore di <xref:System.Xml.Linq.XElement.%23ctor%2A> e, se necessario, il costruttore di <xref:System.Xml.Linq.XAttribute.%23ctor%2A>.</span><span class="sxs-lookup"><span data-stu-id="0613b-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="0613b-179">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="0613b-179">XML Namespaces</span></span>

<span data-ttu-id="0613b-180">I prefissi degli spazi dei nomi XML sono utili quando è necessario creare valori letterali XML con gli elementi dello stesso spazio dei nomi più volte nel codice.</span><span class="sxs-lookup"><span data-stu-id="0613b-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="0613b-181">È possibile utilizzare i prefissi degli spazi dei nomi XML globali, definiti utilizzando l'istruzione `Imports` o i prefissi locali definiti utilizzando la sintassi dell'attributo `xmlns:xmlPrefix="xmlNamespace"`.</span><span class="sxs-lookup"><span data-stu-id="0613b-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="0613b-182">Per altre informazioni, vedere [istruzione Imports (spazio dei nomi XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="0613b-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>

<span data-ttu-id="0613b-183">In conformità alle regole di ambito per gli spazi dei nomi XML, i prefissi locali hanno la precedenza sui prefissi globali.</span><span class="sxs-lookup"><span data-stu-id="0613b-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="0613b-184">Tuttavia, se un valore letterale XML definisce uno spazio dei nomi XML, tale spazio dei nomi non è disponibile per le espressioni visualizzate in un'espressione incorporata.</span><span class="sxs-lookup"><span data-stu-id="0613b-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="0613b-185">L'espressione incorporata può accedere solo allo spazio dei nomi XML globale.</span><span class="sxs-lookup"><span data-stu-id="0613b-185">The embedded expression can access only the global XML namespace.</span></span>

<span data-ttu-id="0613b-186">Il compilatore Visual Basic converte tutti gli spazi dei nomi XML globali utilizzati da un valore letterale XML in una definizione di uno spazio dei nomi locale nel codice generato.</span><span class="sxs-lookup"><span data-stu-id="0613b-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="0613b-187">Gli spazi dei nomi XML globali non utilizzati non vengono visualizzati nel codice generato.</span><span class="sxs-lookup"><span data-stu-id="0613b-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>

## <a name="example"></a><span data-ttu-id="0613b-188">Esempio</span><span class="sxs-lookup"><span data-stu-id="0613b-188">Example</span></span>

<span data-ttu-id="0613b-189">Nell'esempio seguente viene illustrato come creare un elemento XML semplice con due elementi vuoti annidati.</span><span class="sxs-lookup"><span data-stu-id="0613b-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

<span data-ttu-id="0613b-190">Nell'esempio viene visualizzato il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="0613b-190">The example displays the following text.</span></span> <span data-ttu-id="0613b-191">Si noti che il valore letterale conserva la struttura degli elementi vuoti.</span><span class="sxs-lookup"><span data-stu-id="0613b-191">Notice that the literal preserves the structure of the empty elements.</span></span>

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a><span data-ttu-id="0613b-192">Esempio</span><span class="sxs-lookup"><span data-stu-id="0613b-192">Example</span></span>

<span data-ttu-id="0613b-193">Nell'esempio seguente viene illustrato come utilizzare le espressioni incorporate per assegnare un nome a un elemento e creare attributi.</span><span class="sxs-lookup"><span data-stu-id="0613b-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

<span data-ttu-id="0613b-194">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="0613b-194">This code displays the following text:</span></span>

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a><span data-ttu-id="0613b-195">Esempio</span><span class="sxs-lookup"><span data-stu-id="0613b-195">Example</span></span>

<span data-ttu-id="0613b-196">Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="0613b-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="0613b-197">USA quindi il prefisso dello spazio dei nomi per creare un valore letterale XML e visualizza il formato finale dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="0613b-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="0613b-198">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="0613b-198">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="0613b-199">Si noti che il compilatore ha convertito il prefisso dello spazio dei nomi XML globale in una definizione di prefisso per lo spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="0613b-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="0613b-200">L'elemento \<NS: Middle > ridefinisce il prefisso dello spazio dei nomi XML per l'elemento \<NS: inner1 >.</span><span class="sxs-lookup"><span data-stu-id="0613b-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="0613b-201">Tuttavia, l'elemento \<NS: INNER2 > USA lo spazio dei nomi definito dall'istruzione `Imports`.</span><span class="sxs-lookup"><span data-stu-id="0613b-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="0613b-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0613b-202">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="0613b-203">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="0613b-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="0613b-204">Valore letterale di commento XML</span><span class="sxs-lookup"><span data-stu-id="0613b-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="0613b-205">Valore letterale CDATA XML</span><span class="sxs-lookup"><span data-stu-id="0613b-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [<span data-ttu-id="0613b-206">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="0613b-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="0613b-207">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0613b-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="0613b-208">Espressioni incorporate in XML</span><span class="sxs-lookup"><span data-stu-id="0613b-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="0613b-209">Istruzione Imports (spazio dei nomi XML)</span><span class="sxs-lookup"><span data-stu-id="0613b-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)

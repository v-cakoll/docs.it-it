---
title: Valore letterale di elemento XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: d6a91de4e279816bafd29f46bb4f5422cbd934ff
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400189"
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="be79d-102">Valore letterale elemento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be79d-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="be79d-103">Valore letterale che rappresenta un <xref:System.Xml.Linq.XElement> oggetto.</span><span class="sxs-lookup"><span data-stu-id="be79d-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="syntax"></a><span data-ttu-id="be79d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be79d-104">Syntax</span></span>

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a><span data-ttu-id="be79d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="be79d-105">Parts</span></span>

- `<`

  <span data-ttu-id="be79d-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="be79d-106">Required.</span></span> <span data-ttu-id="be79d-107">Apre il tag dell'elemento iniziale.</span><span class="sxs-lookup"><span data-stu-id="be79d-107">Opens the starting element tag.</span></span>

- `name`

  <span data-ttu-id="be79d-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="be79d-108">Required.</span></span> <span data-ttu-id="be79d-109">Nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="be79d-109">Name of the element.</span></span> <span data-ttu-id="be79d-110">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="be79d-110">The format is one of the following:</span></span>

  - <span data-ttu-id="be79d-111">Testo letterale per il nome dell'elemento, nel formato `[ePrefix:]eName` , dove:</span><span class="sxs-lookup"><span data-stu-id="be79d-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>

    |<span data-ttu-id="be79d-112">Parte</span><span class="sxs-lookup"><span data-stu-id="be79d-112">Part</span></span>|<span data-ttu-id="be79d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be79d-113">Description</span></span>|
    |---|---|
    |`ePrefix`|<span data-ttu-id="be79d-114">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="be79d-114">Optional.</span></span> <span data-ttu-id="be79d-115">Prefisso dello spazio dei nomi XML per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="be79d-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="be79d-116">Deve essere uno spazio dei nomi XML globale definito con un' `Imports` istruzione nel file o a livello di progetto o uno spazio dei nomi XML locale definito in questo elemento o in un elemento padre.</span><span class="sxs-lookup"><span data-stu-id="be79d-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`eName`|<span data-ttu-id="be79d-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="be79d-117">Required.</span></span> <span data-ttu-id="be79d-118">Nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="be79d-118">Name of the element.</span></span> <span data-ttu-id="be79d-119">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="be79d-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="be79d-120">-Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="be79d-120">- Literal text.</span></span> <span data-ttu-id="be79d-121">Vedere [nomi di elementi e attributi XML dichiarati](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="be79d-121">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="be79d-122">-Espressione incorporata del form `<%= eNameExp %>` .</span><span class="sxs-lookup"><span data-stu-id="be79d-122">- Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="be79d-123">Il tipo di `eNameExp` deve essere `String` o un tipo convertibile in modo implicito in <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="be79d-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|

  - <span data-ttu-id="be79d-124">Espressione incorporata del form `<%= nameExp %>` .</span><span class="sxs-lookup"><span data-stu-id="be79d-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="be79d-125">Il tipo di `nameExp` deve essere `String` o un tipo convertibile in modo implicito in <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="be79d-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="be79d-126">Espressione incorporata non consentita in un tag di chiusura di un elemento.</span><span class="sxs-lookup"><span data-stu-id="be79d-126">An embedded expression is not allowed in a closing tag of an element.</span></span>

- `attributeList`

  <span data-ttu-id="be79d-127">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="be79d-127">Optional.</span></span> <span data-ttu-id="be79d-128">Elenco di attributi dichiarati nel valore letterale.</span><span class="sxs-lookup"><span data-stu-id="be79d-128">List of attributes declared in the literal.</span></span>

  `attribute [ attribute ... ]`

  <span data-ttu-id="be79d-129">Ogni `attribute` ha una delle seguenti sintassi:</span><span class="sxs-lookup"><span data-stu-id="be79d-129">Each `attribute` has one of the following syntaxes:</span></span>

  - <span data-ttu-id="be79d-130">Assegnazione di attributi, nel formato `[aPrefix:]aName=aValue` , dove:</span><span class="sxs-lookup"><span data-stu-id="be79d-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>

    |<span data-ttu-id="be79d-131">Parte</span><span class="sxs-lookup"><span data-stu-id="be79d-131">Part</span></span>|<span data-ttu-id="be79d-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be79d-132">Description</span></span>|
    |---|---|
    |`aPrefix`|<span data-ttu-id="be79d-133">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="be79d-133">Optional.</span></span> <span data-ttu-id="be79d-134">Prefisso dello spazio dei nomi XML per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="be79d-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="be79d-135">Deve essere uno spazio dei nomi XML globale definito con un' `Imports` istruzione o uno spazio dei nomi XML locale definito in questo elemento o in un elemento padre.</span><span class="sxs-lookup"><span data-stu-id="be79d-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`aName`|<span data-ttu-id="be79d-136">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="be79d-136">Required.</span></span> <span data-ttu-id="be79d-137">Nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="be79d-137">Name of the attribute.</span></span> <span data-ttu-id="be79d-138">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="be79d-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="be79d-139">-Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="be79d-139">- Literal text.</span></span> <span data-ttu-id="be79d-140">Vedere [nomi di elementi e attributi XML dichiarati](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="be79d-140">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="be79d-141">-Espressione incorporata del form `<%= aNameExp %>` .</span><span class="sxs-lookup"><span data-stu-id="be79d-141">- Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="be79d-142">Il tipo di `aNameExp` deve essere `String` o un tipo convertibile in modo implicito in <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="be79d-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|
    |`aValue`|<span data-ttu-id="be79d-143">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="be79d-143">Optional.</span></span> <span data-ttu-id="be79d-144">Valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="be79d-144">Value of the attribute.</span></span> <span data-ttu-id="be79d-145">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="be79d-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="be79d-146">-Testo letterale, racchiuso tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="be79d-146">- Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="be79d-147">-Espressione incorporata del form `<%= aValueExp %>` .</span><span class="sxs-lookup"><span data-stu-id="be79d-147">- Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="be79d-148">Qualsiasi tipo è consentito.</span><span class="sxs-lookup"><span data-stu-id="be79d-148">Any type is allowed.</span></span>|

  - <span data-ttu-id="be79d-149">Espressione incorporata del form `<%= aExp %>` .</span><span class="sxs-lookup"><span data-stu-id="be79d-149">Embedded expression of the form `<%= aExp %>`.</span></span>

- `/>`

  <span data-ttu-id="be79d-150">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="be79d-150">Optional.</span></span> <span data-ttu-id="be79d-151">Indica che l'elemento è un elemento vuoto, senza contenuto.</span><span class="sxs-lookup"><span data-stu-id="be79d-151">Indicates that the element is an empty element, without content.</span></span>

- `>`

  <span data-ttu-id="be79d-152">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="be79d-152">Required.</span></span> <span data-ttu-id="be79d-153">Termina il tag dell'elemento iniziale o vuoto.</span><span class="sxs-lookup"><span data-stu-id="be79d-153">Ends the beginning or empty element tag.</span></span>

- `elementContents`

  <span data-ttu-id="be79d-154">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="be79d-154">Optional.</span></span> <span data-ttu-id="be79d-155">Contenuto dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="be79d-155">Content of the element.</span></span>

  `content [ content ... ]`

  <span data-ttu-id="be79d-156">Ognuno `content` può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="be79d-156">Each `content` can be one of the following:</span></span>

  - <span data-ttu-id="be79d-157">Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="be79d-157">Literal text.</span></span> <span data-ttu-id="be79d-158">Tutti gli spazi vuoti in `elementContents` diventano significativi se è presente un testo letterale.</span><span class="sxs-lookup"><span data-stu-id="be79d-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>

  - <span data-ttu-id="be79d-159">Espressione incorporata del form `<%= contentExp %>` .</span><span class="sxs-lookup"><span data-stu-id="be79d-159">Embedded expression of the form `<%= contentExp %>`.</span></span>

  - <span data-ttu-id="be79d-160">Valore letterale elemento XML.</span><span class="sxs-lookup"><span data-stu-id="be79d-160">XML element literal.</span></span>

  - <span data-ttu-id="be79d-161">Valore letterale del commento XML.</span><span class="sxs-lookup"><span data-stu-id="be79d-161">XML comment literal.</span></span> <span data-ttu-id="be79d-162">Vedere [valore letterale del commento XML](xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="be79d-162">See [XML Comment Literal](xml-comment-literal.md).</span></span>

  - <span data-ttu-id="be79d-163">Valore letterale istruzione di elaborazione XML.</span><span class="sxs-lookup"><span data-stu-id="be79d-163">XML processing instruction literal.</span></span> <span data-ttu-id="be79d-164">Vedere [valore letterale istruzione di elaborazione XML](xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="be79d-164">See [XML Processing Instruction Literal](xml-processing-instruction-literal.md).</span></span>

  - <span data-ttu-id="be79d-165">Valore letterale CDATA XML.</span><span class="sxs-lookup"><span data-stu-id="be79d-165">XML CDATA literal.</span></span> <span data-ttu-id="be79d-166">Vedere [valore letterale CDATA XML](xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="be79d-166">See [XML CDATA Literal](xml-cdata-literal.md).</span></span>

- `</[name]>`

  <span data-ttu-id="be79d-167">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="be79d-167">Optional.</span></span> <span data-ttu-id="be79d-168">Rappresenta il tag di chiusura per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="be79d-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="be79d-169">Il `name` parametro facoltativo non è consentito quando è il risultato di un'espressione incorporata.</span><span class="sxs-lookup"><span data-stu-id="be79d-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>

## <a name="return-value"></a><span data-ttu-id="be79d-170">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="be79d-170">Return Value</span></span>

<span data-ttu-id="be79d-171">Oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="be79d-171">An <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="remarks"></a><span data-ttu-id="be79d-172">Commenti</span><span class="sxs-lookup"><span data-stu-id="be79d-172">Remarks</span></span>

<span data-ttu-id="be79d-173">È possibile utilizzare la sintassi dei valori letterali dell'elemento XML per creare <xref:System.Xml.Linq.XElement> oggetti nel codice.</span><span class="sxs-lookup"><span data-stu-id="be79d-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>

> [!NOTE]
> <span data-ttu-id="be79d-174">Un valore letterale XML può estendersi su più righe senza usare caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="be79d-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="be79d-175">Questa funzionalità consente di copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="be79d-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>

<span data-ttu-id="be79d-176">Le espressioni incorporate del form `<%= exp %>` consentono di aggiungere informazioni dinamiche a un valore letterale elemento XML.</span><span class="sxs-lookup"><span data-stu-id="be79d-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="be79d-177">Per ulteriori informazioni, vedere [espressioni incorporate in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="be79d-177">For more information, see [Embedded Expressions in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>

<span data-ttu-id="be79d-178">Il compilatore Visual Basic converte il valore letterale dell'elemento XML in chiamate al <xref:System.Xml.Linq.XElement.%23ctor%2A> costruttore e, se necessario, il <xref:System.Xml.Linq.XAttribute.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="be79d-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="be79d-179">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="be79d-179">XML Namespaces</span></span>

<span data-ttu-id="be79d-180">I prefissi degli spazi dei nomi XML sono utili quando è necessario creare valori letterali XML con gli elementi dello stesso spazio dei nomi più volte nel codice.</span><span class="sxs-lookup"><span data-stu-id="be79d-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="be79d-181">È possibile utilizzare i prefissi degli spazi dei nomi XML globali, definiti utilizzando l' `Imports` istruzione o prefissi locali, definiti utilizzando la `xmlns:xmlPrefix="xmlNamespace"` sintassi dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="be79d-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="be79d-182">Per altre informazioni, vedere [istruzione Imports (spazio dei nomi XML)](../statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="be79d-182">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>

<span data-ttu-id="be79d-183">In conformità alle regole di ambito per gli spazi dei nomi XML, i prefissi locali hanno la precedenza sui prefissi globali.</span><span class="sxs-lookup"><span data-stu-id="be79d-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="be79d-184">Tuttavia, se un valore letterale XML definisce uno spazio dei nomi XML, tale spazio dei nomi non è disponibile per le espressioni visualizzate in un'espressione incorporata.</span><span class="sxs-lookup"><span data-stu-id="be79d-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="be79d-185">L'espressione incorporata può accedere solo allo spazio dei nomi XML globale.</span><span class="sxs-lookup"><span data-stu-id="be79d-185">The embedded expression can access only the global XML namespace.</span></span>

<span data-ttu-id="be79d-186">Il compilatore Visual Basic converte tutti gli spazi dei nomi XML globali utilizzati da un valore letterale XML in una definizione di uno spazio dei nomi locale nel codice generato.</span><span class="sxs-lookup"><span data-stu-id="be79d-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="be79d-187">Gli spazi dei nomi XML globali non utilizzati non vengono visualizzati nel codice generato.</span><span class="sxs-lookup"><span data-stu-id="be79d-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>

## <a name="example"></a><span data-ttu-id="be79d-188">Esempio</span><span class="sxs-lookup"><span data-stu-id="be79d-188">Example</span></span>

<span data-ttu-id="be79d-189">Nell'esempio seguente viene illustrato come creare un elemento XML semplice con due elementi vuoti annidati.</span><span class="sxs-lookup"><span data-stu-id="be79d-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

<span data-ttu-id="be79d-190">Nell'esempio viene visualizzato il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="be79d-190">The example displays the following text.</span></span> <span data-ttu-id="be79d-191">Si noti che il valore letterale conserva la struttura degli elementi vuoti.</span><span class="sxs-lookup"><span data-stu-id="be79d-191">Notice that the literal preserves the structure of the empty elements.</span></span>

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a><span data-ttu-id="be79d-192">Esempio</span><span class="sxs-lookup"><span data-stu-id="be79d-192">Example</span></span>

<span data-ttu-id="be79d-193">Nell'esempio seguente viene illustrato come utilizzare le espressioni incorporate per assegnare un nome a un elemento e creare attributi.</span><span class="sxs-lookup"><span data-stu-id="be79d-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

<span data-ttu-id="be79d-194">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="be79d-194">This code displays the following text:</span></span>

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a><span data-ttu-id="be79d-195">Esempio</span><span class="sxs-lookup"><span data-stu-id="be79d-195">Example</span></span>

<span data-ttu-id="be79d-196">Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="be79d-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="be79d-197">USA quindi il prefisso dello spazio dei nomi per creare un valore letterale XML e visualizza il formato finale dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="be79d-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="be79d-198">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="be79d-198">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="be79d-199">Si noti che il compilatore ha convertito il prefisso dello spazio dei nomi XML globale in una definizione di prefisso per lo spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="be79d-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="be79d-200">L' \<ns:middle> elemento ridefinisce il prefisso dello spazio dei nomi XML per l' \<ns:inner1> elemento.</span><span class="sxs-lookup"><span data-stu-id="be79d-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="be79d-201">Tuttavia, l' \<ns:inner2> elemento utilizza lo spazio dei nomi definito dall' `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="be79d-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="be79d-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be79d-202">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="be79d-203">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="be79d-203">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="be79d-204">Valore letterale di commento XML</span><span class="sxs-lookup"><span data-stu-id="be79d-204">XML Comment Literal</span></span>](xml-comment-literal.md)
- [<span data-ttu-id="be79d-205">Valore letterale CDATA XML</span><span class="sxs-lookup"><span data-stu-id="be79d-205">XML CDATA Literal</span></span>](xml-cdata-literal.md)
- [<span data-ttu-id="be79d-206">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="be79d-206">XML Literals</span></span>](index.md)
- [<span data-ttu-id="be79d-207">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="be79d-207">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="be79d-208">Espressioni incorporate in XML</span><span class="sxs-lookup"><span data-stu-id="be79d-208">Embedded Expressions in XML</span></span>](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="be79d-209">Istruzione Imports (spazio dei nomi XML)</span><span class="sxs-lookup"><span data-stu-id="be79d-209">Imports Statement (XML Namespace)</span></span>](../statements/imports-statement-xml-namespace.md)

---
title: Valore letterale elemento XML (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralElement
dev_langs:
- VB
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
caps.latest.revision: 32
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
ms.openlocfilehash: d5cf769a1e3f668652d1eb4551058deba38a8acf
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="e180c-102">Valore letterale elemento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e180c-102">XML Element Literal (Visual Basic)</span></span>
<span data-ttu-id="e180c-103">Un valore letterale che rappresenta un <xref:System.Xml.Linq.XElement>oggetto.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e180c-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e180c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e180c-104">Syntax</span></span>  
  
```  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a><span data-ttu-id="e180c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="e180c-105">Parts</span></span>  
  
-   `<`  
  
     <span data-ttu-id="e180c-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e180c-106">Required.</span></span> <span data-ttu-id="e180c-107">Apre il tag dell'elemento iniziale.</span><span class="sxs-lookup"><span data-stu-id="e180c-107">Opens the starting element tag.</span></span>  
  
-   `name`  
  
     <span data-ttu-id="e180c-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e180c-108">Required.</span></span> <span data-ttu-id="e180c-109">Nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="e180c-109">Name of the element.</span></span> <span data-ttu-id="e180c-110">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="e180c-110">The format is one of the following:</span></span>  
  
    -   <span data-ttu-id="e180c-111">Testo letterale per il nome dell'elemento del modulo [`ePrefix``:`]`eName`, dove:</span><span class="sxs-lookup"><span data-stu-id="e180c-111">Literal text for the element name, of the form [`ePrefix``:`]`eName`, where:</span></span>  
  
        |<span data-ttu-id="e180c-112">Parte</span><span class="sxs-lookup"><span data-stu-id="e180c-112">Part</span></span>|<span data-ttu-id="e180c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e180c-113">Description</span></span>|  
        |---|---|  
        |`ePrefix`|<span data-ttu-id="e180c-114">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e180c-114">Optional.</span></span> <span data-ttu-id="e180c-115">Prefisso dello spazio dei nomi XML per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="e180c-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="e180c-116">Deve essere uno spazio dei nomi XML globale viene definito con un `Imports` istruzione nel file o a livello di progetto, o uno spazio dei nomi XML locale definito in questo elemento o un elemento padre.</span><span class="sxs-lookup"><span data-stu-id="e180c-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`eName`|<span data-ttu-id="e180c-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e180c-117">Required.</span></span> <span data-ttu-id="e180c-118">Nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="e180c-118">Name of the element.</span></span> <span data-ttu-id="e180c-119">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="e180c-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="e180c-120">-Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="e180c-120">-   Literal text.</span></span> <span data-ttu-id="e180c-121">Vedere [i nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="e180c-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="e180c-122">-Espressione incorporata del formato `<%=` e`NameExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="e180c-122">-   Embedded expression of the form `<%=` e`NameExp` `%>`.</span></span> <span data-ttu-id="e180c-123">Il tipo di `eNameExp` deve essere `String` o un tipo convertibile in modo implicito a <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="e180c-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
  
    -   <span data-ttu-id="e180c-124">Espressione incorporata del formato `<%=` `nameExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="e180c-124">Embedded expression of the form `<%=` `nameExp` `%>`.</span></span> <span data-ttu-id="e180c-125">Il tipo di `nameExp` deve essere `String` o un tipo convertibile in modo implicito in <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="e180c-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="e180c-126">Un'espressione incorporata non è consentita in un tag di chiusura di un elemento.</span><span class="sxs-lookup"><span data-stu-id="e180c-126">An embedded expression is not allowed in a closing tag of an element.</span></span>  
  
-   `attributeList`  
  
     <span data-ttu-id="e180c-127">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e180c-127">Optional.</span></span> <span data-ttu-id="e180c-128">Elenco di attributi dichiarato nel valore letterale.</span><span class="sxs-lookup"><span data-stu-id="e180c-128">List of attributes declared in the literal.</span></span>  
  
     `attribute [ attribute ... ]`  
  
     <span data-ttu-id="e180c-129">Ogni `attribute` ha una delle sintassi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e180c-129">Each `attribute` has one of the following syntaxes:</span></span>  
  
    -   <span data-ttu-id="e180c-130">Assegnazione, nel formato di attributi [`aPrefix``:`]`aName``=``aValue`, dove:</span><span class="sxs-lookup"><span data-stu-id="e180c-130">Attribute assignment, of the form [`aPrefix``:`]`aName``=``aValue`, where:</span></span>  
  
        |<span data-ttu-id="e180c-131">Parte</span><span class="sxs-lookup"><span data-stu-id="e180c-131">Part</span></span>|<span data-ttu-id="e180c-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e180c-132">Description</span></span>|  
        |---|---|  
        |`aPrefix`|<span data-ttu-id="e180c-133">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e180c-133">Optional.</span></span> <span data-ttu-id="e180c-134">Prefisso dello spazio dei nomi XML per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="e180c-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="e180c-135">Deve essere uno spazio dei nomi XML globale viene definito con un `Imports` istruzione o uno spazio dei nomi XML locale definito in questo elemento o un elemento padre.</span><span class="sxs-lookup"><span data-stu-id="e180c-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`aName`|<span data-ttu-id="e180c-136">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e180c-136">Required.</span></span> <span data-ttu-id="e180c-137">Nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="e180c-137">Name of the attribute.</span></span> <span data-ttu-id="e180c-138">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="e180c-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="e180c-139">-Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="e180c-139">-   Literal text.</span></span> <span data-ttu-id="e180c-140">Vedere [i nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="e180c-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="e180c-141">-Espressione incorporata del formato `<%=` `aNameExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="e180c-141">-   Embedded expression of the form `<%=` `aNameExp` `%>`.</span></span> <span data-ttu-id="e180c-142">Il tipo di `aNameExp` deve essere `String` o un tipo convertibile in modo implicito a <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="e180c-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
        |`aValue`|<span data-ttu-id="e180c-143">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e180c-143">Optional.</span></span> <span data-ttu-id="e180c-144">Valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="e180c-144">Value of the attribute.</span></span> <span data-ttu-id="e180c-145">Il formato è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="e180c-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="e180c-146">-Testo letterale, racchiuso tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="e180c-146">-   Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="e180c-147">-Espressione incorporata del formato `<%=` `aValueExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="e180c-147">-   Embedded expression of the form `<%=` `aValueExp` `%>`.</span></span> <span data-ttu-id="e180c-148">È consentito qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="e180c-148">Any type is allowed.</span></span>|  
  
    -   <span data-ttu-id="e180c-149">Espressione incorporata del formato `<%=` `aExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="e180c-149">Embedded expression of the form `<%=` `aExp` `%>`.</span></span>  
  
-   `/>`  
  
     <span data-ttu-id="e180c-150">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e180c-150">Optional.</span></span> <span data-ttu-id="e180c-151">Indica che l'elemento è un elemento vuoto, senza contenuto.</span><span class="sxs-lookup"><span data-stu-id="e180c-151">Indicates that the element is an empty element, without content.</span></span>  
  
-   `>`  
  
     <span data-ttu-id="e180c-152">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e180c-152">Required.</span></span> <span data-ttu-id="e180c-153">Termina il tag dell'elemento iniziale o vuoto.</span><span class="sxs-lookup"><span data-stu-id="e180c-153">Ends the beginning or empty element tag.</span></span>  
  
-   `elementContents`  
  
     <span data-ttu-id="e180c-154">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e180c-154">Optional.</span></span> <span data-ttu-id="e180c-155">Contenuto dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="e180c-155">Content of the element.</span></span>  
  
     `content [ content ... ]`  
  
     <span data-ttu-id="e180c-156">Ogni `content` può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="e180c-156">Each `content` can be one of the following:</span></span>  
  
    -   <span data-ttu-id="e180c-157">Testo letterale.</span><span class="sxs-lookup"><span data-stu-id="e180c-157">Literal text.</span></span> <span data-ttu-id="e180c-158">Tutti gli spazi vuoti in `elementContents` diventano significativi se è presente del testo letterale.</span><span class="sxs-lookup"><span data-stu-id="e180c-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>  
  
    -   <span data-ttu-id="e180c-159">Espressione incorporata del formato `<%=` `contentExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="e180c-159">Embedded expression of the form `<%=` `contentExp` `%>`.</span></span>  
  
    -   <span data-ttu-id="e180c-160">Valore letterale elemento XML.</span><span class="sxs-lookup"><span data-stu-id="e180c-160">XML element literal.</span></span>  
  
    -   <span data-ttu-id="e180c-161">Valore letterale commento XML.</span><span class="sxs-lookup"><span data-stu-id="e180c-161">XML comment literal.</span></span> <span data-ttu-id="e180c-162">Vedere [valore letterale commento XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="e180c-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>  
  
    -   <span data-ttu-id="e180c-163">Istruzione di elaborazione XML.</span><span class="sxs-lookup"><span data-stu-id="e180c-163">XML processing instruction literal.</span></span> <span data-ttu-id="e180c-164">Vedere [valore letterale istruzione di elaborazione XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="e180c-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>  
  
    -   <span data-ttu-id="e180c-165">Valore letterale CDATA XML.</span><span class="sxs-lookup"><span data-stu-id="e180c-165">XML CDATA literal.</span></span> <span data-ttu-id="e180c-166">Vedere [valore letterale CDATA XML](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="e180c-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>  
  
-   <span data-ttu-id="e180c-167">`</`[`name`]`>`</span><span class="sxs-lookup"><span data-stu-id="e180c-167">`</`[`name`]`>`</span></span>  
  
     <span data-ttu-id="e180c-168">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e180c-168">Optional.</span></span> <span data-ttu-id="e180c-169">Rappresenta il tag di chiusura per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="e180c-169">Represents the closing tag for the element.</span></span> <span data-ttu-id="e180c-170">Facoltativo `name` parametro non è consentito quando è il risultato di un'espressione incorporata.</span><span class="sxs-lookup"><span data-stu-id="e180c-170">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e180c-171">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e180c-171">Return Value</span></span>  
 <span data-ttu-id="e180c-172">Un <xref:System.Xml.Linq.XElement>oggetto.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e180c-172">An <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e180c-173">Note</span><span class="sxs-lookup"><span data-stu-id="e180c-173">Remarks</span></span>  
 <span data-ttu-id="e180c-174">È possibile utilizzare la sintassi del valore letterale elemento XML per creare <xref:System.Xml.Linq.XElement>oggetti nel codice.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e180c-174">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e180c-175">Un valore letterale XML può occupare più righe senza utilizzare caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="e180c-175">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="e180c-176">Questa funzionalità consente di copiare il contenuto di un documento XML e incollarlo direttamente in un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programma.</span><span class="sxs-lookup"><span data-stu-id="e180c-176">This feature enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="e180c-177">Le espressioni incorporate il formato `<%=` `exp` `%>` consentono di aggiungere informazioni dinamiche a un valore letterale elemento XML.</span><span class="sxs-lookup"><span data-stu-id="e180c-177">Embedded expressions of the form `<%=` `exp` `%>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="e180c-178">Per ulteriori informazioni, vedere [espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e180c-178">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="e180c-179">Il [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore converte il valore letterale elemento XML in chiamate per il <xref:System.Xml.Linq.XElement.%23ctor%2A>costruttore e, se necessario, il <xref:System.Xml.Linq.XAttribute.%23ctor%2A>costruttore.</xref:System.Xml.Linq.XAttribute.%23ctor%2A> </xref:System.Xml.Linq.XElement.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="e180c-179">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="e180c-180">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="e180c-180">XML Namespaces</span></span>  
 <span data-ttu-id="e180c-181">Prefissi dello spazio dei nomi XML sono utili quando è necessario creare valori letterali XML con elementi dallo spazio dei nomi stesso numero di volte nel codice.</span><span class="sxs-lookup"><span data-stu-id="e180c-181">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="e180c-182">È possibile utilizzare i prefissi dello spazio dei nomi XML globali, che può essere definito utilizzando il `Imports` istruzione o i prefissi locali, che può essere definito utilizzando il `xmlns:``xmlPrefix`= "`xmlNamespace`" sintassi degli attributi.</span><span class="sxs-lookup"><span data-stu-id="e180c-182">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:``xmlPrefix`="`xmlNamespace`" attribute syntax.</span></span> <span data-ttu-id="e180c-183">Per ulteriori informazioni, vedere [istruzione Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="e180c-183">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
 <span data-ttu-id="e180c-184">In base alle regole di ambito per gli spazi dei nomi XML, i prefissi locali hanno la precedenza sui prefissi globali.</span><span class="sxs-lookup"><span data-stu-id="e180c-184">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="e180c-185">Tuttavia, se un valore letterale XML definisce uno spazio dei nomi XML, tale spazio dei nomi non è disponibile per le espressioni contenute in un'espressione incorporata.</span><span class="sxs-lookup"><span data-stu-id="e180c-185">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="e180c-186">L'espressione incorporata può accedere solo i nomi XML globale.</span><span class="sxs-lookup"><span data-stu-id="e180c-186">The embedded expression can access only the global XML namespace.</span></span>  
  
 <span data-ttu-id="e180c-187">Il [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore converte ogni spazio dei nomi XML globale utilizzato da un valore letterale XML in una definizione dello spazio dei nomi locale nel codice generato.</span><span class="sxs-lookup"><span data-stu-id="e180c-187">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="e180c-188">Spazi dei nomi XML globali non utilizzati non vengono visualizzati nel codice generato.</span><span class="sxs-lookup"><span data-stu-id="e180c-188">Global XML namespaces that are not used do not appear in the generated code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e180c-189">Esempio</span><span class="sxs-lookup"><span data-stu-id="e180c-189">Example</span></span>  
 <span data-ttu-id="e180c-190">Nell'esempio seguente viene illustrato come creare un semplice elemento XML che ha due elementi vuoti nidificati.</span><span class="sxs-lookup"><span data-stu-id="e180c-190">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>  
  
 <span data-ttu-id="e180c-191">[!code-vb[VbXMLSamples&#20;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e180c-191">[!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]</span></span>  
  
 <span data-ttu-id="e180c-192">L'esempio mostra il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="e180c-192">The example displays the following text.</span></span> <span data-ttu-id="e180c-193">Si noti che il valore letterale mantiene la struttura degli elementi vuoti.</span><span class="sxs-lookup"><span data-stu-id="e180c-193">Notice that the literal preserves the structure of the empty elements.</span></span>  
  
```  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a><span data-ttu-id="e180c-194">Esempio</span><span class="sxs-lookup"><span data-stu-id="e180c-194">Example</span></span>  
 <span data-ttu-id="e180c-195">Nell'esempio seguente viene illustrato come utilizzare le espressioni incorporate per denominare un elemento e creare attributi.</span><span class="sxs-lookup"><span data-stu-id="e180c-195">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>  
  
 <span data-ttu-id="e180c-196">[!code-vb[VbXMLSamples numero&21;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e180c-196">[!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]</span></span>  
  
 <span data-ttu-id="e180c-197">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="e180c-197">This code displays the following text:</span></span>  
  
```  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a><span data-ttu-id="e180c-198">Esempio</span><span class="sxs-lookup"><span data-stu-id="e180c-198">Example</span></span>  
 <span data-ttu-id="e180c-199">Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="e180c-199">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="e180c-200">Quindi, il prefisso dello spazio dei nomi utilizzato per creare un file XML letterale e visualizza il formato dell'elemento finale.</span><span class="sxs-lookup"><span data-stu-id="e180c-200">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>  
  
 <span data-ttu-id="e180c-201">[!code-vb[VbXMLSamples&#22;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="e180c-201">[!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]</span></span>  
  
 <span data-ttu-id="e180c-202">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="e180c-202">This code displays the following text:</span></span>  
  
```  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="e180c-203">Si noti che il compilatore converte il prefisso dello spazio dei nomi XML globali in una definizione del prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="e180c-203">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="e180c-204">Il \<ns:middle > elemento consente di ridefinire il prefisso dello spazio dei nomi XML per il \<ns:inner1 > elemento.</span><span class="sxs-lookup"><span data-stu-id="e180c-204">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="e180c-205">Tuttavia, il \<ns:inner2 > elemento utilizza lo spazio dei nomi definito per il `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="e180c-205">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e180c-206">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e180c-206">See Also</span></span>  
 <span data-ttu-id="e180c-207"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e180c-207"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="e180c-208"> [Nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="e180c-208"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span></span>  
<span data-ttu-id="e180c-209"> [Valore letterale commento XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span><span class="sxs-lookup"><span data-stu-id="e180c-209"> [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span></span>  
<span data-ttu-id="e180c-210"> [Valore letterale CDATA XML](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md) </span><span class="sxs-lookup"><span data-stu-id="e180c-210"> [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md) </span></span>  
<span data-ttu-id="e180c-211"> [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="e180c-211"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="e180c-212"> [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="e180c-212"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="e180c-213"> [Espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span><span class="sxs-lookup"><span data-stu-id="e180c-213"> [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span></span>  
<span data-ttu-id="e180c-214"> [Istruzione Imports (spazio dei nomi XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)</span><span class="sxs-lookup"><span data-stu-id="e180c-214"> [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)</span></span>

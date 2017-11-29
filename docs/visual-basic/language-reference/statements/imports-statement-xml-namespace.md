---
title: Istruzione Imports (spazio dei nomi XML)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a0fe6d37c58ead94f2c03736318209abb67cd6dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imports-statement-xml-namespace"></a><span data-ttu-id="ca09f-102">Istruzione Imports (spazio dei nomi XML)</span><span class="sxs-lookup"><span data-stu-id="ca09f-102">Imports Statement (XML Namespace)</span></span>
<span data-ttu-id="ca09f-103">Importa i prefissi dello spazio dei nomi XML per l'utilizzo in valori letterali XML e proprietà axis XML.</span><span class="sxs-lookup"><span data-stu-id="ca09f-103">Imports XML namespace prefixes for use in XML literals and XML axis properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca09f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca09f-104">Syntax</span></span>  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a><span data-ttu-id="ca09f-105">Parti</span><span class="sxs-lookup"><span data-stu-id="ca09f-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="ca09f-106">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ca09f-106">Optional.</span></span> <span data-ttu-id="ca09f-107">La stringa da cui XML elementi e attributi possono fare riferimento a `xmlNamespaceName`.</span><span class="sxs-lookup"><span data-stu-id="ca09f-107">The string by which XML elements and attributes can refer to `xmlNamespaceName`.</span></span> <span data-ttu-id="ca09f-108">Se non `xmlNamespacePrefix` viene fornito, spazio dei nomi XML importato è lo spazio dei nomi XML predefinito.</span><span class="sxs-lookup"><span data-stu-id="ca09f-108">If no `xmlNamespacePrefix` is supplied, the imported XML namespace is the default XML namespace.</span></span> <span data-ttu-id="ca09f-109">Deve essere un identificatore XML valido.</span><span class="sxs-lookup"><span data-stu-id="ca09f-109">Must be a valid XML identifier.</span></span> <span data-ttu-id="ca09f-110">Per ulteriori informazioni, vedere [attributi e i nomi di elementi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="ca09f-110">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>  
  
 `xmlNamespaceName`  
 <span data-ttu-id="ca09f-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ca09f-111">Required.</span></span> <span data-ttu-id="ca09f-112">Stringa che identifica lo spazio dei nomi XML importato.</span><span class="sxs-lookup"><span data-stu-id="ca09f-112">The string identifying the XML namespace being imported.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca09f-113">Note</span><span class="sxs-lookup"><span data-stu-id="ca09f-113">Remarks</span></span>  
 <span data-ttu-id="ca09f-114">È possibile utilizzare il `Imports` istruzione per definire spazi dei nomi XML globali che è possibile utilizzare con i valori letterali XML e proprietà axis XML o come parametri per il `GetXmlNamespace` operatore.</span><span class="sxs-lookup"><span data-stu-id="ca09f-114">You can use the `Imports` statement to define global XML namespaces that you can use with XML literals and XML axis properties, or as parameters passed to the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="ca09f-115">(Per informazioni sull'utilizzo di `Imports` per importare un alias che può essere usato in cui vengono utilizzati i nomi dei tipi nel codice, vedere [istruzione Imports (tipo e Namespace .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) La sintassi per dichiarare uno spazio dei nomi XML utilizzando il `Imports` istruzione è identica a quella utilizzata nel codice XML.</span><span class="sxs-lookup"><span data-stu-id="ca09f-115">(For information about using the `Imports` statement to import an alias that can be used where type names are used in your code, see [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) The syntax for declaring an XML namespace by using the `Imports` statement is identical to the syntax used in XML.</span></span> <span data-ttu-id="ca09f-116">Pertanto, è possibile copiare una dichiarazione dello spazio dei nomi da un file XML e utilizzarla in un `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="ca09f-116">Therefore, you can copy a namespace declaration from an XML file and use it in an `Imports` statement.</span></span>  
  
 <span data-ttu-id="ca09f-117">Prefissi di spazio dei nomi XML sono utili quando si desidera creare ripetutamente elementi XML che provengono dallo stesso spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ca09f-117">XML namespace prefixes are useful when you want to repeatedly create XML elements that are from the same namespace.</span></span> <span data-ttu-id="ca09f-118">Il prefisso dello spazio dei nomi XML dichiarati con la `Imports` è globale nel senso che sia disponibile a tutto il codice nel file di istruzione.</span><span class="sxs-lookup"><span data-stu-id="ca09f-118">The XML namespace prefix declared with the `Imports` statement is global in the sense that it is available to all code in the file.</span></span> <span data-ttu-id="ca09f-119">È possibile utilizzarlo quando si creano valori letterali dell'elemento XML e quando si accede a proprietà axis XML.</span><span class="sxs-lookup"><span data-stu-id="ca09f-119">You can use it when you create XML element literals and when you access XML axis properties.</span></span> <span data-ttu-id="ca09f-120">Per ulteriori informazioni, vedere [XML elemento Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) e [proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ca09f-120">For more information, see [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).</span></span>  
  
 <span data-ttu-id="ca09f-121">Se si definisce un spazio dei nomi XML globale senza un prefisso dello spazio dei nomi (ad esempio, `Imports <xmlns="http://SomeNameSpace>"`), tale spazio dei nomi viene considerato lo spazio dei nomi XML predefinito.</span><span class="sxs-lookup"><span data-stu-id="ca09f-121">If you define a global XML namespace without a namespace prefix (for example, `Imports <xmlns="http://SomeNameSpace>"`), that namespace is considered the default XML namespace.</span></span> <span data-ttu-id="ca09f-122">Spazio dei nomi XML predefinito viene utilizzato per le proprietà axis XML attributo che non specificano in modo esplicito uno spazio dei nomi o valori letterali dell'elemento XML.</span><span class="sxs-lookup"><span data-stu-id="ca09f-122">The default XML namespace is used for any XML element literals or XML attribute axis properties that do not explicitly specify a namespace.</span></span> <span data-ttu-id="ca09f-123">Spazio dei nomi predefinito viene usato anche se lo spazio dei nomi specificato è lo spazio dei nomi vuoto (vale a dire `xmlns=""`).</span><span class="sxs-lookup"><span data-stu-id="ca09f-123">The default namespace is also used if the specified namespace is the empty namespace (that is, `xmlns=""`).</span></span> <span data-ttu-id="ca09f-124">Spazio dei nomi XML predefinito non è applicabile ad attributi XML nei valori letterali XML o per le proprietà axis dell'attributo XML non dispone di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ca09f-124">The default XML namespace does not apply to XML attributes in XML literals or to XML attribute axis properties that do not have a namespace.</span></span>  
  
 <span data-ttu-id="ca09f-125">Spazi dei nomi XML definiti in un valore letterale XML, che vengono chiamati *locale spazi dei nomi XML*, hanno la precedenza su spazi dei nomi XML definiti per il `Imports` istruzione come globale.</span><span class="sxs-lookup"><span data-stu-id="ca09f-125">XML namespaces that are defined in an XML literal, which are called *local XML namespaces*, take precedence over XML namespaces that are defined by the `Imports` statement as global.</span></span> <span data-ttu-id="ca09f-126">Spazi dei nomi XML definiti per il `Imports` istruzione hanno la precedenza su spazi dei nomi XML importato per un progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ca09f-126">XML namespaces that are defined by the `Imports` statement take precedence over XML namespaces imported for a Visual Basic project.</span></span> <span data-ttu-id="ca09f-127">Se un valore letterale XML definisce uno spazio dei nomi XML, spazio dei nomi locale non è applicabile per le espressioni incorporate.</span><span class="sxs-lookup"><span data-stu-id="ca09f-127">If an XML literal defines an XML namespace, that local namespace does not apply to embedded expressions.</span></span>  
  
 <span data-ttu-id="ca09f-128">Spazi dei nomi XML globale seguire le stesse regole di ambito e di definizione degli spazi dei nomi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca09f-128">Global XML namespaces follow the same scoping and definition rules as .NET Framework namespaces.</span></span> <span data-ttu-id="ca09f-129">Di conseguenza, è possibile includere un `Imports` istruzione per definire un spazio dei nomi XML globale ovunque sia possibile importare uno spazio dei nomi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca09f-129">As a result, you can include an `Imports` statement to define a global XML namespace anywhere you can import a .NET Framework namespace.</span></span> <span data-ttu-id="ca09f-130">Questo include i file di codice e spazi dei nomi importati a livello di progetto.</span><span class="sxs-lookup"><span data-stu-id="ca09f-130">This includes both code files and project-level imported namespaces.</span></span> <span data-ttu-id="ca09f-131">Per informazioni sugli spazi dei nomi importato a livello di progetto, vedere [pagina riferimenti, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ca09f-131">For information about project-level imported namespaces, see [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="ca09f-132">Ogni file di origine può contenere un numero qualsiasi di `Imports` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="ca09f-132">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="ca09f-133">Queste devono seguire le dichiarazioni di opzione, ad esempio il `Option Strict` istruzione essi devono precedere dichiarazione di elemento di programmazione, ad esempio `Module` o `Class` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="ca09f-133">These must follow option declarations, such as the `Option Strict` statement, and they must precede programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca09f-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="ca09f-134">Example</span></span>  
 <span data-ttu-id="ca09f-135">L'esempio seguente importa uno spazio dei nomi XML predefinito e un spazio dei nomi XML identificato con il prefisso `ns`.</span><span class="sxs-lookup"><span data-stu-id="ca09f-135">The following example imports a default XML namespace and an XML namespace identified with the prefix `ns`.</span></span> <span data-ttu-id="ca09f-136">Crea quindi i valori letterali XML che utilizzano entrambi gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ca09f-136">It then creates XML literals that use both namespaces.</span></span>  
  
 [!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]  
  
 <span data-ttu-id="ca09f-137">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="ca09f-137">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## <a name="example"></a><span data-ttu-id="ca09f-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="ca09f-138">Example</span></span>  
 <span data-ttu-id="ca09f-139">L'esempio seguente importa il prefisso dello spazio dei nomi XML `ns`.</span><span class="sxs-lookup"><span data-stu-id="ca09f-139">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="ca09f-140">Crea quindi un valore letterale XML che viene utilizzato il prefisso dello spazio dei nomi e visualizza il formato dell'elemento finale.</span><span class="sxs-lookup"><span data-stu-id="ca09f-140">It then creates an XML literal that uses the namespace prefix and displays the element's final form.</span></span>  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]  
  
 <span data-ttu-id="ca09f-141">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="ca09f-141">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="ca09f-142">Si noti che il compilatore converte il prefisso dello spazio dei nomi XML da un prefisso globale a una definizione del prefisso locale.</span><span class="sxs-lookup"><span data-stu-id="ca09f-142">Notice that the compiler converted the XML namespace prefix from a global prefix to a local prefix definition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca09f-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="ca09f-143">Example</span></span>  
 <span data-ttu-id="ca09f-144">L'esempio seguente importa il prefisso dello spazio dei nomi XML `ns`.</span><span class="sxs-lookup"><span data-stu-id="ca09f-144">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="ca09f-145">Il prefisso dello spazio dei nomi viene quindi usato per creare un valore letterale XML e accedere al primo nodo figlio con il nome completo `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="ca09f-145">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]  
  
 <span data-ttu-id="ca09f-146">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="ca09f-146">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="ca09f-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca09f-147">See Also</span></span>  
 [<span data-ttu-id="ca09f-148">Valore letterale elemento XML</span><span class="sxs-lookup"><span data-stu-id="ca09f-148">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="ca09f-149">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="ca09f-149">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="ca09f-150">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="ca09f-150">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [<span data-ttu-id="ca09f-151">Operatore GetXmlNamespace</span><span class="sxs-lookup"><span data-stu-id="ca09f-151">GetXmlNamespace Operator</span></span>](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)

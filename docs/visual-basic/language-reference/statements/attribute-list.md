---
title: Elenco degli attributi (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: adfb980380bb787280715ca0185950657e174eb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="2578c-102">Elenco degli attributi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2578c-102">Attribute List (Visual Basic)</span></span>
<span data-ttu-id="2578c-103">Specifica gli attributi da applicare a un elemento di programmazione dichiarato.</span><span class="sxs-lookup"><span data-stu-id="2578c-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="2578c-104">Gli attributi sono separati da una virgola.</span><span class="sxs-lookup"><span data-stu-id="2578c-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="2578c-105">Di seguito è la sintassi per un attributo.</span><span class="sxs-lookup"><span data-stu-id="2578c-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2578c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2578c-106">Syntax</span></span>  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="2578c-107">Parti</span><span class="sxs-lookup"><span data-stu-id="2578c-107">Parts</span></span>  
 `attributemodifier`  
 <span data-ttu-id="2578c-108">Obbligatorio per gli attributi applicati all'inizio di un file di origine.</span><span class="sxs-lookup"><span data-stu-id="2578c-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="2578c-109">Può essere [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) o [modulo](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="2578c-109">Can be [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) or [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span></span>  
  
 `attributename`  
 <span data-ttu-id="2578c-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2578c-110">Required.</span></span> <span data-ttu-id="2578c-111">Nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="2578c-111">Name of the attribute.</span></span>  
  
 `attributearguments`  
 <span data-ttu-id="2578c-112">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2578c-112">Optional.</span></span> <span data-ttu-id="2578c-113">Elenco di argomenti posizionali per questo attributo.</span><span class="sxs-lookup"><span data-stu-id="2578c-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="2578c-114">Più argomenti sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="2578c-114">Multiple arguments are separated by commas.</span></span>  
  
 `attributeinitializer`  
 <span data-ttu-id="2578c-115">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2578c-115">Optional.</span></span> <span data-ttu-id="2578c-116">Elenco di inizializzatori di variabile o proprietà per questo attributo.</span><span class="sxs-lookup"><span data-stu-id="2578c-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="2578c-117">Gli inizializzatori sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="2578c-117">Multiple initializers are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2578c-118">Note</span><span class="sxs-lookup"><span data-stu-id="2578c-118">Remarks</span></span>  
 <span data-ttu-id="2578c-119">È possibile applicare uno o più attributi a qualsiasi elemento di programmazione (tipi, procedure, le proprietà e così via).</span><span class="sxs-lookup"><span data-stu-id="2578c-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="2578c-120">Gli attributi vengono visualizzati nei metadati dell'assembly e consentono di annotare il codice o specificare l'utilizzo di un particolare elemento di programmazione.</span><span class="sxs-lookup"><span data-stu-id="2578c-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="2578c-121">È possibile applicare attributi definiti da Visual Basic e .NET Framework, ed è possibile definire attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2578c-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="2578c-122">Per ulteriori informazioni sull'utilizzo degli attributi, vedere [Cenni preliminari sugli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="2578c-122">For more information on when to use attributes, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="2578c-123">Per informazioni sui nomi degli attributi, vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="2578c-123">For information on attribute names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="2578c-124">Regole</span><span class="sxs-lookup"><span data-stu-id="2578c-124">Rules</span></span>  
  
-   <span data-ttu-id="2578c-125">**Selezione host.**</span><span class="sxs-lookup"><span data-stu-id="2578c-125">**Placement.**</span></span> <span data-ttu-id="2578c-126">È possibile applicare attributi a dichiarato più elementi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="2578c-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="2578c-127">Per applicare uno o più attributi, posizionare un *blocco di attributi* all'inizio della dichiarazione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="2578c-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="2578c-128">Ogni voce nell'elenco degli attributi specifica un attributo che si desidera applicare, e il modificatore e gli argomenti utilizzati per la chiamata dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="2578c-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
-   <span data-ttu-id="2578c-129">**Parentesi angolari.**</span><span class="sxs-lookup"><span data-stu-id="2578c-129">**Angle Brackets.**</span></span> <span data-ttu-id="2578c-130">Se si fornisce un elenco di attributi, è necessario racchiuderlo tra parentesi quadre ("`<`"e"`>`").</span><span class="sxs-lookup"><span data-stu-id="2578c-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
-   <span data-ttu-id="2578c-131">**Parte della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="2578c-131">**Part of the Declaration.**</span></span> <span data-ttu-id="2578c-132">L'attributo deve essere parte della dichiarazione di elemento, non un'istruzione separata.</span><span class="sxs-lookup"><span data-stu-id="2578c-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="2578c-133">È possibile utilizzare la sequenza di continuazione di riga (" `_`") per estendere l'istruzione di dichiarazione su più righe di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="2578c-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
-   <span data-ttu-id="2578c-134">**Modificatori.**</span><span class="sxs-lookup"><span data-stu-id="2578c-134">**Modifiers.**</span></span> <span data-ttu-id="2578c-135">Un modificatore di attributo (`Assembly` o `Module`) è necessaria per ogni attributo applicato a un elemento di programmazione all'inizio di un file di origine.</span><span class="sxs-lookup"><span data-stu-id="2578c-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="2578c-136">Attributo modificatori non consentiti per gli attributi applicati agli elementi che non si trovano all'inizio di un file di origine.</span><span class="sxs-lookup"><span data-stu-id="2578c-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
-   <span data-ttu-id="2578c-137">**Argomenti.**</span><span class="sxs-lookup"><span data-stu-id="2578c-137">**Arguments.**</span></span> <span data-ttu-id="2578c-138">Tutti gli argomenti posizionali per un attributo devono precedere gli inizializzatori di qualsiasi variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="2578c-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2578c-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="2578c-139">Example</span></span>  
 <span data-ttu-id="2578c-140">Nell'esempio seguente viene applicato il <xref:System.Runtime.InteropServices.DllImportAttribute> dell'attributo a una struttura di definizione di un `Function` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="2578c-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <span data-ttu-id="2578c-141"><xref:System.Runtime.InteropServices.DllImportAttribute>indica che la routine con attributi rappresenta un punto di ingresso in una libreria di collegamento dinamico (DLL) non gestita.</span><span class="sxs-lookup"><span data-stu-id="2578c-141"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="2578c-142">L'attributo fornisce il nome della DLL come un argomento posizionale e le altre informazioni come inizializzatori.</span><span class="sxs-lookup"><span data-stu-id="2578c-142">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2578c-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2578c-143">See Also</span></span>  
 [<span data-ttu-id="2578c-144">Assembly</span><span class="sxs-lookup"><span data-stu-id="2578c-144">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [<span data-ttu-id="2578c-145">Modulo \<parola chiave></span><span class="sxs-lookup"><span data-stu-id="2578c-145">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [<span data-ttu-id="2578c-146">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="2578c-146">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="2578c-147">Procedura: Interrompere e combinare istruzioni nel codice</span><span class="sxs-lookup"><span data-stu-id="2578c-147">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

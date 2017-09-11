---
title: Tipo di promozione (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declared elements, scope
- visibility, declared elements
- Partial keyword, unexpected results with type promotion
- scope, declared elements
- scope, Visual Basic
- type promotion
- declared elements, visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: 17
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
ms.openlocfilehash: 383f4b1d29e9bbf81eee44bf78762a80aea9eb36
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="71d76-102">Promozione tipo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71d76-102">Type Promotion (Visual Basic)</span></span>
<span data-ttu-id="71d76-103">Quando si dichiara un elemento di programmazione in un modulo, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] promuove l'ambito per lo spazio dei nomi che contiene il modulo.</span><span class="sxs-lookup"><span data-stu-id="71d76-103">When you declare a programming element in a module, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="71d76-104">Ciò è noto come *promozione del tipo*.</span><span class="sxs-lookup"><span data-stu-id="71d76-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="71d76-105">Nell'esempio seguente viene illustrata una definizione di base di un modulo e due membri del modulo.</span><span class="sxs-lookup"><span data-stu-id="71d76-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 <span data-ttu-id="71d76-106">[!code-vb[VbVbalrDeclaredElements n.&1;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="71d76-106">[!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]</span></span>  
  
 <span data-ttu-id="71d76-107">All'interno di `projModule`, programmazione gli elementi dichiarati a livello di modulo vengono promossi alla `projNamespace`.</span><span class="sxs-lookup"><span data-stu-id="71d76-107">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="71d76-108">Nell'esempio precedente, `basicEnum` e `innerClass` alzate di livello, ma `numberSub` non lo è, poiché non è dichiarato a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="71d76-108">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="71d76-109">Effetto della promozione del tipo</span><span class="sxs-lookup"><span data-stu-id="71d76-109">Effect of Type Promotion</span></span>  
 <span data-ttu-id="71d76-110">L'effetto della promozione del tipo è che la stringa di qualificazione non è necessario includere il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="71d76-110">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="71d76-111">Nell'esempio seguente effettuate due chiamate alla procedura nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="71d76-111">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 <span data-ttu-id="71d76-112">[!code-vb[VbVbalrDeclaredElements n.&2;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="71d76-112">[!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]</span></span>  
  
 <span data-ttu-id="71d76-113">Nell'esempio precedente, la prima chiamata utilizza stringhe di qualificazione complete.</span><span class="sxs-lookup"><span data-stu-id="71d76-113">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="71d76-114">Tuttavia, questo non è necessario a causa di promozione del tipo.</span><span class="sxs-lookup"><span data-stu-id="71d76-114">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="71d76-115">Anche la seconda chiamata accede a membri del modulo senza includere `projModule` nelle stringhe di qualificazione.</span><span class="sxs-lookup"><span data-stu-id="71d76-115">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="71d76-116">Annullamento dell'effetto della promozione del tipo</span><span class="sxs-lookup"><span data-stu-id="71d76-116">Defeat of Type Promotion</span></span>  
 <span data-ttu-id="71d76-117">Se lo spazio dei nomi dispone già di un membro con lo stesso nome di un membro del modulo, la promozione del tipo viene annullato per tale membro.</span><span class="sxs-lookup"><span data-stu-id="71d76-117">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="71d76-118">Nell'esempio seguente viene illustrata una definizione di base di un'enumerazione e un modulo all'interno dello stesso spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="71d76-118">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 <span data-ttu-id="71d76-119">[!code-vb[VbVbalrDeclaredElements n.&3;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="71d76-119">[!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]</span></span>  
  
 <span data-ttu-id="71d76-120">Nell'esempio precedente, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Impossibile promuovere la classe `abc` a `thisNameSpace` perché esiste già un'enumerazione con lo stesso nome a livello di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="71d76-120">In the preceding example, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="71d76-121">Per accedere a `abcSub`, è necessario utilizzare la stringa di qualificazione completo `thisNamespace.thisModule.abc.abcSub`.</span><span class="sxs-lookup"><span data-stu-id="71d76-121">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="71d76-122">Tuttavia, classe `xyz` ancora viene promosso, ed è possibile accedere `xyzSub` con la stringa più corta qualificazione `thisNamespace.xyz.xyzSub`.</span><span class="sxs-lookup"><span data-stu-id="71d76-122">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="71d76-123">Annullamento dell'effetto della promozione del tipo per i tipi parziali</span><span class="sxs-lookup"><span data-stu-id="71d76-123">Defeat of Type Promotion for Partial Types</span></span>  
 <span data-ttu-id="71d76-124">Se una classe o struttura all'interno di un modulo viene utilizzato il [parziale](../../../../visual-basic/language-reference/modifiers/partial.md) (parola chiave), la promozione dei tipi viene automaticamente annullata da tale classe o struttura, se lo spazio dei nomi ha un membro con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="71d76-124">If a class or structure inside a module uses the [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="71d76-125">Altri elementi del modulo sono comunque idonei per la promozione del tipo.</span><span class="sxs-lookup"><span data-stu-id="71d76-125">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="71d76-126">**Conseguenze.**</span><span class="sxs-lookup"><span data-stu-id="71d76-126">**Consequences.**</span></span> <span data-ttu-id="71d76-127">Annullamento dell'effetto della promozione del tipo di una definizione parziale può causare risultati imprevisti e persino errori del compilatore.</span><span class="sxs-lookup"><span data-stu-id="71d76-127">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="71d76-128">L'esempio seguente mostra alcune definizioni parziali di una classe, uno dei quali è all'interno di un modulo.</span><span class="sxs-lookup"><span data-stu-id="71d76-128">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 <span data-ttu-id="71d76-129">[!code-vb[VbVbalrDeclaredElements n.&4;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="71d76-129">[!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]</span></span>  
  
 <span data-ttu-id="71d76-130">Nell'esempio precedente, lo sviluppatore potrebbe aspettarsi che il compilatore per unire le due definizioni parziali di `sampleClass`.</span><span class="sxs-lookup"><span data-stu-id="71d76-130">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="71d76-131">Tuttavia, il compilatore non considera promozione per la definizione parziale all'interno di `sampleModule`.</span><span class="sxs-lookup"><span data-stu-id="71d76-131">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="71d76-132">Di conseguenza, il tentativo di compilare due classi separate e distinte, denominate entrambe `sampleClass` ma con percorsi di qualificazione differenti.</span><span class="sxs-lookup"><span data-stu-id="71d76-132">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="71d76-133">Il compilatore unisce le definizioni parziali solo se i relativi percorsi completi sono identici.</span><span class="sxs-lookup"><span data-stu-id="71d76-133">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="71d76-134">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="71d76-134">Recommendations</span></span>  
 <span data-ttu-id="71d76-135">I suggerimenti seguenti rappresentano una buona norma di programmazione.</span><span class="sxs-lookup"><span data-stu-id="71d76-135">The following recommendations represent good programming practice.</span></span>  
  
-   <span data-ttu-id="71d76-136">**Nomi univoci.**</span><span class="sxs-lookup"><span data-stu-id="71d76-136">**Unique Names.**</span></span> <span data-ttu-id="71d76-137">Quando si dispone di un controllo completo sulla denominazione degli elementi di programmazione, è sempre una buona idea utilizzare nomi univoci ovunque.</span><span class="sxs-lookup"><span data-stu-id="71d76-137">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="71d76-138">I nomi identici richiedono una qualificazione aggiuntiva e possono rendere difficile leggere il codice.</span><span class="sxs-lookup"><span data-stu-id="71d76-138">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="71d76-139">Si può inoltre causare errori difficili da rilevare e risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="71d76-139">They can also lead to subtle errors and unexpected results.</span></span>  
  
-   <span data-ttu-id="71d76-140">**Nome completo.**</span><span class="sxs-lookup"><span data-stu-id="71d76-140">**Full Qualification.**</span></span> <span data-ttu-id="71d76-141">Quando si lavora con i moduli e altri elementi dello stesso spazio dei nomi, l'approccio più sicuro consiste nell'utilizzare sempre il nome completo per tutti gli elementi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="71d76-141">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="71d76-142">Se la promozione del tipo viene annullato per un membro del modulo e non è completamente qualificare tale membro, è possibile accedere accidentalmente un elemento di programmazione diversi.</span><span class="sxs-lookup"><span data-stu-id="71d76-142">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71d76-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71d76-143">See Also</span></span>  
 <span data-ttu-id="71d76-144">[Module (istruzione)](../../../../visual-basic/language-reference/statements/module-statement.md) </span><span class="sxs-lookup"><span data-stu-id="71d76-144">[Module Statement](../../../../visual-basic/language-reference/statements/module-statement.md) </span></span>  
<span data-ttu-id="71d76-145"> [Istruzione Namespace](../../../../visual-basic/language-reference/statements/namespace-statement.md) </span><span class="sxs-lookup"><span data-stu-id="71d76-145"> [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md) </span></span>  
<span data-ttu-id="71d76-146"> [Parziale](../../../../visual-basic/language-reference/modifiers/partial.md) </span><span class="sxs-lookup"><span data-stu-id="71d76-146"> [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) </span></span>  
<span data-ttu-id="71d76-147"> [Ambito in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span><span class="sxs-lookup"><span data-stu-id="71d76-147"> [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span></span>  
<span data-ttu-id="71d76-148"> [Procedura: controllare l'ambito di una variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md) </span><span class="sxs-lookup"><span data-stu-id="71d76-148"> [How to: Control the Scope of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md) </span></span>  
<span data-ttu-id="71d76-149"> [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span><span class="sxs-lookup"><span data-stu-id="71d76-149"> [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span></span>

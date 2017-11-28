---
title: Promozione tipo (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3a55c023afe7afe96f862f0b3cbbdb03a15b902
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="21112-102">Promozione tipo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21112-102">Type Promotion (Visual Basic)</span></span>
<span data-ttu-id="21112-103">Quando si dichiara un elemento di programmazione in un modulo, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] promuove l'ambito allo spazio dei nomi che contiene il modulo.</span><span class="sxs-lookup"><span data-stu-id="21112-103">When you declare a programming element in a module, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="21112-104">Questo è noto come *promozione del tipo*.</span><span class="sxs-lookup"><span data-stu-id="21112-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="21112-105">Nell'esempio seguente mostra una struttura di definizione di un modulo e due membri del modulo.</span><span class="sxs-lookup"><span data-stu-id="21112-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 <span data-ttu-id="21112-106">All'interno di `projModule`, programmazione gli elementi dichiarati a livello di modulo vengono promossi alla `projNamespace`.</span><span class="sxs-lookup"><span data-stu-id="21112-106">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="21112-107">Nell'esempio precedente, `basicEnum` e `innerClass` vengono alzate di livello, ma `numberSub` non lo è, poiché non è stato dichiarato a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="21112-107">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="21112-108">Effetto della promozione del tipo</span><span class="sxs-lookup"><span data-stu-id="21112-108">Effect of Type Promotion</span></span>  
 <span data-ttu-id="21112-109">L'effetto della promozione del tipo è che la stringa di qualificazione non è necessario includere il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="21112-109">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="21112-110">Nell'esempio seguente effettua le due chiamate alla procedura nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="21112-110">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 <span data-ttu-id="21112-111">Nell'esempio precedente, la prima chiamata utilizza stringhe di qualificazione completo.</span><span class="sxs-lookup"><span data-stu-id="21112-111">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="21112-112">Tuttavia, questo non è necessario a causa di promozione del tipo.</span><span class="sxs-lookup"><span data-stu-id="21112-112">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="21112-113">La seconda chiamata anche gli accessi ai membri del modulo senza includere `projModule` nelle stringhe di qualificazione.</span><span class="sxs-lookup"><span data-stu-id="21112-113">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="21112-114">Annullamento dell'effetto della promozione del tipo</span><span class="sxs-lookup"><span data-stu-id="21112-114">Defeat of Type Promotion</span></span>  
 <span data-ttu-id="21112-115">Se lo spazio dei nomi contiene già un membro con lo stesso nome di un membro di modulo, la promozione del tipo viene annullato per tale membro.</span><span class="sxs-lookup"><span data-stu-id="21112-115">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="21112-116">Nell'esempio seguente viene illustrata una definizione di base di un'enumerazione e un modulo entro lo stesso spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="21112-116">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 <span data-ttu-id="21112-117">Nell'esempio precedente, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] non è possibile promuovere la classe `abc` a `thisNameSpace` perché esiste già un'enumerazione con lo stesso nome a livello di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="21112-117">In the preceding example, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="21112-118">Per accedere a `abcSub`, è necessario utilizzare la stringa di qualificazione completo `thisNamespace.thisModule.abc.abcSub`.</span><span class="sxs-lookup"><span data-stu-id="21112-118">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="21112-119">Tuttavia, classe `xyz` ancora viene promosso, ed è possibile accedere `xyzSub` più breve stringa di qualificazione `thisNamespace.xyz.xyzSub`.</span><span class="sxs-lookup"><span data-stu-id="21112-119">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="21112-120">Annullamento dell'effetto della promozione del tipo per i tipi parziali</span><span class="sxs-lookup"><span data-stu-id="21112-120">Defeat of Type Promotion for Partial Types</span></span>  
 <span data-ttu-id="21112-121">Se una classe o struttura all'interno di un modulo viene utilizzato il [parziale](../../../../visual-basic/language-reference/modifiers/partial.md) (parola chiave), la promozione del tipo viene automaticamente annullato per quella classe o struttura, se lo spazio dei nomi è un membro con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="21112-121">If a class or structure inside a module uses the [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="21112-122">Gli altri elementi nel modulo sono comunque idonei per la promozione del tipo.</span><span class="sxs-lookup"><span data-stu-id="21112-122">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="21112-123">**Conseguenze.**</span><span class="sxs-lookup"><span data-stu-id="21112-123">**Consequences.**</span></span> <span data-ttu-id="21112-124">Annullamento dell'effetto della promozione del tipo di una definizione parziale può causare risultati imprevisti e persino errori del compilatore.</span><span class="sxs-lookup"><span data-stu-id="21112-124">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="21112-125">L'esempio seguente mostra alcune definizioni parziali di una classe, uno dei quali è all'interno di un modulo.</span><span class="sxs-lookup"><span data-stu-id="21112-125">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 <span data-ttu-id="21112-126">Nell'esempio precedente, lo sviluppatore può aspettarsi che il compilatore per unire le due definizioni parziali di `sampleClass`.</span><span class="sxs-lookup"><span data-stu-id="21112-126">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="21112-127">Tuttavia, il compilatore non considera l'innalzamento di livello per la definizione parziale all'interno di `sampleModule`.</span><span class="sxs-lookup"><span data-stu-id="21112-127">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="21112-128">Di conseguenza, il tentativo di compilare due classi separate e distinte, entrambi denominati `sampleClass` ma con percorsi di qualificazione differenti.</span><span class="sxs-lookup"><span data-stu-id="21112-128">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="21112-129">Il compilatore unisce le definizioni parziali solo se i relativi percorsi completi sono identici.</span><span class="sxs-lookup"><span data-stu-id="21112-129">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="21112-130">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="21112-130">Recommendations</span></span>  
 <span data-ttu-id="21112-131">Le indicazioni seguenti rappresentano una buona norma di programmazione.</span><span class="sxs-lookup"><span data-stu-id="21112-131">The following recommendations represent good programming practice.</span></span>  
  
-   <span data-ttu-id="21112-132">**Nomi univoci.**</span><span class="sxs-lookup"><span data-stu-id="21112-132">**Unique Names.**</span></span> <span data-ttu-id="21112-133">Quando si dispone di un controllo completo sulla denominazione degli elementi di programmazione, è sempre consigliabile utilizzare nomi univoci ovunque.</span><span class="sxs-lookup"><span data-stu-id="21112-133">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="21112-134">I nomi identici richiedono una qualificazione aggiuntiva e possono rendere difficile leggere il codice.</span><span class="sxs-lookup"><span data-stu-id="21112-134">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="21112-135">Essi possono causare errori difficili da rilevare e risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="21112-135">They can also lead to subtle errors and unexpected results.</span></span>  
  
-   <span data-ttu-id="21112-136">**Nome completo.**</span><span class="sxs-lookup"><span data-stu-id="21112-136">**Full Qualification.**</span></span> <span data-ttu-id="21112-137">Quando si lavora con i moduli e altri elementi dello stesso spazio dei nomi, l'approccio più sicuro è utilizzare sempre il nome completo per tutti gli elementi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="21112-137">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="21112-138">Se la promozione del tipo viene annullato per il membro di un modulo e non qualificare completamente tale membro, è possibile accedere inavvertitamente un elemento di programmazione diverso.</span><span class="sxs-lookup"><span data-stu-id="21112-138">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21112-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21112-139">See Also</span></span>  
 [<span data-ttu-id="21112-140">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="21112-140">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [<span data-ttu-id="21112-141">Istruzione Namespace</span><span class="sxs-lookup"><span data-stu-id="21112-141">Namespace Statement</span></span>](../../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="21112-142">Partial</span><span class="sxs-lookup"><span data-stu-id="21112-142">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [<span data-ttu-id="21112-143">Ambito in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="21112-143">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [<span data-ttu-id="21112-144">Procedura: controllare l'ambito di una variabile</span><span class="sxs-lookup"><span data-stu-id="21112-144">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [<span data-ttu-id="21112-145">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="21112-145">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

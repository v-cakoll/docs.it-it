---
title: Differenze tra argomenti modificabili e non modificabili (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: a880ae8c13eebd5d9d325468098e058f58d3fa71
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826665"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="e8a40-102">Differenze tra argomenti modificabili e non modificabili (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8a40-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="e8a40-103">Quando si chiama una routine, in genere passare uno o più argomenti.</span><span class="sxs-lookup"><span data-stu-id="e8a40-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="e8a40-104">Ciascun argomento corrisponde a un elemento di programmazione sottostante.</span><span class="sxs-lookup"><span data-stu-id="e8a40-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="e8a40-105">Gli elementi sottostanti sia gli argomenti stessi possono essere modificabili o meno.</span><span class="sxs-lookup"><span data-stu-id="e8a40-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="e8a40-106">Elementi modificabili e non modificabili</span><span class="sxs-lookup"><span data-stu-id="e8a40-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="e8a40-107">Un elemento di programmazione può essere un' *elemento modificabile*, che può essere modificata, o una *non è modificabile*, che ha un valore fisso dopo che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="e8a40-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="e8a40-108">La tabella seguente elenca gli elementi di programmazione modificabili e non modificabili.</span><span class="sxs-lookup"><span data-stu-id="e8a40-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="e8a40-109">Elementi modificabili</span><span class="sxs-lookup"><span data-stu-id="e8a40-109">Modifiable elements</span></span>|<span data-ttu-id="e8a40-110">Elementi non modificabili</span><span class="sxs-lookup"><span data-stu-id="e8a40-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="e8a40-111">Le variabili locali (dichiarate all'interno di procedure), incluse le variabili di oggetto, ad eccezione di sola lettura</span><span class="sxs-lookup"><span data-stu-id="e8a40-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="e8a40-112">Le proprietà, campi e le variabili di sola lettura</span><span class="sxs-lookup"><span data-stu-id="e8a40-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="e8a40-113">Campi (variabili membro delle classi, moduli e le strutture), ad eccezione di sola lettura</span><span class="sxs-lookup"><span data-stu-id="e8a40-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="e8a40-114">Valori letterali e costanti</span><span class="sxs-lookup"><span data-stu-id="e8a40-114">Constants and literals</span></span>|  
|<span data-ttu-id="e8a40-115">Proprietà, ad eccezione di sola lettura</span><span class="sxs-lookup"><span data-stu-id="e8a40-115">Properties, except for read-only</span></span>|<span data-ttu-id="e8a40-116">Membri dell'enumerazione</span><span class="sxs-lookup"><span data-stu-id="e8a40-116">Enumeration members</span></span>|  
|<span data-ttu-id="e8a40-117">Elementi della matrice</span><span class="sxs-lookup"><span data-stu-id="e8a40-117">Array elements</span></span>|<span data-ttu-id="e8a40-118">Espressioni (anche se i relativi elementi sono modificabili)</span><span class="sxs-lookup"><span data-stu-id="e8a40-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="e8a40-119">Argomenti modificabili e</span><span class="sxs-lookup"><span data-stu-id="e8a40-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="e8a40-120">Oggetto *modificabile argomento* è un attributo con un elemento sottostante modificabile.</span><span class="sxs-lookup"><span data-stu-id="e8a40-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="e8a40-121">Il codice chiamante può archiviare un valore nuovo in qualsiasi momento, e se si passa l'argomento [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), il codice nella procedura possa anche modificare l'elemento sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="e8a40-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="e8a40-122">Oggetto *argomento non è modificabile* non contiene un elemento sottostante non modificabile o è passato [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="e8a40-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="e8a40-123">La procedura non è possibile modificare l'elemento sottostante nel codice chiamante, anche se si tratta di un elemento modificabile.</span><span class="sxs-lookup"><span data-stu-id="e8a40-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="e8a40-124">Se si tratta di un elemento non è modificabile, il codice chiama non può modificarlo.</span><span class="sxs-lookup"><span data-stu-id="e8a40-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="e8a40-125">La routine chiamata potrebbe modificare la copia locale di un argomento non è modificabile, ma tale modifica non ha effetto sull'elemento sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="e8a40-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a40-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8a40-126">See also</span></span>

- [<span data-ttu-id="e8a40-127">Routine</span><span class="sxs-lookup"><span data-stu-id="e8a40-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e8a40-128">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="e8a40-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e8a40-129">Procedura: Passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="e8a40-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="e8a40-130">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="e8a40-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="e8a40-131">Differenze tra il passaggio di un argomento per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="e8a40-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="e8a40-132">Procedura: Modificare il valore di un argomento di routine</span><span class="sxs-lookup"><span data-stu-id="e8a40-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="e8a40-133">Procedura: Proteggere un argomento di routine modifica del valore</span><span class="sxs-lookup"><span data-stu-id="e8a40-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="e8a40-134">Procedura: Forzare un argomento da passare per valore</span><span class="sxs-lookup"><span data-stu-id="e8a40-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="e8a40-135">Passaggio di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="e8a40-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="e8a40-136">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="e8a40-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)

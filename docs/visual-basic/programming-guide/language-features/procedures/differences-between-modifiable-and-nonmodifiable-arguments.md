---
title: Differenze tra argomenti modificabili e non modificabili
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: 733f92cc2cdaa6e923c57649774ceb64de172c18
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403343"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="18200-102">Differenze tra argomenti modificabili e non modificabili (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18200-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="18200-103">Quando si chiama una routine, in genere si passa uno o più argomenti.</span><span class="sxs-lookup"><span data-stu-id="18200-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="18200-104">Ogni argomento corrisponde a un elemento di programmazione sottostante.</span><span class="sxs-lookup"><span data-stu-id="18200-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="18200-105">Sia gli elementi sottostanti che gli argomenti possono essere modificabili o non modificabili.</span><span class="sxs-lookup"><span data-stu-id="18200-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="18200-106">Elementi modificabili e non modificabili</span><span class="sxs-lookup"><span data-stu-id="18200-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="18200-107">Un elemento di programmazione può essere un *elemento modificabile*, il cui valore può essere modificato o un *elemento non modificabile*, che ha un valore fisso dopo che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="18200-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="18200-108">Nella tabella seguente sono elencati gli elementi di programmazione modificabili e non modificabili.</span><span class="sxs-lookup"><span data-stu-id="18200-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="18200-109">Elementi modificabili</span><span class="sxs-lookup"><span data-stu-id="18200-109">Modifiable elements</span></span>|<span data-ttu-id="18200-110">Elementi non modificabili</span><span class="sxs-lookup"><span data-stu-id="18200-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="18200-111">Variabili locali (dichiarate all'interno di procedure), incluse le variabili oggetto, ad eccezione di sola lettura</span><span class="sxs-lookup"><span data-stu-id="18200-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="18200-112">Variabili, campi e proprietà di sola lettura</span><span class="sxs-lookup"><span data-stu-id="18200-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="18200-113">Campi (variabili membro di moduli, classi e strutture), ad eccezione di sola lettura</span><span class="sxs-lookup"><span data-stu-id="18200-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="18200-114">Costanti e valori letterali</span><span class="sxs-lookup"><span data-stu-id="18200-114">Constants and literals</span></span>|  
|<span data-ttu-id="18200-115">Proprietà, ad eccezione di sola lettura</span><span class="sxs-lookup"><span data-stu-id="18200-115">Properties, except for read-only</span></span>|<span data-ttu-id="18200-116">Membri dell'enumerazione</span><span class="sxs-lookup"><span data-stu-id="18200-116">Enumeration members</span></span>|  
|<span data-ttu-id="18200-117">Elementi di matrice</span><span class="sxs-lookup"><span data-stu-id="18200-117">Array elements</span></span>|<span data-ttu-id="18200-118">Espressioni (anche se i relativi elementi sono modificabili)</span><span class="sxs-lookup"><span data-stu-id="18200-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="18200-119">Argomenti modificabili e non modificabili</span><span class="sxs-lookup"><span data-stu-id="18200-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="18200-120">Un *argomento modificabile* è uno con un elemento sottostante modificabile.</span><span class="sxs-lookup"><span data-stu-id="18200-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="18200-121">Il codice chiamante può archiviare un nuovo valore in qualsiasi momento e, se si passa l'argomento [ByRef](../../../language-reference/modifiers/byref.md), il codice nella procedura può anche modificare l'elemento sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="18200-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="18200-122">Un *argomento non modificabile* presenta un elemento sottostante non modificabile o viene passato [ByVal](../../../language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="18200-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="18200-123">La routine non può modificare l'elemento sottostante nel codice chiamante, anche se è un elemento modificabile.</span><span class="sxs-lookup"><span data-stu-id="18200-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="18200-124">Se è un elemento non modificabile, il codice chiamante non può modificarlo.</span><span class="sxs-lookup"><span data-stu-id="18200-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="18200-125">La procedura chiamata potrebbe modificare la copia locale di un argomento non modificabile, ma la modifica non influisce sull'elemento sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="18200-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18200-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18200-126">See also</span></span>

- [<span data-ttu-id="18200-127">Procedure</span><span class="sxs-lookup"><span data-stu-id="18200-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="18200-128">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="18200-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="18200-129">Procedura: passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="18200-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="18200-130">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="18200-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="18200-131">Differenze tra il passaggio di un argomento per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="18200-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="18200-132">Procedura: cambiare il valore di un argomento di routine</span><span class="sxs-lookup"><span data-stu-id="18200-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="18200-133">Procedura: impedire la modifica del valore di un argomento di una routine</span><span class="sxs-lookup"><span data-stu-id="18200-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="18200-134">Procedura: forzare il passaggio di un argomento per valore</span><span class="sxs-lookup"><span data-stu-id="18200-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="18200-135">Passaggio di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="18200-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="18200-136">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="18200-136">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)

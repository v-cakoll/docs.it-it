---
title: Static (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: de4f67fc5b60de48383a8ca886cff02b03830318
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781186"
---
# <a name="static-visual-basic"></a><span data-ttu-id="912a2-102">Static (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="912a2-102">Static (Visual Basic)</span></span>
<span data-ttu-id="912a2-103">Specifica che uno o più variabili locali dichiarate devono continuare a esistere e mantengono i valori più recenti dopo la terminazione della procedura in cui sono dichiarate.</span><span class="sxs-lookup"><span data-stu-id="912a2-103">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="912a2-104">Note</span><span class="sxs-lookup"><span data-stu-id="912a2-104">Remarks</span></span>  
 <span data-ttu-id="912a2-105">In genere, una variabile locale in una procedura cessa di esistere, non appena la routine verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="912a2-105">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="912a2-106">Una variabile statica continua a esistere e mantiene il valore più recente.</span><span class="sxs-lookup"><span data-stu-id="912a2-106">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="912a2-107">La volta successiva che il codice chiama la procedura, la variabile non viene reinizializzata e contiene ancora il valore più recente che è assegnato a esso.</span><span class="sxs-lookup"><span data-stu-id="912a2-107">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="912a2-108">Una variabile statica continua a esistere per la durata della classe o modulo in cui è definito.</span><span class="sxs-lookup"><span data-stu-id="912a2-108">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="912a2-109">Regole</span><span class="sxs-lookup"><span data-stu-id="912a2-109">Rules</span></span>  
  
- <span data-ttu-id="912a2-110">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="912a2-110">**Declaration Context.**</span></span> <span data-ttu-id="912a2-111">È possibile usare `Static` solo in variabili locali.</span><span class="sxs-lookup"><span data-stu-id="912a2-111">You can use `Static` only on local variables.</span></span> <span data-ttu-id="912a2-112">Ciò significa che il contesto della dichiarazione per un `Static` variabile deve essere una routine o un blocco in una routine, e non può essere un file di origine, lo spazio dei nomi, classe, struttura o modulo.</span><span class="sxs-lookup"><span data-stu-id="912a2-112">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="912a2-113">Non è possibile usare `Static` all'interno di una routine di struttura.</span><span class="sxs-lookup"><span data-stu-id="912a2-113">You cannot use `Static` inside a structure procedure.</span></span>  
  
- <span data-ttu-id="912a2-114">I tipi di dati di `Static` non è possibile dedurre le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="912a2-114">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="912a2-115">Per altre informazioni, vedere [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="912a2-115">For more information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
- <span data-ttu-id="912a2-116">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="912a2-116">**Combined Modifiers.**</span></span> <span data-ttu-id="912a2-117">Non è possibile specificare `Static` assieme `ReadOnly`, `Shadows`, o `Shared` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="912a2-117">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="912a2-118">Comportamento</span><span class="sxs-lookup"><span data-stu-id="912a2-118">Behavior</span></span>  
 <span data-ttu-id="912a2-119">Quando si dichiara una variabile statica in un `Shared` procedure, solo una copia della variabile statica è disponibile per l'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="912a2-119">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="912a2-120">Si chiama un `Shared` nome procedura utilizzando la classe, non una variabile che punta a un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="912a2-120">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="912a2-121">Quando si dichiara una variabile statica in una routine che non sia `Shared`, solo una copia della variabile è disponibile per ogni istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="912a2-121">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="912a2-122">Si chiama una routine non condivise usando una variabile che punta a una specifica istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="912a2-122">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="912a2-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="912a2-123">Example</span></span>  
 <span data-ttu-id="912a2-124">L'esempio seguente illustra l'uso di `Static`.</span><span class="sxs-lookup"><span data-stu-id="912a2-124">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 <span data-ttu-id="912a2-125">Il `Static` variabile `totalSales` viene inizializzata su 0 solo una volta.</span><span class="sxs-lookup"><span data-stu-id="912a2-125">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="912a2-126">Ogni volta che si immette `updateSales`, `totalSales` ha ancora il valore più recente che viene calcolata per tale.</span><span class="sxs-lookup"><span data-stu-id="912a2-126">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="912a2-127">Il `Static` modificatore può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="912a2-127">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="912a2-128">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="912a2-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="912a2-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="912a2-129">See also</span></span>

- [<span data-ttu-id="912a2-130">Shadows</span><span class="sxs-lookup"><span data-stu-id="912a2-130">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="912a2-131">Shared</span><span class="sxs-lookup"><span data-stu-id="912a2-131">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="912a2-132">Durata in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="912a2-132">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="912a2-133">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="912a2-133">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="912a2-134">Strutture</span><span class="sxs-lookup"><span data-stu-id="912a2-134">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="912a2-135">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="912a2-135">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="912a2-136">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="912a2-136">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)

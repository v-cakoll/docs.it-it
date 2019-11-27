---
title: Static
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: f020756466888f51298abb423997906ddc7caff7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350753"
---
# <a name="static-visual-basic"></a><span data-ttu-id="a68c5-102">Static (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a68c5-102">Static (Visual Basic)</span></span>
<span data-ttu-id="a68c5-103">Specifica che una o più variabili locali dichiarate devono continuare a esistere e mantenere i valori più recenti dopo la terminazione della routine in cui sono dichiarate.</span><span class="sxs-lookup"><span data-stu-id="a68c5-103">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a68c5-104">Note</span><span class="sxs-lookup"><span data-stu-id="a68c5-104">Remarks</span></span>  
 <span data-ttu-id="a68c5-105">In genere, una variabile locale di una routine cessa di esistere non appena la procedura viene arrestata.</span><span class="sxs-lookup"><span data-stu-id="a68c5-105">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="a68c5-106">Una variabile statica continua a esistere e mantiene il valore più recente.</span><span class="sxs-lookup"><span data-stu-id="a68c5-106">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="a68c5-107">Alla successiva chiamata della stored procedure da parte del codice, la variabile non viene reinizializzata e continua a contenere l'ultimo valore assegnato.</span><span class="sxs-lookup"><span data-stu-id="a68c5-107">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="a68c5-108">Una variabile statica continua a esistere per la durata della classe o del modulo in cui è definita.</span><span class="sxs-lookup"><span data-stu-id="a68c5-108">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a68c5-109">Regole</span><span class="sxs-lookup"><span data-stu-id="a68c5-109">Rules</span></span>  
  
- <span data-ttu-id="a68c5-110">**Contesto di dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="a68c5-110">**Declaration Context.**</span></span> <span data-ttu-id="a68c5-111">È possibile utilizzare `Static` solo su variabili locali.</span><span class="sxs-lookup"><span data-stu-id="a68c5-111">You can use `Static` only on local variables.</span></span> <span data-ttu-id="a68c5-112">Ciò significa che il contesto di dichiarazione per una variabile di `Static` deve essere una routine o un blocco in una routine e non può essere un file di origine, uno spazio dei nomi, una classe, una struttura o un modulo.</span><span class="sxs-lookup"><span data-stu-id="a68c5-112">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="a68c5-113">Non è possibile utilizzare `Static` all'interno di una routine della struttura.</span><span class="sxs-lookup"><span data-stu-id="a68c5-113">You cannot use `Static` inside a structure procedure.</span></span>  
  
- <span data-ttu-id="a68c5-114">Non è possibile dedurre i tipi di dati di `Static` variabili locali.</span><span class="sxs-lookup"><span data-stu-id="a68c5-114">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="a68c5-115">Per altre informazioni, vedere [inferenza dei tipi locali](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="a68c5-115">For more information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
- <span data-ttu-id="a68c5-116">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="a68c5-116">**Combined Modifiers.**</span></span> <span data-ttu-id="a68c5-117">Non è possibile specificare `Static` insieme `ReadOnly`, `Shadows`o `Shared` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="a68c5-117">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="a68c5-118">Comportamento</span><span class="sxs-lookup"><span data-stu-id="a68c5-118">Behavior</span></span>  
 <span data-ttu-id="a68c5-119">Quando si dichiara una variabile statica in una procedura di `Shared`, è disponibile solo una copia della variabile statica per l'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="a68c5-119">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="a68c5-120">È possibile chiamare una procedura `Shared` usando il nome della classe, non una variabile che punta a un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="a68c5-120">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="a68c5-121">Quando si dichiara una variabile statica in una routine che non è `Shared`, è disponibile solo una copia della variabile per ogni istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="a68c5-121">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="a68c5-122">Una routine non condivisa viene chiamata utilizzando una variabile che punta a un'istanza specifica della classe.</span><span class="sxs-lookup"><span data-stu-id="a68c5-122">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a68c5-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="a68c5-123">Example</span></span>  
 <span data-ttu-id="a68c5-124">L'esempio seguente illustra l'uso di `Static`.</span><span class="sxs-lookup"><span data-stu-id="a68c5-124">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 <span data-ttu-id="a68c5-125">La variabile `Static` `totalSales` viene inizializzata su 0 solo una volta.</span><span class="sxs-lookup"><span data-stu-id="a68c5-125">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="a68c5-126">Ogni volta che si immette `updateSales`, `totalSales` dispone ancora del valore più recente calcolato.</span><span class="sxs-lookup"><span data-stu-id="a68c5-126">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="a68c5-127">Il modificatore `Static` può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="a68c5-127">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="a68c5-128">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="a68c5-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="a68c5-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a68c5-129">See also</span></span>

- [<span data-ttu-id="a68c5-130">Shadows</span><span class="sxs-lookup"><span data-stu-id="a68c5-130">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="a68c5-131">Shared</span><span class="sxs-lookup"><span data-stu-id="a68c5-131">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="a68c5-132">Durata in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a68c5-132">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="a68c5-133">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="a68c5-133">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="a68c5-134">Strutture</span><span class="sxs-lookup"><span data-stu-id="a68c5-134">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a68c5-135">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="a68c5-135">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="a68c5-136">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="a68c5-136">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)

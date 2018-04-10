---
title: Static (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e08f46076281e766a5bc0b99cd61fee9cd41ece5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="static-visual-basic"></a><span data-ttu-id="ae066-102">Static (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae066-102">Static (Visual Basic)</span></span>
<span data-ttu-id="ae066-103">Specifica che uno o più variabili locali dichiarate devono continuare a esistere e conservano i valori più recenti dopo il termine della procedura in cui sono dichiarati.</span><span class="sxs-lookup"><span data-stu-id="ae066-103">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae066-104">Note</span><span class="sxs-lookup"><span data-stu-id="ae066-104">Remarks</span></span>  
 <span data-ttu-id="ae066-105">In genere, una variabile locale in una routine cessa di esistere non appena la routine verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="ae066-105">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="ae066-106">Una variabile statica continua a esistere e mantiene il valore più recente.</span><span class="sxs-lookup"><span data-stu-id="ae066-106">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="ae066-107">La variabile non viene reinizializzata alla successiva che il codice chiama la routine, e contiene ancora il valore più recente che è assegnato.</span><span class="sxs-lookup"><span data-stu-id="ae066-107">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="ae066-108">Una variabile statica continua a esistere per la durata della classe o modulo in cui è definita in.</span><span class="sxs-lookup"><span data-stu-id="ae066-108">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ae066-109">Regole</span><span class="sxs-lookup"><span data-stu-id="ae066-109">Rules</span></span>  
  
-   <span data-ttu-id="ae066-110">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="ae066-110">**Declaration Context.**</span></span> <span data-ttu-id="ae066-111">È possibile utilizzare `Static` solo su variabili locali.</span><span class="sxs-lookup"><span data-stu-id="ae066-111">You can use `Static` only on local variables.</span></span> <span data-ttu-id="ae066-112">Ciò significa che il contesto della dichiarazione per un `Static` variabile deve essere una routine o un blocco in una stored procedure e non può trattarsi di un file di origine, lo spazio dei nomi, classe, struttura o modulo.</span><span class="sxs-lookup"><span data-stu-id="ae066-112">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="ae066-113">Non è possibile utilizzare `Static` all'interno di una routine di struttura.</span><span class="sxs-lookup"><span data-stu-id="ae066-113">You cannot use `Static` inside a structure procedure.</span></span>  
  
-   <span data-ttu-id="ae066-114">I tipi di dati di `Static` non è possibile dedurre le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="ae066-114">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="ae066-115">Per ulteriori informazioni, vedere [locale l'inferenza del tipo](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="ae066-115">For more information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
-   <span data-ttu-id="ae066-116">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="ae066-116">**Combined Modifiers.**</span></span> <span data-ttu-id="ae066-117">Non è possibile specificare `Static` con `ReadOnly`, `Shadows`, o `Shared` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="ae066-117">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="ae066-118">Comportamento</span><span class="sxs-lookup"><span data-stu-id="ae066-118">Behavior</span></span>  
 <span data-ttu-id="ae066-119">Quando si dichiara una variabile statica in un `Shared` procedure, solo una copia della variabile statica è disponibile per l'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="ae066-119">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="ae066-120">Si chiama un `Shared` nome procedura utilizzando la classe, non una variabile che punta a un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="ae066-120">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="ae066-121">Quando si dichiara una variabile statica in una routine che non è `Shared`, solo una copia della variabile è disponibile per ogni istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="ae066-121">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="ae066-122">Si chiama una routine non condivisa tramite una variabile che punta a una specifica istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="ae066-122">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae066-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="ae066-123">Example</span></span>  
 <span data-ttu-id="ae066-124">L'esempio seguente illustra l'uso di `Static`.</span><span class="sxs-lookup"><span data-stu-id="ae066-124">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](../../../visual-basic/language-reference/codesnippet/VisualBasic/static_1.vb)]  
  
 <span data-ttu-id="ae066-125">Il `Static` variabile `totalSales` viene inizializzata su 0, solo una volta.</span><span class="sxs-lookup"><span data-stu-id="ae066-125">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="ae066-126">Ogni volta che si immette `updateSales`, `totalSales` presenta ancora il valore più recente è calcolato.</span><span class="sxs-lookup"><span data-stu-id="ae066-126">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="ae066-127">Il `Static` modificatore può essere utilizzato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="ae066-127">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="ae066-128">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="ae066-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ae066-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae066-129">See Also</span></span>  
 [<span data-ttu-id="ae066-130">Shadows</span><span class="sxs-lookup"><span data-stu-id="ae066-130">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="ae066-131">Shared</span><span class="sxs-lookup"><span data-stu-id="ae066-131">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="ae066-132">Durata in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ae066-132">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [<span data-ttu-id="ae066-133">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="ae066-133">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="ae066-134">Strutture</span><span class="sxs-lookup"><span data-stu-id="ae066-134">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="ae066-135">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="ae066-135">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="ae066-136">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="ae066-136">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)

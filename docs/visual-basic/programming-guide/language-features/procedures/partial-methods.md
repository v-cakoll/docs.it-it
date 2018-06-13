---
title: Metodi parziali (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
ms.openlocfilehash: a1708c1d953a60429c1bd87fd858da5c50a3e759
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651596"
---
# <a name="partial-methods-visual-basic"></a><span data-ttu-id="3034f-102">Metodi parziali (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3034f-102">Partial Methods (Visual Basic)</span></span>
<span data-ttu-id="3034f-103">Metodi parziali consentono agli sviluppatori di inserire la logica personalizzata nel codice.</span><span class="sxs-lookup"><span data-stu-id="3034f-103">Partial methods enable developers to insert custom logic into code.</span></span> <span data-ttu-id="3034f-104">In genere, il codice è parte di una classe generato da progettazione.</span><span class="sxs-lookup"><span data-stu-id="3034f-104">Typically, the code is part of a designer-generated class.</span></span> <span data-ttu-id="3034f-105">Metodi parziali sono definiti in una classe parziale che viene creata da un generatore di codice e vengono utilizzati frequentemente per fornire la notifica che un elemento è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="3034f-105">Partial methods are defined in a partial class that is created by a code generator, and they are commonly used to provide notification that something has been changed.</span></span> <span data-ttu-id="3034f-106">Consentono allo sviluppatore di specificare un comportamento personalizzato in risposta alla modifica.</span><span class="sxs-lookup"><span data-stu-id="3034f-106">They enable the developer to specify custom behavior in response to the change.</span></span>  
  
 <span data-ttu-id="3034f-107">La finestra di progettazione del generatore di codice definisce solo la firma del metodo e uno o più chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="3034f-107">The designer of the code generator defines only the method signature and one or more calls to the method.</span></span> <span data-ttu-id="3034f-108">Gli sviluppatori possono quindi fornire le implementazioni del metodo, se si desidera personalizzare il comportamento del codice generato.</span><span class="sxs-lookup"><span data-stu-id="3034f-108">Developers can then provide implementations for the method if they want to customize the behavior of the generated code.</span></span> <span data-ttu-id="3034f-109">Quando viene fornita alcuna implementazione, le chiamate al metodo vengono rimossi dal compilatore, risultante in nessun overhead di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="3034f-109">When no implementation is provided, calls to the method are removed by the compiler, resulting in no additional performance overhead.</span></span>  
  
## <a name="declaration"></a><span data-ttu-id="3034f-110">Dichiarazione</span><span class="sxs-lookup"><span data-stu-id="3034f-110">Declaration</span></span>  
 <span data-ttu-id="3034f-111">Il codice generato contrassegna la definizione di un metodo parziale inserendo la parola chiave `Partial` all'inizio della riga della firma.</span><span class="sxs-lookup"><span data-stu-id="3034f-111">The generated code marks the definition of a partial method by placing the keyword `Partial` at the start of the signature line.</span></span>  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 <span data-ttu-id="3034f-112">La definizione deve soddisfare le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3034f-112">The definition must meet the following conditions:</span></span>  
  
-   <span data-ttu-id="3034f-113">Il metodo deve essere un `Sub`, non un `Function`.</span><span class="sxs-lookup"><span data-stu-id="3034f-113">The method must be a `Sub`, not a `Function`.</span></span>  
  
-   <span data-ttu-id="3034f-114">Il corpo del metodo deve essere lasciato vuoto.</span><span class="sxs-lookup"><span data-stu-id="3034f-114">The body of the method must be left empty.</span></span>  
  
-   <span data-ttu-id="3034f-115">Il modificatore di accesso deve essere `Private`.</span><span class="sxs-lookup"><span data-stu-id="3034f-115">The access modifier must be `Private`.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="3034f-116">Implementazione</span><span class="sxs-lookup"><span data-stu-id="3034f-116">Implementation</span></span>  
 <span data-ttu-id="3034f-117">L'implementazione è costituita principalmente nell'inserire il corpo del metodo parziale.</span><span class="sxs-lookup"><span data-stu-id="3034f-117">The implementation consists primarily of filling in the body of the partial method.</span></span> <span data-ttu-id="3034f-118">L'implementazione è in genere in una classe parziale separata dalla definizione e viene scritto da uno sviluppatore che desidera estendere il codice generato.</span><span class="sxs-lookup"><span data-stu-id="3034f-118">The implementation is typically in a separate partial class from the definition, and is written by a developer who wants to extend the generated code.</span></span>  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 <span data-ttu-id="3034f-119">La firma nella dichiarazione consente di duplicare esattamente l'esempio precedente, ma sono possibili variazioni.</span><span class="sxs-lookup"><span data-stu-id="3034f-119">The previous example duplicates the signature in the declaration exactly, but variations are possible.</span></span> <span data-ttu-id="3034f-120">In particolare, è possano aggiungere altri modificatori, ad esempio `Overloads` o `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="3034f-120">In particular, other modifiers can be added, such as `Overloads` or `Overrides`.</span></span> <span data-ttu-id="3034f-121">Un solo `Overrides` modificatore è consentito.</span><span class="sxs-lookup"><span data-stu-id="3034f-121">Only one `Overrides` modifier is permitted.</span></span> <span data-ttu-id="3034f-122">Per ulteriori informazioni sui modificatori di metodo, vedere [istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3034f-122">For more information about method modifiers, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="use"></a><span data-ttu-id="3034f-123">Usa</span><span class="sxs-lookup"><span data-stu-id="3034f-123">Use</span></span>  
 <span data-ttu-id="3034f-124">Si chiama un metodo parziale procedendo come per qualsiasi altro `Sub` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="3034f-124">You call a partial method as you would call any other `Sub` procedure.</span></span> <span data-ttu-id="3034f-125">Se è stato implementato il metodo, gli argomenti vengono valutati e viene eseguito il corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="3034f-125">If the method has been implemented, the arguments are evaluated and the body of the method is executed.</span></span> <span data-ttu-id="3034f-126">Tuttavia, tenere presente che l'implementazione di un metodo parziale è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="3034f-126">However, remember that implementing a partial method is optional.</span></span> <span data-ttu-id="3034f-127">Se non è stato implementato il metodo, una chiamata non ha alcun effetto e non vengono valutate le espressioni passate come argomenti al metodo.</span><span class="sxs-lookup"><span data-stu-id="3034f-127">If the method is not implemented, a call to it has no effect, and expressions passed as arguments to the method are not evaluated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3034f-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="3034f-128">Example</span></span>  
 <span data-ttu-id="3034f-129">In un file denominato Product.Designer.vb, definire un `Product` classe che ha un `Quantity` proprietà.</span><span class="sxs-lookup"><span data-stu-id="3034f-129">In a file named Product.Designer.vb, define a `Product` class that has a `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#4](./codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 <span data-ttu-id="3034f-130">In un file denominato Product. vb, fornire un'implementazione per `QuantityChanged`.</span><span class="sxs-lookup"><span data-stu-id="3034f-130">In a file named Product.vb, provide an implementation for `QuantityChanged`.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#5](./codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 <span data-ttu-id="3034f-131">Infine, nel metodo Main di un progetto, dichiarare un `Product` istanza e fornire un valore iniziale per il relativo `Quantity` proprietà.</span><span class="sxs-lookup"><span data-stu-id="3034f-131">Finally, in the Main method of a project, declare a `Product` instance and provide an initial value for its `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#6](./codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 <span data-ttu-id="3034f-132">Verrà visualizzata una finestra di messaggio che viene visualizzato questo messaggio:</span><span class="sxs-lookup"><span data-stu-id="3034f-132">A message box should appear that displays this message:</span></span>  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a><span data-ttu-id="3034f-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3034f-133">See Also</span></span>  
 [<span data-ttu-id="3034f-134">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="3034f-134">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="3034f-135">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="3034f-135">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="3034f-136">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="3034f-136">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="3034f-137">Partial</span><span class="sxs-lookup"><span data-stu-id="3034f-137">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [<span data-ttu-id="3034f-138">Generazione di codice in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3034f-138">Code Generation in LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [<span data-ttu-id="3034f-139">Aggiunta di logica di business mediante metodi parziali</span><span class="sxs-lookup"><span data-stu-id="3034f-139">Adding Business Logic By Using Partial Methods</span></span>](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)

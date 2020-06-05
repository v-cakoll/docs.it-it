---
title: Metodi parziali
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
ms.openlocfilehash: 61a1398ba7de8dab005fa1e9efa13dc2ba18cc3c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364123"
---
# <a name="partial-methods-visual-basic"></a><span data-ttu-id="cc92b-102">Metodi parziali (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc92b-102">Partial Methods (Visual Basic)</span></span>
<span data-ttu-id="cc92b-103">I metodi parziali consentono agli sviluppatori di inserire logica personalizzata nel codice.</span><span class="sxs-lookup"><span data-stu-id="cc92b-103">Partial methods enable developers to insert custom logic into code.</span></span> <span data-ttu-id="cc92b-104">In genere, il codice fa parte di una classe generata dalla finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="cc92b-104">Typically, the code is part of a designer-generated class.</span></span> <span data-ttu-id="cc92b-105">I metodi parziali sono definiti in una classe parziale creata da un generatore di codice e vengono comunemente usati per fornire una notifica che è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="cc92b-105">Partial methods are defined in a partial class that is created by a code generator, and they are commonly used to provide notification that something has been changed.</span></span> <span data-ttu-id="cc92b-106">Consentono allo sviluppatore di specificare un comportamento personalizzato in risposta alla modifica.</span><span class="sxs-lookup"><span data-stu-id="cc92b-106">They enable the developer to specify custom behavior in response to the change.</span></span>  
  
 <span data-ttu-id="cc92b-107">La finestra di progettazione del generatore di codice definisce solo la firma del metodo e una o più chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="cc92b-107">The designer of the code generator defines only the method signature and one or more calls to the method.</span></span> <span data-ttu-id="cc92b-108">Gli sviluppatori possono quindi fornire implementazioni per il metodo se desiderano personalizzare il comportamento del codice generato.</span><span class="sxs-lookup"><span data-stu-id="cc92b-108">Developers can then provide implementations for the method if they want to customize the behavior of the generated code.</span></span> <span data-ttu-id="cc92b-109">Quando non viene fornita alcuna implementazione, le chiamate al metodo vengono rimosse dal compilatore, causando un sovraccarico delle prestazioni aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="cc92b-109">When no implementation is provided, calls to the method are removed by the compiler, resulting in no additional performance overhead.</span></span>  
  
## <a name="declaration"></a><span data-ttu-id="cc92b-110">Dichiarazione</span><span class="sxs-lookup"><span data-stu-id="cc92b-110">Declaration</span></span>  
 <span data-ttu-id="cc92b-111">Il codice generato contrassegna la definizione di un metodo parziale inserendo la parola chiave `Partial` all'inizio della riga della firma.</span><span class="sxs-lookup"><span data-stu-id="cc92b-111">The generated code marks the definition of a partial method by placing the keyword `Partial` at the start of the signature line.</span></span>  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 <span data-ttu-id="cc92b-112">La definizione deve soddisfare le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc92b-112">The definition must meet the following conditions:</span></span>  
  
- <span data-ttu-id="cc92b-113">Il metodo deve essere un oggetto `Sub` , non un oggetto `Function` .</span><span class="sxs-lookup"><span data-stu-id="cc92b-113">The method must be a `Sub`, not a `Function`.</span></span>  
  
- <span data-ttu-id="cc92b-114">Il corpo del metodo deve essere lasciato vuoto.</span><span class="sxs-lookup"><span data-stu-id="cc92b-114">The body of the method must be left empty.</span></span>  
  
- <span data-ttu-id="cc92b-115">Il modificatore di accesso deve essere `Private` .</span><span class="sxs-lookup"><span data-stu-id="cc92b-115">The access modifier must be `Private`.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="cc92b-116">Implementazione</span><span class="sxs-lookup"><span data-stu-id="cc92b-116">Implementation</span></span>  
 <span data-ttu-id="cc92b-117">L'implementazione consiste principalmente nel compilare il corpo del metodo parziale.</span><span class="sxs-lookup"><span data-stu-id="cc92b-117">The implementation consists primarily of filling in the body of the partial method.</span></span> <span data-ttu-id="cc92b-118">L'implementazione si trova in genere in una classe parziale separata dalla definizione e viene scritta da uno sviluppatore che desidera estendere il codice generato.</span><span class="sxs-lookup"><span data-stu-id="cc92b-118">The implementation is typically in a separate partial class from the definition, and is written by a developer who wants to extend the generated code.</span></span>  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 <span data-ttu-id="cc92b-119">Nell'esempio precedente la firma è stata duplicata esattamente nella dichiarazione, ma le variazioni sono possibili.</span><span class="sxs-lookup"><span data-stu-id="cc92b-119">The previous example duplicates the signature in the declaration exactly, but variations are possible.</span></span> <span data-ttu-id="cc92b-120">In particolare, è possibile aggiungere altri modificatori, ad esempio `Overloads` o `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="cc92b-120">In particular, other modifiers can be added, such as `Overloads` or `Overrides`.</span></span> <span data-ttu-id="cc92b-121">`Overrides`È consentito un solo modificatore.</span><span class="sxs-lookup"><span data-stu-id="cc92b-121">Only one `Overrides` modifier is permitted.</span></span> <span data-ttu-id="cc92b-122">Per ulteriori informazioni sui modificatori di metodo, vedere [istruzione secondaria](../../../language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cc92b-122">For more information about method modifiers, see [Sub Statement](../../../language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="use"></a><span data-ttu-id="cc92b-123">Uso</span><span class="sxs-lookup"><span data-stu-id="cc92b-123">Use</span></span>  
 <span data-ttu-id="cc92b-124">È possibile chiamare un metodo parziale come si farebbe per qualsiasi altra `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="cc92b-124">You call a partial method as you would call any other `Sub` procedure.</span></span> <span data-ttu-id="cc92b-125">Se il metodo è stato implementato, gli argomenti vengono valutati e viene eseguito il corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="cc92b-125">If the method has been implemented, the arguments are evaluated and the body of the method is executed.</span></span> <span data-ttu-id="cc92b-126">Tuttavia, tenere presente che l'implementazione di un metodo parziale è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="cc92b-126">However, remember that implementing a partial method is optional.</span></span> <span data-ttu-id="cc92b-127">Se il metodo non è implementato, una chiamata non ha alcun effetto e le espressioni passate come argomenti al metodo non vengono valutate.</span><span class="sxs-lookup"><span data-stu-id="cc92b-127">If the method is not implemented, a call to it has no effect, and expressions passed as arguments to the method are not evaluated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc92b-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="cc92b-128">Example</span></span>  
 <span data-ttu-id="cc92b-129">In un file denominato Product. designer. vb definire una `Product` classe con una `Quantity` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="cc92b-129">In a file named Product.Designer.vb, define a `Product` class that has a `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#4)]  
  
 <span data-ttu-id="cc92b-130">In un file denominato Product. vb fornire un'implementazione di per `QuantityChanged` .</span><span class="sxs-lookup"><span data-stu-id="cc92b-130">In a file named Product.vb, provide an implementation for `QuantityChanged`.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#5)]  
  
 <span data-ttu-id="cc92b-131">Infine, nel metodo Main di un progetto, dichiarare un' `Product` istanza e fornire un valore iniziale per la `Quantity` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="cc92b-131">Finally, in the Main method of a project, declare a `Product` instance and provide an initial value for its `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#6)]  
  
 <span data-ttu-id="cc92b-132">Verrà visualizzata una finestra di messaggio in cui viene visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="cc92b-132">A message box should appear that displays this message:</span></span>  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a><span data-ttu-id="cc92b-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc92b-133">See also</span></span>

- [<span data-ttu-id="cc92b-134">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="cc92b-134">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="cc92b-135">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="cc92b-135">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="cc92b-136">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="cc92b-136">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="cc92b-137">Partial</span><span class="sxs-lookup"><span data-stu-id="cc92b-137">Partial</span></span>](../../../language-reference/modifiers/partial.md)
- [<span data-ttu-id="cc92b-138">Generazione di codice in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="cc92b-138">Code Generation in LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="cc92b-139">Aggiunta di logica di business mediante metodi parziali</span><span class="sxs-lookup"><span data-stu-id="cc92b-139">Adding Business Logic By Using Partial Methods</span></span>](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)

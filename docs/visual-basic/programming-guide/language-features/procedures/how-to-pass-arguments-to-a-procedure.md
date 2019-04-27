---
title: 'Procedura: Passare argomenti a una routine (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
ms.openlocfilehash: 012ad8e6229958575030ee820a3b0b79cc50facc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863441"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="cf929-102">Procedura: Passare argomenti a una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf929-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="cf929-103">Quando si chiama una routine, si seguono il nome della routine con un elenco di argomenti racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="cf929-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="cf929-104">Viene fornito un argomento corrispondente a ogni parametro obbligatorio, definisce la procedura e, facoltativamente, è possibile specificare argomenti per il `Optional` parametri.</span><span class="sxs-lookup"><span data-stu-id="cf929-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="cf929-105">Se non si fornisce un `Optional` parametro nella chiamata, è necessario includere una virgola per contrassegnarne la posizione nell'elenco di argomenti, se viene fornito alcun argomento successivo.</span><span class="sxs-lookup"><span data-stu-id="cf929-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="cf929-106">Se si prevede di passare un argomento di un tipo di dati diverso da quello del parametro corrispondente, ad esempio `Byte` al `String`, è possibile impostare l'opzione di controllo del tipo ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) per `Off`.</span><span class="sxs-lookup"><span data-stu-id="cf929-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="cf929-107">Se `Option Strict` è `On`, è necessario utilizzare parole chiave di conversione esplicita o le conversioni di ampliamento.</span><span class="sxs-lookup"><span data-stu-id="cf929-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="cf929-108">Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) e [funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="cf929-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="cf929-109">Per altre informazioni, vedere [parametri delle Procedure e argomenti](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="cf929-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="cf929-110">Per passare uno o più argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="cf929-110">To pass one or more arguments to a procedure</span></span>  
  
1. <span data-ttu-id="cf929-111">Nell'istruzione di chiamata, inserire il nome della routine tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="cf929-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2. <span data-ttu-id="cf929-112">All'interno delle parentesi, inserire un elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="cf929-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="cf929-113">Includere un argomento per ogni parametro obbligatorio, che definisce la routine e gli argomenti, separarli con virgole.</span><span class="sxs-lookup"><span data-stu-id="cf929-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3. <span data-ttu-id="cf929-114">Assicurarsi che ogni argomento è un'espressione valida che restituisce un tipo di dati convertibile nel tipo di routine definisce per il parametro corrispondente.</span><span class="sxs-lookup"><span data-stu-id="cf929-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4. <span data-ttu-id="cf929-115">Se un parametro viene definito come [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md), è possibile includerlo nell'elenco di argomenti oppure ometterlo.</span><span class="sxs-lookup"><span data-stu-id="cf929-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="cf929-116">Se viene omesso, la routine utilizza il valore predefinito definito per tale parametro.</span><span class="sxs-lookup"><span data-stu-id="cf929-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5. <span data-ttu-id="cf929-117">Se si omette un argomento per un `Optional` parametro ed è presente un altro parametro dopo di esso nell'elenco dei parametri, è possibile contrassegnare la posizione dell'argomento omesso da una virgola aggiuntiva nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="cf929-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="cf929-118">L'esempio seguente chiama il Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> (funzione).</span><span class="sxs-lookup"><span data-stu-id="cf929-118">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     <span data-ttu-id="cf929-119">Nell'esempio precedente specifica il primo argomento obbligatorio, ovvero la stringa di messaggio da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="cf929-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="cf929-120">Omette un argomento per il secondo parametro facoltativo che specifica i pulsanti da visualizzare nella finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="cf929-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="cf929-121">Poiché la chiamata non fornisce alcun valore, `MsgBox` Usa il valore predefinito `MsgBoxStyle.OKOnly`, che consente di visualizzare solo un **OK** pulsante.</span><span class="sxs-lookup"><span data-stu-id="cf929-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="cf929-122">La seconda virgola nell'elenco di argomenti contrassegna la posizione del secondo argomento viene omesso e l'ultima stringa viene passata al terzo parametro facoltativo di `MsgBox`, ovvero il testo da visualizzare nella barra del titolo.</span><span class="sxs-lookup"><span data-stu-id="cf929-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf929-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf929-123">See also</span></span>

- [<span data-ttu-id="cf929-124">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="cf929-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="cf929-125">Routine Function</span><span class="sxs-lookup"><span data-stu-id="cf929-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="cf929-126">Routine Property</span><span class="sxs-lookup"><span data-stu-id="cf929-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="cf929-127">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="cf929-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="cf929-128">Procedura: Definire un parametro per una routine</span><span class="sxs-lookup"><span data-stu-id="cf929-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="cf929-129">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="cf929-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="cf929-130">Routine ricorsive</span><span class="sxs-lookup"><span data-stu-id="cf929-130">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="cf929-131">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="cf929-131">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="cf929-132">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="cf929-132">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="cf929-133">Programmazione orientata a oggetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf929-133">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)

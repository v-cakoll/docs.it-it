---
title: 'Procedura: passare argomenti a una routine'
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
ms.openlocfilehash: 903e05facccd1f2afdf4bb51b200531feb64aa79
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387777"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="d2ca8-102">Procedura: passare argomenti a una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2ca8-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="d2ca8-103">Quando si chiama una routine, il nome della procedura viene seguito da un elenco di argomenti racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="d2ca8-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="d2ca8-104">Si fornisce un argomento corrispondente a ogni parametro obbligatorio definito dalla procedura ed è possibile specificare facoltativamente argomenti per i `Optional` parametri.</span><span class="sxs-lookup"><span data-stu-id="d2ca8-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="d2ca8-105">Se non si specifica un `Optional` parametro nella chiamata, è necessario includere una virgola per contrassegnare la posizione nell'elenco di argomenti se si specificano gli argomenti successivi.</span><span class="sxs-lookup"><span data-stu-id="d2ca8-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="d2ca8-106">Se si intende passare un argomento di un tipo di dati diverso da quello del parametro corrispondente, ad esempio `Byte` a `String` , è possibile impostare l'opzione di controllo del tipo ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) su `Off` .</span><span class="sxs-lookup"><span data-stu-id="d2ca8-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="d2ca8-107">Se `Option Strict` è `On` , è necessario usare le conversioni verso un tipo di conversione più ampio o le parole chiave di conversione esplicita.</span><span class="sxs-lookup"><span data-stu-id="d2ca8-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="d2ca8-108">Per altre informazioni, vedere [conversioni](../data-types/widening-and-narrowing-conversions.md) verso un tipo di dati più piccolo e le [funzioni di conversione dei tipi](../../../language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="d2ca8-108">For more information, see [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="d2ca8-109">Per ulteriori informazioni, vedere [parametri e argomenti delle procedure](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="d2ca8-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="d2ca8-110">Per passare uno o più argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="d2ca8-110">To pass one or more arguments to a procedure</span></span>  
  
1. <span data-ttu-id="d2ca8-111">Nell'istruzione chiamante, seguire il nome della procedura con le parentesi.</span><span class="sxs-lookup"><span data-stu-id="d2ca8-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2. <span data-ttu-id="d2ca8-112">Inserire un elenco di argomenti all'interno delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="d2ca8-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="d2ca8-113">Includere un argomento per ogni parametro obbligatorio definito dalla procedura e separare gli argomenti con virgole.</span><span class="sxs-lookup"><span data-stu-id="d2ca8-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3. <span data-ttu-id="d2ca8-114">Verificare che ogni argomento sia un'espressione valida che restituisca un tipo di dati convertibile nel tipo definito dalla routine per il parametro corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d2ca8-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4. <span data-ttu-id="d2ca8-115">Se un parametro è definito come [facoltativo](../../../language-reference/modifiers/optional.md), è possibile includerlo nell'elenco di argomenti o ometterlo.</span><span class="sxs-lookup"><span data-stu-id="d2ca8-115">If a parameter is defined as [Optional](../../../language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="d2ca8-116">Se la si omette, la procedura utilizzerà il valore predefinito definito per il parametro.</span><span class="sxs-lookup"><span data-stu-id="d2ca8-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5. <span data-ttu-id="d2ca8-117">Se si omette un argomento per un `Optional` parametro ed è presente un altro parametro dopo di esso nell'elenco dei parametri, è possibile contrassegnare la posizione dell'argomento omesso con una virgola aggiuntiva nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="d2ca8-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="d2ca8-118">Nell'esempio seguente viene chiamata la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> funzione Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d2ca8-118">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     <span data-ttu-id="d2ca8-119">Nell'esempio precedente viene fornito il primo argomento obbligatorio, ovvero la stringa di messaggio da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="d2ca8-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="d2ca8-120">Omette un argomento per il secondo parametro facoltativo, che specifica i pulsanti da visualizzare nella finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="d2ca8-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="d2ca8-121">Poiché la chiamata non fornisce un valore, in `MsgBox` viene utilizzato il valore predefinito, `MsgBoxStyle.OKOnly` , che visualizza solo un pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="d2ca8-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="d2ca8-122">La seconda virgola nell'elenco di argomenti contrassegna il posto del secondo argomento omesso e l'ultima stringa viene passata al terzo parametro facoltativo di `MsgBox` , ovvero il testo da visualizzare nella barra del titolo.</span><span class="sxs-lookup"><span data-stu-id="d2ca8-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2ca8-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2ca8-123">See also</span></span>

- [<span data-ttu-id="d2ca8-124">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="d2ca8-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="d2ca8-125">Routine Function</span><span class="sxs-lookup"><span data-stu-id="d2ca8-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="d2ca8-126">Routine Property</span><span class="sxs-lookup"><span data-stu-id="d2ca8-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="d2ca8-127">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="d2ca8-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="d2ca8-128">Procedura: definire un parametro per una routine</span><span class="sxs-lookup"><span data-stu-id="d2ca8-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="d2ca8-129">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="d2ca8-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="d2ca8-130">Routine ricorsive</span><span class="sxs-lookup"><span data-stu-id="d2ca8-130">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="d2ca8-131">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="d2ca8-131">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="d2ca8-132">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="d2ca8-132">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="d2ca8-133">Programmazione orientata a oggetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2ca8-133">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)

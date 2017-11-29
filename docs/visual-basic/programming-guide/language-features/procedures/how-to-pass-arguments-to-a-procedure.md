---
title: 'Procedura: passare argomenti a una routine (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3debb4fa6e7b15f9c321ef207d0cc04181a98da2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="8e817-102">Procedura: passare argomenti a una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e817-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="8e817-103">Quando si chiama una routine, si seguono il nome della routine con un elenco di argomenti tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="8e817-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="8e817-104">Viene fornito un argomento corrispondente a ogni parametro obbligatorio definito dalla routine e, facoltativamente, è possibile specificare argomenti per il `Optional` parametri.</span><span class="sxs-lookup"><span data-stu-id="8e817-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="8e817-105">Se non si specifica un `Optional` parametro nella chiamata di, è necessario includere una virgola per contrassegnarne la posizione nell'elenco di argomenti, se viene fornito alcun argomento successivo.</span><span class="sxs-lookup"><span data-stu-id="8e817-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="8e817-106">Se si prevede di passare un argomento di un tipo di dati diverso da quello del parametro corrispondente, ad esempio `Byte` a `String`, è possibile impostare l'opzione di verifica del tipo ([istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) a `Off`.</span><span class="sxs-lookup"><span data-stu-id="8e817-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="8e817-107">Se `Option Strict` è `On`, è necessario utilizzare parole chiave di conversione esplicita o conversioni di ampliamento.</span><span class="sxs-lookup"><span data-stu-id="8e817-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="8e817-108">Per ulteriori informazioni, vedere [conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) e [funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="8e817-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="8e817-109">Per ulteriori informazioni, vedere [parametri di stored Procedure e argomenti](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="8e817-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="8e817-110">Per passare uno o più argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="8e817-110">To pass one or more arguments to a procedure</span></span>  
  
1.  <span data-ttu-id="8e817-111">Nell'istruzione di chiamata, aggiungere il nome tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="8e817-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2.  <span data-ttu-id="8e817-112">All'interno delle parentesi, inserire un elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="8e817-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="8e817-113">Includere un argomento per ogni parametro obbligatorio definito dalla routine e gli argomenti, separarli con virgole.</span><span class="sxs-lookup"><span data-stu-id="8e817-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3.  <span data-ttu-id="8e817-114">Verificare che ogni argomento è un'espressione valida che restituisce un tipo di dati convertibile nel tipo di routine definisce per il parametro corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8e817-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4.  <span data-ttu-id="8e817-115">Se un parametro viene definito come [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md), è possibile includerlo nell'elenco di argomenti oppure ometterlo.</span><span class="sxs-lookup"><span data-stu-id="8e817-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="8e817-116">Se viene omesso, la routine utilizza il valore predefinito definito per tale parametro.</span><span class="sxs-lookup"><span data-stu-id="8e817-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5.  <span data-ttu-id="8e817-117">Se si omette un argomento per un `Optional` parametro ed è presente un altro parametro dopo di esso nell'elenco di parametri, è possibile contrassegnare la posizione dell'argomento omesso da una virgola aggiuntiva nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="8e817-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="8e817-118">L'esempio seguente chiama il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> (funzione).</span><span class="sxs-lookup"><span data-stu-id="8e817-118">The following example calls the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     <span data-ttu-id="8e817-119">Nell'esempio precedente fornisce il primo argomento obbligatorio, ovvero la stringa di messaggio da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="8e817-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="8e817-120">Omette un argomento per il secondo parametro facoltativo che specifica i pulsanti da visualizzare nella finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="8e817-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="8e817-121">Poiché la chiamata non fornisce alcun valore, `MsgBox` utilizza il valore predefinito, `MsgBoxStyle.OKOnly`, che consente di visualizzare solo un **OK** pulsante.</span><span class="sxs-lookup"><span data-stu-id="8e817-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="8e817-122">La seconda virgola nell'elenco di argomenti contrassegna la posizione del secondo argomento omesso e l'ultima stringa viene passato per il terzo parametro facoltativo di `MsgBox`, ovvero il testo da visualizzare nella barra del titolo.</span><span class="sxs-lookup"><span data-stu-id="8e817-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e817-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e817-123">See Also</span></span>  
 [<span data-ttu-id="8e817-124">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="8e817-124">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="8e817-125">Routine Function</span><span class="sxs-lookup"><span data-stu-id="8e817-125">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="8e817-126">Routine Property</span><span class="sxs-lookup"><span data-stu-id="8e817-126">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="8e817-127">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="8e817-127">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="8e817-128">Procedura: Definire un parametro per una routine</span><span class="sxs-lookup"><span data-stu-id="8e817-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)  
 [<span data-ttu-id="8e817-129">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="8e817-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="8e817-130">Routine ricorsive</span><span class="sxs-lookup"><span data-stu-id="8e817-130">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="8e817-131">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="8e817-131">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="8e817-132">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="8e817-132">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="8e817-133">Programmazione orientata ad oggetti</span><span class="sxs-lookup"><span data-stu-id="8e817-133">Object-Oriented Programming</span></span>](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)

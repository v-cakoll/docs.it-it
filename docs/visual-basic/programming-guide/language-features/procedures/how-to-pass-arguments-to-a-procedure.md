---
title: 'Procedura: passare argomenti a una routine (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures, arguments
- procedures, parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures, calling
- argument passing, procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1e0a8d5e798f25f22f53f56a7c01bd69e3e14463
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="8723c-102">Procedura: passare argomenti a una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8723c-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="8723c-103">Quando si chiama una routine, seguendo il nome della routine con un elenco di argomenti racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="8723c-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="8723c-104">Viene fornito un argomento corrispondente a ogni parametro obbligatorio definisce la procedura e, facoltativamente, è possibile specificare argomenti per il `Optional` parametri.</span><span class="sxs-lookup"><span data-stu-id="8723c-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="8723c-105">Se non si fornisce un `Optional` parametro nella chiamata, è necessario includere una virgola per contrassegnarne la posizione nell'elenco di argomenti, se viene fornito alcun argomento successivo.</span><span class="sxs-lookup"><span data-stu-id="8723c-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="8723c-106">Se si intende passare un argomento di un tipo di dati diverso da quello del parametro corrispondente, ad esempio `Byte` a `String`, è possibile impostare l'opzione di verifica del tipo ([istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) a `Off`.</span><span class="sxs-lookup"><span data-stu-id="8723c-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="8723c-107">Se `Option Strict` è `On`, è necessario utilizzare parole chiave di conversione esplicita o le conversioni di ampliamento.</span><span class="sxs-lookup"><span data-stu-id="8723c-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="8723c-108">Per ulteriori informazioni, vedere [conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) e [funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="8723c-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="8723c-109">Per ulteriori informazioni, vedere [procedura parametri e argomenti](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="8723c-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="8723c-110">Per passare uno o più argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="8723c-110">To pass one or more arguments to a procedure</span></span>  
  
1.  <span data-ttu-id="8723c-111">Nell'istruzione di chiamata, aggiungere il nome tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="8723c-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2.  <span data-ttu-id="8723c-112">All'interno delle parentesi, inserire un elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="8723c-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="8723c-113">Includere un argomento per ogni parametro obbligatorio definito dalla routine e gli argomenti, separarli con virgole.</span><span class="sxs-lookup"><span data-stu-id="8723c-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3.  <span data-ttu-id="8723c-114">Assicurarsi che ogni argomento è un'espressione valida che restituisce un tipo di dati convertibile nel tipo di procedura definisce per il parametro corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8723c-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4.  <span data-ttu-id="8723c-115">Se un parametro viene definito come [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md), è possibile includerlo nell'elenco di argomenti oppure ometterlo.</span><span class="sxs-lookup"><span data-stu-id="8723c-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="8723c-116">Se viene omesso, la routine utilizza il valore predefinito definito per tale parametro.</span><span class="sxs-lookup"><span data-stu-id="8723c-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5.  <span data-ttu-id="8723c-117">Se si omette un argomento per un `Optional` parametro ed è presente un altro parametro dopo di esso nell'elenco dei parametri, è possibile contrassegnare la posizione dell'argomento viene omesso da un'altra virgola nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="8723c-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="8723c-118">Nell'esempio seguente viene chiamato il [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>funzione.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="8723c-118">The following example calls the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     <span data-ttu-id="8723c-119">[!code-vb[VbVbcnProcedures&#34;](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8723c-119">[!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="8723c-120">Nell'esempio precedente fornisce il primo argomento obbligatorio, ovvero la stringa di messaggio da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="8723c-120">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="8723c-121">Viene omesso un argomento per il secondo parametro facoltativo che specifica i pulsanti da visualizzare nella finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="8723c-121">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="8723c-122">Poiché la chiamata non fornisce alcun valore, `MsgBox` utilizza il valore predefinito, `MsgBoxStyle.OKOnly`, che consente di visualizzare solo un **OK** pulsante.</span><span class="sxs-lookup"><span data-stu-id="8723c-122">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="8723c-123">La seconda virgola nell'elenco degli argomenti contrassegna la posizione del secondo argomento omesso e l'ultima stringa viene passata al terzo parametro facoltativo di `MsgBox`, ovvero il testo da visualizzare nella barra del titolo.</span><span class="sxs-lookup"><span data-stu-id="8723c-123">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8723c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8723c-124">See Also</span></span>  
 <span data-ttu-id="8723c-125">[Sub (routine)](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8723c-125">[Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="8723c-126"> [Routine di funzione](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8723c-126"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="8723c-127"> [Proprietà (routine)](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8723c-127"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="8723c-128"> [Routine di operatore](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8723c-128"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="8723c-129"> [Procedura: definire un parametro per una routine](./how-to-define-a-parameter-for-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="8723c-129"> [How to: Define a Parameter for a Procedure](./how-to-define-a-parameter-for-a-procedure.md) </span></span>  
<span data-ttu-id="8723c-130"> [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8723c-130"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="8723c-131"> [Routine ricorsive](./recursive-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8723c-131"> [Recursive Procedures](./recursive-procedures.md) </span></span>  
<span data-ttu-id="8723c-132"> [Overload di routine](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="8723c-132"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="8723c-133"> [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="8723c-133"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="8723c-134"> [Programmazione orientata ad oggetti](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span><span class="sxs-lookup"><span data-stu-id="8723c-134"> [Object-Oriented Programming](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span></span>

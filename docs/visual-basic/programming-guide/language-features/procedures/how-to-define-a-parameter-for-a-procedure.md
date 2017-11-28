---
title: 'Procedura: definire un parametro per una routine (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c909cfe1b45a42aae91948917f310474575f225
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="246b3-102">Procedura: definire un parametro per una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="246b3-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>
<span data-ttu-id="246b3-103">Oggetto *parametro* consente di passare un valore per la procedura quando esegue la chiamata al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="246b3-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="246b3-104">Dichiarare ogni parametro per una procedura esattamente come si dichiara una variabile, che specifica il nome e tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="246b3-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="246b3-105">Specificare inoltre il meccanismo di passaggio e se il parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="246b3-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="246b3-106">Per ulteriori informazioni, vedere [parametri di stored Procedure e argomenti](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="246b3-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="246b3-107">Per definire un parametro di routine</span><span class="sxs-lookup"><span data-stu-id="246b3-107">To define a procedure parameter</span></span>  
  
1.  <span data-ttu-id="246b3-108">Nella dichiarazione di routine, aggiungere il nome del parametro all'elenco di parametri della stored procedure, separandolo dalle altri parametri da virgole.</span><span class="sxs-lookup"><span data-stu-id="246b3-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2.  <span data-ttu-id="246b3-109">Decidere il tipo di dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="246b3-109">Decide the data type of the parameter.</span></span>  
  
3.  <span data-ttu-id="246b3-110">Seguire il nome del parametro con un `As` clausola per specificare il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="246b3-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4.  <span data-ttu-id="246b3-111">Decidere il meccanismo di passaggio desiderato per il parametro.</span><span class="sxs-lookup"><span data-stu-id="246b3-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="246b3-112">In genere si passa un parametro per valore, a meno che non si desidera essere in grado di modificare il valore nel codice chiamante alla routine.</span><span class="sxs-lookup"><span data-stu-id="246b3-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5.  <span data-ttu-id="246b3-113">Anteporre al nome di parametro [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) per specificare il meccanismo di passaggio.</span><span class="sxs-lookup"><span data-stu-id="246b3-113">Precede the parameter name with [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="246b3-114">Per ulteriori informazioni, vedere [le differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="246b3-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6.  <span data-ttu-id="246b3-115">Se il parametro è facoltativo, anteporre il meccanismo di passaggio [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) e seguire il tipo di dati del parametro con un segno di uguale (`=`) e un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="246b3-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="246b3-116">Nell'esempio seguente viene definita la struttura di un `Sub` routine con tre parametri.</span><span class="sxs-lookup"><span data-stu-id="246b3-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="246b3-117">Le prime due sono necessari e il terzo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="246b3-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="246b3-118">Nell'elenco di parametri, le dichiarazioni dei parametri sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="246b3-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     [!code-vb[VbVbcnProcedures#33](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     <span data-ttu-id="246b3-119">Il primo parametro accetta un `customer` oggetto, e `updateCustomer` può aggiornare direttamente la variabile passata a `c` perché l'argomento è passato [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span><span class="sxs-lookup"><span data-stu-id="246b3-119">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="246b3-120">La procedura non è possibile modificare i valori degli ultimi due argomenti in quanto vengono passati [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="246b3-120">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="246b3-121">Se il codice chiamante non specifica un valore per il `level` parametro [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] imposta il valore predefinito pari a 0.</span><span class="sxs-lookup"><span data-stu-id="246b3-121">If the calling code does not supply a value for the `level` parameter, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="246b3-122">Se il controllo dei tipi passa ([istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) è `Off`, `As` clausola è facoltativa quando si definisce un parametro.</span><span class="sxs-lookup"><span data-stu-id="246b3-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="246b3-123">Tuttavia, se un qualsiasi parametro utilizza un `As` clausola, tutti gli elementi deve essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="246b3-123">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="246b3-124">Se il tipo di opzione di controllo è `On`, `As` clausola è obbligatoria per ogni definizione di parametro.</span><span class="sxs-lookup"><span data-stu-id="246b3-124">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="246b3-125">Specifica di tipi di dati per tutti gli elementi di programmazione è noto come *tipizzazione forte*.</span><span class="sxs-lookup"><span data-stu-id="246b3-125">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="246b3-126">Quando si imposta `Option Strict On`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] applica la tipizzazione forte.</span><span class="sxs-lookup"><span data-stu-id="246b3-126">When you set `Option Strict On`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] enforces strong typing.</span></span> <span data-ttu-id="246b3-127">Ciò è particolarmente consigliata per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="246b3-127">This is strongly recommended, for the following reasons:</span></span>  
  
    -   <span data-ttu-id="246b3-128">Consente il supporto IntelliSense per le variabili e parametri.</span><span class="sxs-lookup"><span data-stu-id="246b3-128">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="246b3-129">In questo modo è possibile visualizzare le relative proprietà e gli altri membri durante la digitazione nel codice.</span><span class="sxs-lookup"><span data-stu-id="246b3-129">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    -   <span data-ttu-id="246b3-130">Consente al compilatore di eseguire il controllo dei tipi.</span><span class="sxs-lookup"><span data-stu-id="246b3-130">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="246b3-131">Ciò consente di intercettare istruzioni possono avere esito negativo in fase di esecuzione a causa di errori, ad esempio l'overflow.</span><span class="sxs-lookup"><span data-stu-id="246b3-131">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="246b3-132">Vengono inoltre rilevate le chiamate ai metodi su oggetti che non li supportano.</span><span class="sxs-lookup"><span data-stu-id="246b3-132">It also catches calls to methods on objects that do not support them.</span></span>  
  
    -   <span data-ttu-id="246b3-133">Comporta tempi di esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="246b3-133">It results in faster execution of your code.</span></span> <span data-ttu-id="246b3-134">Un motivo è che, se non si specifica un tipo di dati per un elemento di programmazione, il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore assegna automaticamente il `Object` tipo.</span><span class="sxs-lookup"><span data-stu-id="246b3-134">One reason for this is that if you do not specify a data type for a programming element, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler assigns it the `Object` type.</span></span> <span data-ttu-id="246b3-135">Il codice compilato potrebbe essere necessario convertire avanti e indietro tra `Object` e altri tipi di dati, riducendo le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="246b3-135">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="246b3-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="246b3-136">See Also</span></span>  
 [<span data-ttu-id="246b3-137">Routine</span><span class="sxs-lookup"><span data-stu-id="246b3-137">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="246b3-138">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="246b3-138">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="246b3-139">Routine Function</span><span class="sxs-lookup"><span data-stu-id="246b3-139">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="246b3-140">Procedura: Passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="246b3-140">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="246b3-141">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="246b3-141">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="246b3-142">Routine ricorsive</span><span class="sxs-lookup"><span data-stu-id="246b3-142">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="246b3-143">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="246b3-143">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="246b3-144">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="246b3-144">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="246b3-145">Programmazione orientata ad oggetti</span><span class="sxs-lookup"><span data-stu-id="246b3-145">Object-Oriented Programming</span></span>](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)

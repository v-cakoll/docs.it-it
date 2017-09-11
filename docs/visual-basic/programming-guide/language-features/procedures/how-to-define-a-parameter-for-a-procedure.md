---
title: 'Procedura: definire un parametro per una routine (Visual Basic) | Documenti di Microsoft'
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
- procedure parameters, defining data types for
- procedures, parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters, defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: 15
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
ms.openlocfilehash: 5a29bab1c18920d293c51d83d4d8cffdcefe936c
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="23db4-102">Procedura: definire un parametro per una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23db4-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>
<span data-ttu-id="23db4-103">Oggetto *parametro* consente di passare un valore alla routine quando si chiama il codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="23db4-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="23db4-104">Dichiarare ogni parametro per una procedura simile a quello si dichiara una variabile, specificando il nome e tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="23db4-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="23db4-105">Specificare inoltre il meccanismo di passaggio e se il parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="23db4-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="23db4-106">Per ulteriori informazioni, vedere [procedura parametri e argomenti](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="23db4-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="23db4-107">Per definire un parametro di routine</span><span class="sxs-lookup"><span data-stu-id="23db4-107">To define a procedure parameter</span></span>  
  
1.  <span data-ttu-id="23db4-108">Nella dichiarazione di routine, aggiungere il nome del parametro all'elenco di parametri della stored procedure, separandolo dalle altri parametri da una virgola.</span><span class="sxs-lookup"><span data-stu-id="23db4-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2.  <span data-ttu-id="23db4-109">Decidere il tipo di dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="23db4-109">Decide the data type of the parameter.</span></span>  
  
3.  <span data-ttu-id="23db4-110">Seguire il nome del parametro con un `As` clausola per specificare il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="23db4-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4.  <span data-ttu-id="23db4-111">Decidere il meccanismo di passaggio desiderato per il parametro.</span><span class="sxs-lookup"><span data-stu-id="23db4-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="23db4-112">In genere passato un parametro per valore, a meno che non si desidera essere in grado di modificare il valore del codice chiamante alla routine.</span><span class="sxs-lookup"><span data-stu-id="23db4-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5.  <span data-ttu-id="23db4-113">Anteporre il nome del parametro [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) per specificare il meccanismo di passaggio.</span><span class="sxs-lookup"><span data-stu-id="23db4-113">Precede the parameter name with [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="23db4-114">Per ulteriori informazioni, vedere [le differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="23db4-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6.  <span data-ttu-id="23db4-115">Se il parametro è facoltativo, anteporre il meccanismo di passaggio [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) e seguire il tipo di dati di parametro con un segno di uguale (`=`) e un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="23db4-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="23db4-116">Nell'esempio seguente viene definita la struttura di un `Sub` routine con tre parametri.</span><span class="sxs-lookup"><span data-stu-id="23db4-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="23db4-117">I primi due sono necessari e il terzo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="23db4-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="23db4-118">Le dichiarazioni dei parametri sono separati nell'elenco di parametri da virgole.</span><span class="sxs-lookup"><span data-stu-id="23db4-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     <span data-ttu-id="23db4-119">[!code-vb[VbVbcnProcedures n.&33;](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="23db4-119">[!code-vb[VbVbcnProcedures#33](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="23db4-120">Il primo parametro accetta un `customer` oggetto, e `updateCustomer` può aggiornare direttamente la variabile passata a `c` perché viene passato l'argomento [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span><span class="sxs-lookup"><span data-stu-id="23db4-120">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="23db4-121">La procedura non può modificare i valori degli ultimi due argomenti in quanto vengono passati [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="23db4-121">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="23db4-122">Se il codice chiamante non fornisce un valore per il `level` parametro [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] imposta il valore predefinito pari a 0.</span><span class="sxs-lookup"><span data-stu-id="23db4-122">If the calling code does not supply a value for the `level` parameter, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="23db4-123">Se il controllo dei tipi ([istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) è `Off`, `As` clausola è facoltativa quando si definisce un parametro.</span><span class="sxs-lookup"><span data-stu-id="23db4-123">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="23db4-124">Tuttavia, se un qualsiasi parametro utilizza un `As` clausola, tutti gli elementi da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="23db4-124">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="23db4-125">Se il tipo di opzione di verifica dei `On`, `As` clausola è obbligatoria per ogni definizione di parametro.</span><span class="sxs-lookup"><span data-stu-id="23db4-125">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="23db4-126">Specifica di tipi di dati per tutti gli elementi di programmazione è noto come *la tipizzazione forte*.</span><span class="sxs-lookup"><span data-stu-id="23db4-126">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="23db4-127">Quando si imposta `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] attiva la tipizzazione forte.</span><span class="sxs-lookup"><span data-stu-id="23db4-127">When you set `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enforces strong typing.</span></span> <span data-ttu-id="23db4-128">Questa opzione è fortemente consigliata per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="23db4-128">This is strongly recommended, for the following reasons:</span></span>  
  
    -   <span data-ttu-id="23db4-129">Consente il supporto IntelliSense per le variabili e parametri.</span><span class="sxs-lookup"><span data-stu-id="23db4-129">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="23db4-130">Ciò consente di visualizzare le relative proprietà e gli altri membri durante la digitazione del codice.</span><span class="sxs-lookup"><span data-stu-id="23db4-130">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    -   <span data-ttu-id="23db4-131">Consente al compilatore di eseguire il controllo dei tipi.</span><span class="sxs-lookup"><span data-stu-id="23db4-131">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="23db4-132">In questo modo può avere esito negativo in fase di esecuzione a causa di errori, ad esempio overflow istruzione catch.</span><span class="sxs-lookup"><span data-stu-id="23db4-132">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="23db4-133">Inoltre, intercetta le chiamate ai metodi su oggetti che non li supportano.</span><span class="sxs-lookup"><span data-stu-id="23db4-133">It also catches calls to methods on objects that do not support them.</span></span>  
  
    -   <span data-ttu-id="23db4-134">Comporta un'esecuzione più rapida del codice.</span><span class="sxs-lookup"><span data-stu-id="23db4-134">It results in faster execution of your code.</span></span> <span data-ttu-id="23db4-135">Una ragione è che se non si specifica un tipo di dati per un elemento di programmazione, il [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore assegna automaticamente il `Object` tipo.</span><span class="sxs-lookup"><span data-stu-id="23db4-135">One reason for this is that if you do not specify a data type for a programming element, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler assigns it the `Object` type.</span></span> <span data-ttu-id="23db4-136">Il codice compilato potrebbe essere necessario convertire avanti e indietro tra `Object` e altri tipi di dati, riducendo le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="23db4-136">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23db4-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23db4-137">See Also</span></span>  
 <span data-ttu-id="23db4-138">[Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="23db4-138">[Procedures](./index.md) </span></span>  
<span data-ttu-id="23db4-139"> [Sub (routine)](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="23db4-139"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="23db4-140"> [Routine di funzione](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="23db4-140"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="23db4-141"> [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="23db4-141"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="23db4-142"> [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="23db4-142"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="23db4-143"> [Routine ricorsive](./recursive-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="23db4-143"> [Recursive Procedures](./recursive-procedures.md) </span></span>  
<span data-ttu-id="23db4-144"> [Overload di routine](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="23db4-144"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="23db4-145"> [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="23db4-145"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="23db4-146"> [Programmazione orientata ad oggetti](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span><span class="sxs-lookup"><span data-stu-id="23db4-146"> [Object-Oriented Programming](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span></span>

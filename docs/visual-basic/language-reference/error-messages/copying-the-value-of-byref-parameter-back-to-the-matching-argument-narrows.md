---
title: Quando il valore del parametro &quot;ByRef&quot; &quot;&lt;parametername&gt;&quot;argomento corrispondente viene convertito dal tipo&quot;&lt;NomeTipo1&gt;&quot; al tipo&quot;&lt;in NomeTipo2&gt;&quot; | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
dev_langs:
- VB
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
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
ms.openlocfilehash: 10ad4af689c11f3e4defe43c4fed9ed579ba5305
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a><span data-ttu-id="ca6c7-102">Quando il valore del parametro 'ByRef' '&lt;parametername&gt;'argomento corrispondente viene convertito dal tipo'&lt;NomeTipo1&gt;' al tipo'&lt;in NomeTipo2&gt;'</span><span class="sxs-lookup"><span data-stu-id="ca6c7-102">Copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument narrows from type &#39;&lt;typename1&gt;&#39; to type &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="ca6c7-103">Una procedura viene chiamata con un argomento che può ampliarsi nel tipo di parametro corrispondente, e la conversione dal parametro dell'argomento è più piccolo.</span><span class="sxs-lookup"><span data-stu-id="ca6c7-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>  
  
 <span data-ttu-id="ca6c7-104">Quando si definisce una classe o una struttura, è possibile definire uno o più operatori di conversione per convertire il tipo della classe o della struttura in altri tipi.</span><span class="sxs-lookup"><span data-stu-id="ca6c7-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="ca6c7-105">È anche possibile definire operatori di conversione inversi per riconvertire gli altri tipi nel tipo della classe o della struttura originale.</span><span class="sxs-lookup"><span data-stu-id="ca6c7-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="ca6c7-106">Quando si utilizza il tipo di classe o struttura in una chiamata di procedura [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] possibile utilizzare gli operatori di conversione per convertire il tipo di un argomento per il tipo del parametro corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ca6c7-106">When you use your class or structure type in a procedure call, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="ca6c7-107">Se si passa l'argomento [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] talvolta copia il valore dell'argomento in una variabile locale nella procedura anziché passare un riferimento.</span><span class="sxs-lookup"><span data-stu-id="ca6c7-107">If you pass the argument [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="ca6c7-108">In tal caso, quando viene restituito, la procedura [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] dovrà quindi copiare il valore della variabile locale nell'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="ca6c7-108">In such a case, when the procedure returns, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="ca6c7-109">Se un valore dell'argomento `ByRef` viene copiato nella routine e l'argomento e il parametro sono dello stesso tipo, non è necessaria alcuna conversione.</span><span class="sxs-lookup"><span data-stu-id="ca6c7-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="ca6c7-110">Tuttavia, se i tipi sono diversi, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] necessario convertirli in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="ca6c7-110">But if the types are different, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must convert in both directions.</span></span> <span data-ttu-id="ca6c7-111">Se uno dei tipi è il tipo di classe o struttura, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] deve convertire da e verso l'altro tipo.</span><span class="sxs-lookup"><span data-stu-id="ca6c7-111">If one of the types is your class or structure type, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must convert it both to and from the other type.</span></span> <span data-ttu-id="ca6c7-112">Se una di queste conversioni è un ampliamento, potrebbe limitare la conversione inversa.</span><span class="sxs-lookup"><span data-stu-id="ca6c7-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>  
  
 <span data-ttu-id="ca6c7-113">**ID errore:** BC32053</span><span class="sxs-lookup"><span data-stu-id="ca6c7-113">**Error ID:** BC32053</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ca6c7-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ca6c7-114">To correct this error</span></span>  
  
-   <span data-ttu-id="ca6c7-115">Se possibile, utilizzare un argomento chiamante dello stesso tipo del parametro di routine, pertanto [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] non è necessario effettuare alcuna conversione.</span><span class="sxs-lookup"><span data-stu-id="ca6c7-115">If possible, use a calling argument of the same type as the procedure parameter, so [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="ca6c7-116">Se è necessario chiamare la routine con un argomento di tipo diverso dal tipo di parametro ma non è necessario restituire un valore nell'argomento di chiamata, definire il parametro come [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) anziché `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="ca6c7-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
-   <span data-ttu-id="ca6c7-117">Se si desidera restituire un valore nell'argomento di chiamata, definire l'operatore di conversione inversa come [Widening](../../../visual-basic/language-reference/modifiers/widening.md), se possibile.</span><span class="sxs-lookup"><span data-stu-id="ca6c7-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../../../visual-basic/language-reference/modifiers/widening.md), if possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca6c7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca6c7-118">See Also</span></span>  
 <span data-ttu-id="ca6c7-119">[Procedure](../../../visual-basic/programming-guide/language-features/procedures/index.md) </span><span class="sxs-lookup"><span data-stu-id="ca6c7-119">[Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md) </span></span>  
<span data-ttu-id="ca6c7-120"> [Gli argomenti e parametri di routine](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="ca6c7-120"> [Procedure Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="ca6c7-121"> [Passaggio di argomenti per valore e per riferimento](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ca6c7-121"> [Passing Arguments by Value and by Reference](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="ca6c7-122"> [Routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="ca6c7-122"> [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md) </span></span>  
<span data-ttu-id="ca6c7-123"> [Operator (istruzione)](../../../visual-basic/language-reference/statements/operator-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ca6c7-123"> [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md) </span></span>  
<span data-ttu-id="ca6c7-124"> [Procedura: definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="ca6c7-124"> [How to: Define an Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="ca6c7-125"> [Procedura: definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="ca6c7-125"> [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="ca6c7-126"> [Conversioni di tipi in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="ca6c7-126"> [Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="ca6c7-127"> [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="ca6c7-127"> [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span></span>

---
title: Operatori di concatenazione in Visual Basic | Documenti di Microsoft
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
- '& operator [Visual Basic], concatenation'
- concatenation operators
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators, Visual Basic strings
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
caps.latest.revision: 18
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
ms.openlocfilehash: f255e168b9eb794ef846e0cc18dbbdba5941bec5
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="concatenation-operators-in-visual-basic"></a><span data-ttu-id="75ed0-102">Operatori di concatenazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75ed0-102">Concatenation Operators in Visual Basic</span></span>
<span data-ttu-id="75ed0-103">Gli operatori di concatenazione consentono di unire più stringhe in un'unica stringa.</span><span class="sxs-lookup"><span data-stu-id="75ed0-103">Concatenation operators join multiple strings into a single string.</span></span> <span data-ttu-id="75ed0-104">Sono disponibili due operatori di concatenazione: `+` e `&`.</span><span class="sxs-lookup"><span data-stu-id="75ed0-104">There are two concatenation operators, `+` and `&`.</span></span> <span data-ttu-id="75ed0-105">Entrambi eseguono operazioni di concatenazione di base, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="75ed0-105">Both carry out the basic concatenation operation, as the following example shows.</span></span>  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 <span data-ttu-id="75ed0-106">Questi operatori possono concatenare anche variabili di tipo `String`, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="75ed0-106">These operators can also concatenate `String` variables, as the following example shows.</span></span>  
  
 <span data-ttu-id="75ed0-107">[!code-vb[VbVbalrOperators&#76;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="75ed0-107">[!code-vb[VbVbalrOperators#76](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]</span></span>  
  
## <a name="differences-between-the-two-concatenation-operators"></a><span data-ttu-id="75ed0-108">Differenze tra i due operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="75ed0-108">Differences Between the Two Concatenation Operators</span></span>  
 <span data-ttu-id="75ed0-109">Il [+ (operatore)](../../../../visual-basic/language-reference/operators/addition-operator.md) ha lo scopo principale di aggiunta di due numeri.</span><span class="sxs-lookup"><span data-stu-id="75ed0-109">The [+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) has the primary purpose of adding two numbers.</span></span> <span data-ttu-id="75ed0-110">Questo operatore consente però anche di concatenare operandi numerici con operandi stringa.</span><span class="sxs-lookup"><span data-stu-id="75ed0-110">However, it can also concatenate numeric operands with string operands.</span></span> <span data-ttu-id="75ed0-111">Il `+` operatore include un insieme complesso di regole che determinano se aggiungere, concatenare, segnalare un errore del compilatore o generare in fase di esecuzione <xref:System.InvalidCastException>(eccezione).</xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="75ed0-111">The `+` operator has a complex set of rules that determine whether to add, concatenate, signal a compiler error, or throw a run-time <xref:System.InvalidCastException> exception.</span></span>  
  
 <span data-ttu-id="75ed0-112">Il [/ operatore](../../../../visual-basic/language-reference/operators/concatenation-operator.md) viene definito solo per `String` operandi e amplia sempre i propri operandi in `String`, indipendentemente dall'impostazione di `Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="75ed0-112">The [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) is defined only for `String` operands, and it always widens its operands to `String`, regardless of the setting of `Option Strict`.</span></span> <span data-ttu-id="75ed0-113">L'operatore `&` rappresenta la scelta consigliata per la concatenazione delle stringhe poiché viene definito solo per le stringhe e riduce la possibilità di generare conversioni non intenzionali.</span><span class="sxs-lookup"><span data-stu-id="75ed0-113">The `&` operator is recommended for string concatenation because it is defined exclusively for strings and reduces your chances of generating an unintended conversion.</span></span>  
  
## <a name="performance-string-and-stringbuilder"></a><span data-ttu-id="75ed0-114">Prestazioni: String e StringBuilder</span><span class="sxs-lookup"><span data-stu-id="75ed0-114">Performance: String and StringBuilder</span></span>  
 <span data-ttu-id="75ed0-115">Se si esegue un numero significativo di modifiche in una stringa, ad esempio concatenazioni, eliminazioni e sostituzioni, le prestazioni potrebbero profitto ottenuto la <xref:System.Text.StringBuilder>classe il <xref:System.Text>dello spazio dei nomi.</xref:System.Text> </xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="75ed0-115">If you do a significant number of manipulations on a string, such as concatenations, deletions, and replacements, your performance might profit from the <xref:System.Text.StringBuilder> class in the <xref:System.Text> namespace.</span></span> <span data-ttu-id="75ed0-116">Accetta un'istruzione aggiuntiva per creare e inizializzare un <xref:System.Text.StringBuilder>oggetto e un'altra istruzione per convertire il valore finale per un `String`, ma sarà possibile recuperare il momento perché <xref:System.Text.StringBuilder>offre migliori prestazioni.</xref:System.Text.StringBuilder> </xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="75ed0-116">It takes an extra instruction to create and initialize a <xref:System.Text.StringBuilder> object, and another instruction to convert its final value to a `String`, but you might recover this time because <xref:System.Text.StringBuilder> can perform faster.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ed0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75ed0-117">See Also</span></span>  
 <span data-ttu-id="75ed0-118">[Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="75ed0-118">[Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="75ed0-119"> [Tipi di metodi di manipolazione delle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md) </span><span class="sxs-lookup"><span data-stu-id="75ed0-119"> [Types of String Manipulation Methods in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md) </span></span>  
<span data-ttu-id="75ed0-120"> [Operatori aritmetici in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="75ed0-120"> [Arithmetic Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) </span></span>  
<span data-ttu-id="75ed0-121"> [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="75ed0-121"> [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span></span>  
<span data-ttu-id="75ed0-122"> [Operatori logici e bit per bit in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span><span class="sxs-lookup"><span data-stu-id="75ed0-122"> [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span></span>

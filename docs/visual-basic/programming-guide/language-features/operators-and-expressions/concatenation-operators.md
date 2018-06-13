---
title: Operatori di concatenazione in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators [Visual Basic]
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators [Visual Basic]
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
ms.openlocfilehash: ab268e513e6f019ed651c94deb5e423cfcca7587
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650618"
---
# <a name="concatenation-operators-in-visual-basic"></a><span data-ttu-id="6a3bc-102">Operatori di concatenazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a3bc-102">Concatenation Operators in Visual Basic</span></span>
<span data-ttu-id="6a3bc-103">Gli operatori di concatenazione consentono di unire più stringhe in un'unica stringa.</span><span class="sxs-lookup"><span data-stu-id="6a3bc-103">Concatenation operators join multiple strings into a single string.</span></span> <span data-ttu-id="6a3bc-104">Sono disponibili due operatori di concatenazione: `+` e `&`.</span><span class="sxs-lookup"><span data-stu-id="6a3bc-104">There are two concatenation operators, `+` and `&`.</span></span> <span data-ttu-id="6a3bc-105">Entrambi eseguono operazioni di concatenazione di base, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6a3bc-105">Both carry out the basic concatenation operation, as the following example shows.</span></span>  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 <span data-ttu-id="6a3bc-106">Questi operatori possono concatenare anche variabili di tipo `String`, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6a3bc-106">These operators can also concatenate `String` variables, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrOperators#76](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]  
  
## <a name="differences-between-the-two-concatenation-operators"></a><span data-ttu-id="6a3bc-107">Differenze tra i due operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="6a3bc-107">Differences Between the Two Concatenation Operators</span></span>  
 <span data-ttu-id="6a3bc-108">Il [+ (operatore)](../../../../visual-basic/language-reference/operators/addition-operator.md) ha lo scopo principale di aggiunta di due numeri.</span><span class="sxs-lookup"><span data-stu-id="6a3bc-108">The [+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) has the primary purpose of adding two numbers.</span></span> <span data-ttu-id="6a3bc-109">Questo operatore consente però anche di concatenare operandi numerici con operandi stringa.</span><span class="sxs-lookup"><span data-stu-id="6a3bc-109">However, it can also concatenate numeric operands with string operands.</span></span> <span data-ttu-id="6a3bc-110">L'operatore `+` include un insieme complesso di regole che determinano se aggiungere, concatenare, segnalare un errore del compilatore oppure generare un'eccezione <xref:System.InvalidCastException> in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6a3bc-110">The `+` operator has a complex set of rules that determine whether to add, concatenate, signal a compiler error, or throw a run-time <xref:System.InvalidCastException> exception.</span></span>  
  
 <span data-ttu-id="6a3bc-111">Il [& operatore](../../../../visual-basic/language-reference/operators/concatenation-operator.md) viene definito solo per `String` amplia sempre i propri operandi per gli operandi e `String`, indipendentemente dall'impostazione di `Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="6a3bc-111">The [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) is defined only for `String` operands, and it always widens its operands to `String`, regardless of the setting of `Option Strict`.</span></span> <span data-ttu-id="6a3bc-112">L'operatore `&` rappresenta la scelta consigliata per la concatenazione delle stringhe poiché viene definito solo per le stringhe e riduce la possibilità di generare conversioni non intenzionali.</span><span class="sxs-lookup"><span data-stu-id="6a3bc-112">The `&` operator is recommended for string concatenation because it is defined exclusively for strings and reduces your chances of generating an unintended conversion.</span></span>  
  
## <a name="performance-string-and-stringbuilder"></a><span data-ttu-id="6a3bc-113">Prestazioni: String e StringBuilder</span><span class="sxs-lookup"><span data-stu-id="6a3bc-113">Performance: String and StringBuilder</span></span>  
 <span data-ttu-id="6a3bc-114">Se una stringa subisce numerose manipolazioni, ad esempio concatenazioni, eliminazioni e sostituzioni, l'uso della classe <xref:System.Text.StringBuilder> nello spazio dei nomi <xref:System.Text> può migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6a3bc-114">If you do a significant number of manipulations on a string, such as concatenations, deletions, and replacements, your performance might profit from the <xref:System.Text.StringBuilder> class in the <xref:System.Text> namespace.</span></span> <span data-ttu-id="6a3bc-115">Questa classe richiede un'istruzione aggiuntiva per la creazione e l'inizializzazione di un oggetto <xref:System.Text.StringBuilder> e un'altra istruzione per la conversione del relativo valore finale in `String`, ma in questo caso è possibile eseguire il ripristino perché l'esecuzione di <xref:System.Text.StringBuilder> è più veloce.</span><span class="sxs-lookup"><span data-stu-id="6a3bc-115">It takes an extra instruction to create and initialize a <xref:System.Text.StringBuilder> object, and another instruction to convert its final value to a `String`, but you might recover this time because <xref:System.Text.StringBuilder> can perform faster.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a3bc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a3bc-116">See Also</span></span>  
 [<span data-ttu-id="6a3bc-117">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="6a3bc-117">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="6a3bc-118">Tipi di metodi di modifica di stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a3bc-118">Types of String Manipulation Methods in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)  
 [<span data-ttu-id="6a3bc-119">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a3bc-119">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="6a3bc-120">Operatori di confronto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a3bc-120">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="6a3bc-121">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a3bc-121">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)

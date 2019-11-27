---
title: Widening
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: 1c9aa78549ca6e41c9fe54c12e0aaec8e7cc30cb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347836"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="7694f-102">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7694f-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="7694f-103">Indica che un operatore di conversione (`CType`) converte una classe o una struttura in un tipo che può conservare tutti i valori possibili della classe o della struttura originale.</span><span class="sxs-lookup"><span data-stu-id="7694f-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="7694f-104">Conversione con la parola chiave Widen</span><span class="sxs-lookup"><span data-stu-id="7694f-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="7694f-105">La procedura di conversione deve specificare `Public Shared` oltre al `Widening`.</span><span class="sxs-lookup"><span data-stu-id="7694f-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="7694f-106">Le conversioni verso un tipo di dati più ampio hanno sempre esito positivo in fase di esecuzione e non subiscono mai</span><span class="sxs-lookup"><span data-stu-id="7694f-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="7694f-107">Gli esempi sono `Single` `Double`, `Char` `String`e un tipo derivato al relativo tipo di base.</span><span class="sxs-lookup"><span data-stu-id="7694f-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="7694f-108">Questa ultima conversione viene ampliata perché il tipo derivato contiene tutti i membri del tipo di base e pertanto è un'istanza del tipo di base.</span><span class="sxs-lookup"><span data-stu-id="7694f-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="7694f-109">Il codice consumer non deve usare `CType` per le conversioni verso un tipo di oggetto più ampio, anche se `Option Strict` è `On`.</span><span class="sxs-lookup"><span data-stu-id="7694f-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="7694f-110">Il `Widening` parola chiave può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="7694f-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="7694f-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="7694f-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 <span data-ttu-id="7694f-112">Per le definizioni di operatori di conversione verso un tipo di informazioni più piccolo e più piccolo, vedere [procedura: definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="7694f-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7694f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7694f-113">See also</span></span>

- [<span data-ttu-id="7694f-114">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="7694f-114">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="7694f-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="7694f-115">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="7694f-116">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="7694f-116">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="7694f-117">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="7694f-117">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="7694f-118">CType Function</span><span class="sxs-lookup"><span data-stu-id="7694f-118">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="7694f-119">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="7694f-119">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="7694f-120">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="7694f-120">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)

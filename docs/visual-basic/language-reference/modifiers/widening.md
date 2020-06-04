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
ms.openlocfilehash: 69040bf48b44a54f7a231738b88db1cbc716ebb3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359903"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="1509d-102">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1509d-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="1509d-103">Indica che un operatore di conversione ( `CType` ) converte una classe o una struttura in un tipo che può conservare tutti i valori possibili della classe o della struttura originale.</span><span class="sxs-lookup"><span data-stu-id="1509d-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="1509d-104">Conversione con la parola chiave Widen</span><span class="sxs-lookup"><span data-stu-id="1509d-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="1509d-105">La procedura di conversione deve specificare `Public Shared` oltre a `Widening` .</span><span class="sxs-lookup"><span data-stu-id="1509d-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="1509d-106">Le conversioni verso un tipo di dati più ampio hanno sempre esito positivo in fase di esecuzione e non subiscono mai</span><span class="sxs-lookup"><span data-stu-id="1509d-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="1509d-107">Gli esempi `Single` sono `Double` , `Char` a `String` e un tipo derivato al relativo tipo di base.</span><span class="sxs-lookup"><span data-stu-id="1509d-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="1509d-108">Questa ultima conversione viene ampliata perché il tipo derivato contiene tutti i membri del tipo di base e pertanto è un'istanza del tipo di base.</span><span class="sxs-lookup"><span data-stu-id="1509d-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="1509d-109">Il codice consumer non deve usare per le conversioni verso un tipo di oggetto più `CType` ampio, anche se `Option Strict` è `On` .</span><span class="sxs-lookup"><span data-stu-id="1509d-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="1509d-110">La `Widening` parola chiave può essere usata in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="1509d-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="1509d-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="1509d-111">Operator Statement</span></span>](../statements/operator-statement.md)  
  
 <span data-ttu-id="1509d-112">Per le definizioni di operatori di conversione verso un tipo di informazioni più piccolo e più piccolo, vedere [procedura: definire un operatore di conversione](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1509d-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1509d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1509d-113">See also</span></span>

- [<span data-ttu-id="1509d-114">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="1509d-114">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="1509d-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="1509d-115">Narrowing</span></span>](narrowing.md)
- [<span data-ttu-id="1509d-116">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="1509d-116">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="1509d-117">Procedura: definire un operatore</span><span class="sxs-lookup"><span data-stu-id="1509d-117">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="1509d-118">CType Function</span><span class="sxs-lookup"><span data-stu-id="1509d-118">CType Function</span></span>](../functions/ctype-function.md)
- [<span data-ttu-id="1509d-119">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="1509d-119">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
- [<span data-ttu-id="1509d-120">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="1509d-120">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)

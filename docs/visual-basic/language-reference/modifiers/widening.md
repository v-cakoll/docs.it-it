---
title: Widening (Visual Basic)
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
ms.openlocfilehash: 3b9d1ec15c6c2000fb0842abe25848f853cdf986
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703709"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="48aad-102">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48aad-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="48aad-103">Indica che un operatore di conversione (`CType`) converte una classe o struttura in un tipo che può contenere tutti i possibili valori della classe o struttura originale.</span><span class="sxs-lookup"><span data-stu-id="48aad-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="48aad-104">La conversione con la parola chiave Widening</span><span class="sxs-lookup"><span data-stu-id="48aad-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="48aad-105">Routine di conversione deve specificare `Public Shared` oltre a `Widening`.</span><span class="sxs-lookup"><span data-stu-id="48aad-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="48aad-106">Le conversioni di ampliamento sempre eseguite correttamente in fase di esecuzione e non comportano perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="48aad-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="48aad-107">Sono esempi `Single` al `Double`, `Char` a `String`e un tipo derivato al tipo di base.</span><span class="sxs-lookup"><span data-stu-id="48aad-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="48aad-108">Questa conversione ultimo è grande perché il tipo derivato contiene tutti i membri del tipo di base e pertanto rappresenta un'istanza del tipo di base.</span><span class="sxs-lookup"><span data-stu-id="48aad-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="48aad-109">Il codice consumer non deve utilizzare `CType` per la conversione di ampliamento, anche se `Option Strict` è `On`.</span><span class="sxs-lookup"><span data-stu-id="48aad-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="48aad-110">Il `Widening` parola chiave può essere usata in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="48aad-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="48aad-111">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="48aad-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 <span data-ttu-id="48aad-112">Ad esempio le definizioni di ampliamento e restrizione gli operatori di conversione, vedere [come: Definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="48aad-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48aad-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48aad-113">See also</span></span>
- [<span data-ttu-id="48aad-114">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="48aad-114">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="48aad-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="48aad-115">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="48aad-116">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="48aad-116">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="48aad-117">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="48aad-117">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="48aad-118">Funzione CType</span><span class="sxs-lookup"><span data-stu-id="48aad-118">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="48aad-119">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="48aad-119">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="48aad-120">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="48aad-120">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)

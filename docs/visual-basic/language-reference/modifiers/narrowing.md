---
title: Narrowing
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: f7724053e3732c909523e4e2d3b65bb1918c29d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362359"
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="a5141-102">Narrowing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5141-102">Narrowing (Visual Basic)</span></span>
<span data-ttu-id="a5141-103">Indica che un operatore di conversione ( `CType` ) converte una classe o una struttura in un tipo che potrebbe non essere in grado di contenere alcuni dei possibili valori della classe o della struttura originale.</span><span class="sxs-lookup"><span data-stu-id="a5141-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="a5141-104">Conversione con la parola chiave Narrowing</span><span class="sxs-lookup"><span data-stu-id="a5141-104">Converting with the Narrowing Keyword</span></span>  
 <span data-ttu-id="a5141-105">La procedura di conversione deve specificare `Public Shared` oltre a `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="a5141-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="a5141-106">Le conversioni verso un tipo di dati più piccolo non vengono sempre eseguite in fase di esecuzione e possono avere esito negativo o causare una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="a5141-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="a5141-107">Gli esempi `Long` sono `Integer` , `String` a `Date` e un tipo di base a un tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="a5141-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="a5141-108">Questa ultima conversione si restringe perché il tipo di base potrebbe non contenere tutti i membri del tipo derivato e pertanto non è un'istanza del tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="a5141-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="a5141-109">Se `Option Strict` è `On` , il codice consumer deve utilizzare `CType` per tutte le conversioni verso un tipo di caratteri più piccolo.</span><span class="sxs-lookup"><span data-stu-id="a5141-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="a5141-110">La `Narrowing` parola chiave può essere usata in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="a5141-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="a5141-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="a5141-111">Operator Statement</span></span>](../statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="a5141-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5141-112">See also</span></span>

- [<span data-ttu-id="a5141-113">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="a5141-113">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="a5141-114">Widening</span><span class="sxs-lookup"><span data-stu-id="a5141-114">Widening</span></span>](widening.md)
- [<span data-ttu-id="a5141-115">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="a5141-115">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="a5141-116">Procedura: definire un operatore</span><span class="sxs-lookup"><span data-stu-id="a5141-116">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="a5141-117">CType Function</span><span class="sxs-lookup"><span data-stu-id="a5141-117">CType Function</span></span>](../functions/ctype-function.md)
- [<span data-ttu-id="a5141-118">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="a5141-118">Option Strict Statement</span></span>](../statements/option-strict-statement.md)

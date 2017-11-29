---
title: Narrowing (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 50116c6212e919d4b9b35fc933d80dee14bd4ecf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="d1520-102">Narrowing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1520-102">Narrowing (Visual Basic)</span></span>
<span data-ttu-id="d1520-103">Indica che un operatore di conversione (`CType`) converte una classe o struttura in un tipo che potrebbe non essere in grado di contenere alcuni dei possibili valori della classe o della struttura originale.</span><span class="sxs-lookup"><span data-stu-id="d1520-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="d1520-104">La conversione con la parola chiave Narrowing</span><span class="sxs-lookup"><span data-stu-id="d1520-104">Converting with the Narrowing Keyword</span></span>  
 <span data-ttu-id="d1520-105">Routine di conversione deve specificare `Public Shared` oltre a `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="d1520-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="d1520-106">Conversioni di restrizione non sempre esito positivo in fase di esecuzione e può non riuscire o comportare la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="d1520-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="d1520-107">Esempi sono `Long` a `Integer`, `String` a `Date`e un tipo di base a un tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="d1520-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="d1520-108">Questa conversione ultima è narrowing perché il tipo di base potrebbe non contenere tutti i membri del tipo derivato e pertanto non è un'istanza del tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="d1520-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="d1520-109">Se `Option Strict` è `On`, l'utilizzo di codice è necessario utilizzare `CType` per tutte le conversioni di restrizione.</span><span class="sxs-lookup"><span data-stu-id="d1520-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="d1520-110">Il `Narrowing` parola chiave può essere utilizzata in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="d1520-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="d1520-111">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="d1520-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d1520-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1520-112">See Also</span></span>  
 [<span data-ttu-id="d1520-113">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="d1520-113">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="d1520-114">Widening</span><span class="sxs-lookup"><span data-stu-id="d1520-114">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="d1520-115">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="d1520-115">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="d1520-116">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="d1520-116">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="d1520-117">Funzione CType</span><span class="sxs-lookup"><span data-stu-id="d1520-117">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [<span data-ttu-id="d1520-118">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="d1520-118">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)

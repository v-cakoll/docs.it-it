---
title: '&#39;AddressOf&#39; operando deve essere il nome di un metodo (senza parentesi)'
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: 6f9827d885996ffab8bdab91d0f774a57073e4a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565150"
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="dc6a0-102">&#39;AddressOf&#39; operando deve essere il nome di un metodo (senza parentesi)</span><span class="sxs-lookup"><span data-stu-id="dc6a0-102">&#39;AddressOf&#39; operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="dc6a0-103">L'operatore `AddressOf` crea un'istanza di delegato di routine che fa riferimento a una routine specifica.</span><span class="sxs-lookup"><span data-stu-id="dc6a0-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="dc6a0-104">La sintassi è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="dc6a0-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="dc6a0-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="dc6a0-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="dc6a0-106">È stato inserito tra parentesi attorno ai seguenti argomenti `AddressOf`, che tuttavia non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="dc6a0-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="dc6a0-107">**ID errore:** BC30577</span><span class="sxs-lookup"><span data-stu-id="dc6a0-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dc6a0-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="dc6a0-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="dc6a0-109">Rimuovere le parentesi che racchiudono l'argomento che segue `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="dc6a0-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="dc6a0-110">Assicurarsi che l'argomento è un nome di metodo.</span><span class="sxs-lookup"><span data-stu-id="dc6a0-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6a0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc6a0-111">See also</span></span>
- [<span data-ttu-id="dc6a0-112">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="dc6a0-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="dc6a0-113">Delegati</span><span class="sxs-lookup"><span data-stu-id="dc6a0-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)

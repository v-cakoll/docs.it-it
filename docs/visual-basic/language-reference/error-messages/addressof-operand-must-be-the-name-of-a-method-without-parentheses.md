---
title: L'operando 'AddressOf' deve essere il nome di un metodo, senza parentesi
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: b8c67c2390df91c6a4af66e020365544e6bf369b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59323824"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="26061-102">L'operando 'AddressOf' deve essere il nome di un metodo, senza parentesi</span><span class="sxs-lookup"><span data-stu-id="26061-102">'AddressOf' operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="26061-103">L'operatore `AddressOf` crea un'istanza di delegato di routine che fa riferimento a una routine specifica.</span><span class="sxs-lookup"><span data-stu-id="26061-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="26061-104">La sintassi è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="26061-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="26061-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="26061-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="26061-106">È stato inserito tra parentesi attorno ai seguenti argomenti `AddressOf`, che tuttavia non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="26061-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="26061-107">**ID errore:** BC30577</span><span class="sxs-lookup"><span data-stu-id="26061-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="26061-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="26061-108">To correct this error</span></span>  
  
1. <span data-ttu-id="26061-109">Rimuovere le parentesi che racchiudono l'argomento che segue `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="26061-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2. <span data-ttu-id="26061-110">Assicurarsi che l'argomento è un nome di metodo.</span><span class="sxs-lookup"><span data-stu-id="26061-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26061-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26061-111">See also</span></span>

- [<span data-ttu-id="26061-112">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="26061-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="26061-113">Delegati</span><span class="sxs-lookup"><span data-stu-id="26061-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)

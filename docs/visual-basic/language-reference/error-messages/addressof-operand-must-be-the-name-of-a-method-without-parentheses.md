---
title: L'operando 'AddressOf' deve essere il nome di un metodo, senza parentesi
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: 37b02ab76730458b757835fda37b8cb145ed93ad
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262114"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="1b1d4-102">L'operando 'AddressOf' deve essere il nome di un metodo, senza parentesi</span><span class="sxs-lookup"><span data-stu-id="1b1d4-102">'AddressOf' operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="1b1d4-103">L'operatore `AddressOf` crea un'istanza di delegato di routine che fa riferimento a una routine specifica.</span><span class="sxs-lookup"><span data-stu-id="1b1d4-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="1b1d4-104">La sintassi è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="1b1d4-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="1b1d4-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="1b1d4-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="1b1d4-106">È stato inserito tra parentesi attorno ai seguenti argomenti `AddressOf`, che tuttavia non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="1b1d4-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="1b1d4-107">**ID errore:** BC30577</span><span class="sxs-lookup"><span data-stu-id="1b1d4-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1b1d4-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="1b1d4-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="1b1d4-109">Rimuovere le parentesi che racchiudono l'argomento che segue `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="1b1d4-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="1b1d4-110">Assicurarsi che l'argomento è un nome di metodo.</span><span class="sxs-lookup"><span data-stu-id="1b1d4-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b1d4-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b1d4-111">See also</span></span>
- [<span data-ttu-id="1b1d4-112">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="1b1d4-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="1b1d4-113">Delegati</span><span class="sxs-lookup"><span data-stu-id="1b1d4-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)

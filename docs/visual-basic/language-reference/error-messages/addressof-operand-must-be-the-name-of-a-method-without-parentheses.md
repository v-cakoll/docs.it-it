---
title: '&#39;AddressOf&#39; operando deve essere il nome di un metodo (senza parentesi)'
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: 701d86e03d9b14236eec8436d99ec40cebbbcd44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583812"
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="943eb-102">&#39;AddressOf&#39; operando deve essere il nome di un metodo (senza parentesi)</span><span class="sxs-lookup"><span data-stu-id="943eb-102">&#39;AddressOf&#39; operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="943eb-103">L'operatore `AddressOf` crea un'istanza di delegato di routine che fa riferimento a una routine specifica.</span><span class="sxs-lookup"><span data-stu-id="943eb-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="943eb-104">La sintassi è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="943eb-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="943eb-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="943eb-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="943eb-106">È stato inserito parentesi per racchiudere l'argomento che segue `AddressOf`, che tuttavia non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="943eb-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="943eb-107">**ID errore:** BC30577</span><span class="sxs-lookup"><span data-stu-id="943eb-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="943eb-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="943eb-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="943eb-109">Rimuovere le parentesi che racchiudono il seguente argomento `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="943eb-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="943eb-110">Verificare che l'argomento è un nome di metodo.</span><span class="sxs-lookup"><span data-stu-id="943eb-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="943eb-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="943eb-111">See Also</span></span>  
 [<span data-ttu-id="943eb-112">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="943eb-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="943eb-113">Delegati</span><span class="sxs-lookup"><span data-stu-id="943eb-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)

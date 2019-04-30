---
title: Impossibile fare riferimento a un membro di istanza di una classe all'interno di un metodo condiviso o di un inizializzatore di membri condivisi senza un'istanza esplicita della classe
ms.date: 07/20/2015
f1_keywords:
- vbc30369
- bc30369
helpviewer_keywords:
- Shared
- BC30369
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
ms.openlocfilehash: aad068b5857eb956ded63fa2a57cb163d3cf5c58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013842"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a><span data-ttu-id="1ab03-102">Impossibile fare riferimento a un membro di istanza di una classe all'interno di un metodo condiviso o di un inizializzatore di membri condivisi senza un'istanza esplicita della classe</span><span class="sxs-lookup"><span data-stu-id="1ab03-102">Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class</span></span>
<span data-ttu-id="1ab03-103">Si è provato a fare riferimento a un membro non condiviso di una classe all'interno di una routine condivisa.</span><span class="sxs-lookup"><span data-stu-id="1ab03-103">You have tried to refer to a non-shared member of a class from within a shared procedure.</span></span> <span data-ttu-id="1ab03-104">L'esempio seguente illustra una situazione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="1ab03-104">The following example demonstrates such a situation.</span></span>  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="1ab03-105">Nell'esempio precedente, l'istruzione di assegnazione `x = 10` genera questo messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="1ab03-105">In the preceding example, the assignment statement `x = 10` generates this error message.</span></span> <span data-ttu-id="1ab03-106">Questo avviene perché una procedura condivisa sta tentando di accedere a una variabile di istanza.</span><span class="sxs-lookup"><span data-stu-id="1ab03-106">This is because a shared procedure is attempting to access an instance variable.</span></span>  
  
 <span data-ttu-id="1ab03-107">La variabile `x` è un membro di istanza perché non è dichiarato come [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="1ab03-107">The variable `x` is an instance member because it is not declared as [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="1ab03-108">Ogni istanza della classe `sample` contiene il proprio variabile `x`.</span><span class="sxs-lookup"><span data-stu-id="1ab03-108">Each instance of class `sample` contains its own individual variable `x`.</span></span> <span data-ttu-id="1ab03-109">Quando di impostazione o modifica il valore di un'istanza `x`, non influenza il valore di `x` in qualsiasi altra istanza.</span><span class="sxs-lookup"><span data-stu-id="1ab03-109">When one instance sets or changes the value of `x`, it does not affect the value of `x` in any other instance.</span></span>  
  
 <span data-ttu-id="1ab03-110">Tuttavia, la procedura `setX` viene `Shared` tra tutte le istanze della classe `sample`.</span><span class="sxs-lookup"><span data-stu-id="1ab03-110">However, the procedure `setX` is `Shared` among all instances of class `sample`.</span></span> <span data-ttu-id="1ab03-111">Ciò significa non è associato ad alcuna istanza della classe, ma piuttosto opera indipendentemente dalle singole istanze.</span><span class="sxs-lookup"><span data-stu-id="1ab03-111">This means it is not associated with any one instance of the class, but rather operates independently of individual instances.</span></span> <span data-ttu-id="1ab03-112">Poiché non dispone di alcuna connessione con una particolare istanza `setX` non può accedere a una variabile di istanza.</span><span class="sxs-lookup"><span data-stu-id="1ab03-112">Because it has no connection with a particular instance, `setX` cannot access an instance variable.</span></span> <span data-ttu-id="1ab03-113">E deve essere utilizzata solo in `Shared` variabili.</span><span class="sxs-lookup"><span data-stu-id="1ab03-113">It must operate only on `Shared` variables.</span></span> <span data-ttu-id="1ab03-114">Quando `setX` imposta o modifica il valore di una variabile condivisa, che nuovo valore è disponibile per tutte le istanze della classe.</span><span class="sxs-lookup"><span data-stu-id="1ab03-114">When `setX` sets or changes the value of a shared variable, that new value is available to all instances of the class.</span></span>  
  
 <span data-ttu-id="1ab03-115">**ID errore:** BC30369</span><span class="sxs-lookup"><span data-stu-id="1ab03-115">**Error ID:** BC30369</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1ab03-116">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="1ab03-116">To correct this error</span></span>  
  
1. <span data-ttu-id="1ab03-117">Decidere se il membro venga condiviso tra tutte le istanze della classe o mantenuto singoli per ogni istanza.</span><span class="sxs-lookup"><span data-stu-id="1ab03-117">Decide whether you want the member to be shared among all instances of the class, or kept individual for each instance.</span></span>  
  
2. <span data-ttu-id="1ab03-118">Se si desidera che una singola copia del membro venga condiviso tra tutte le istanze, aggiungere il `Shared` parola chiave per la dichiarazione del membro.</span><span class="sxs-lookup"><span data-stu-id="1ab03-118">If you want a single copy of the member to be shared among all instances, add the `Shared` keyword to the member declaration.</span></span> <span data-ttu-id="1ab03-119">Mantenere il `Shared` parola chiave nella dichiarazione di routine.</span><span class="sxs-lookup"><span data-stu-id="1ab03-119">Retain the `Shared` keyword in the procedure declaration.</span></span>  
  
3. <span data-ttu-id="1ab03-120">Se si vuole che ogni istanza per mantenere la propria copia del membro, non specificare `Shared` per la dichiarazione di membro.</span><span class="sxs-lookup"><span data-stu-id="1ab03-120">If you want each instance to have its own individual copy of the member, do not specify `Shared` for the member declaration.</span></span> <span data-ttu-id="1ab03-121">Rimuovere il `Shared` parola chiave dalla dichiarazione di routine.</span><span class="sxs-lookup"><span data-stu-id="1ab03-121">Remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab03-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ab03-122">See also</span></span>

- [<span data-ttu-id="1ab03-123">Shared</span><span class="sxs-lookup"><span data-stu-id="1ab03-123">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)

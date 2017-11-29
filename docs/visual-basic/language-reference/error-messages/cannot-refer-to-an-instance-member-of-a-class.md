---
title: Impossibile fare riferimento a un membro di istanza di una classe all'interno di un metodo condiviso o di un inizializzatore di membri condivisi senza un'istanza esplicita della classe
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30369
- bc30369
helpviewer_keywords:
- Shared
- BC30369
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6a15d36c0b3a4d6b1657d583de0dc61621da960d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a><span data-ttu-id="fcc71-102">Impossibile fare riferimento a un membro di istanza di una classe all'interno di un metodo condiviso o di un inizializzatore di membri condivisi senza un'istanza esplicita della classe</span><span class="sxs-lookup"><span data-stu-id="fcc71-102">Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class</span></span>
<span data-ttu-id="fcc71-103">Si è tentato di fare riferimento a un membro non condiviso di una classe all'interno di una routine condivisa.</span><span class="sxs-lookup"><span data-stu-id="fcc71-103">You have tried to refer to a non-shared member of a class from within a shared procedure.</span></span> <span data-ttu-id="fcc71-104">L'esempio seguente illustra una situazione.</span><span class="sxs-lookup"><span data-stu-id="fcc71-104">The following example demonstrates such a situation.</span></span>  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="fcc71-105">Nell'esempio precedente, l'istruzione di assegnazione `x = 10` genera questo messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="fcc71-105">In the preceding example, the assignment statement `x = 10` generates this error message.</span></span> <span data-ttu-id="fcc71-106">Questo avviene perché una routine condivisa sta tentando di accedere a una variabile di istanza.</span><span class="sxs-lookup"><span data-stu-id="fcc71-106">This is because a shared procedure is attempting to access an instance variable.</span></span>  
  
 <span data-ttu-id="fcc71-107">La variabile `x` è un membro di istanza perché non è dichiarato come [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="fcc71-107">The variable `x` is an instance member because it is not declared as [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="fcc71-108">Ogni istanza della classe `sample` contiene una specifica variabile `x`.</span><span class="sxs-lookup"><span data-stu-id="fcc71-108">Each instance of class `sample` contains its own individual variable `x`.</span></span> <span data-ttu-id="fcc71-109">Quando un'istanza imposta o modifica il valore di `x`, non si applica il valore di `x` nelle altre istanze.</span><span class="sxs-lookup"><span data-stu-id="fcc71-109">When one instance sets or changes the value of `x`, it does not affect the value of `x` in any other instance.</span></span>  
  
 <span data-ttu-id="fcc71-110">Tuttavia, la procedura `setX` è `Shared` tra tutte le istanze della classe `sample`.</span><span class="sxs-lookup"><span data-stu-id="fcc71-110">However, the procedure `setX` is `Shared` among all instances of class `sample`.</span></span> <span data-ttu-id="fcc71-111">Ciò significa non è associata a ogni istanza della classe, ma funziona in modo indipendente da singole istanze.</span><span class="sxs-lookup"><span data-stu-id="fcc71-111">This means it is not associated with any one instance of the class, but rather operates independently of individual instances.</span></span> <span data-ttu-id="fcc71-112">Poiché dispone di alcuna connessione con una particolare istanza `setX` non è possibile accedere a una variabile di istanza.</span><span class="sxs-lookup"><span data-stu-id="fcc71-112">Because it has no connection with a particular instance, `setX` cannot access an instance variable.</span></span> <span data-ttu-id="fcc71-113">Deve essere utilizzata solo per `Shared` variabili.</span><span class="sxs-lookup"><span data-stu-id="fcc71-113">It must operate only on `Shared` variables.</span></span> <span data-ttu-id="fcc71-114">Quando `setX` imposta o modifica il valore di una variabile condivisa, che è disponibile per tutte le istanze della classe nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="fcc71-114">When `setX` sets or changes the value of a shared variable, that new value is available to all instances of the class.</span></span>  
  
 <span data-ttu-id="fcc71-115">**ID errore:** BC30369</span><span class="sxs-lookup"><span data-stu-id="fcc71-115">**Error ID:** BC30369</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fcc71-116">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="fcc71-116">To correct this error</span></span>  
  
1.  <span data-ttu-id="fcc71-117">Decidere se il membro condiviso tra tutte le istanze della classe o mantenuto singoli per ogni istanza.</span><span class="sxs-lookup"><span data-stu-id="fcc71-117">Decide whether you want the member to be shared among all instances of the class, or kept individual for each instance.</span></span>  
  
2.  <span data-ttu-id="fcc71-118">Se si desidera una singola copia del membro per essere condivisi tra tutte le istanze, aggiungere il `Shared` (parola chiave) alla dichiarazione del membro.</span><span class="sxs-lookup"><span data-stu-id="fcc71-118">If you want a single copy of the member to be shared among all instances, add the `Shared` keyword to the member declaration.</span></span> <span data-ttu-id="fcc71-119">Mantenere il `Shared` parola chiave nella dichiarazione di routine.</span><span class="sxs-lookup"><span data-stu-id="fcc71-119">Retain the `Shared` keyword in the procedure declaration.</span></span>  
  
3.  <span data-ttu-id="fcc71-120">Se si desidera che ogni istanza per la propria copia del membro singola, non specificare `Shared` per la dichiarazione di membro.</span><span class="sxs-lookup"><span data-stu-id="fcc71-120">If you want each instance to have its own individual copy of the member, do not specify `Shared` for the member declaration.</span></span> <span data-ttu-id="fcc71-121">Rimuovere il `Shared` parola chiave dalla dichiarazione di routine.</span><span class="sxs-lookup"><span data-stu-id="fcc71-121">Remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc71-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcc71-122">See Also</span></span>  
 [<span data-ttu-id="fcc71-123">Shared</span><span class="sxs-lookup"><span data-stu-id="fcc71-123">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)

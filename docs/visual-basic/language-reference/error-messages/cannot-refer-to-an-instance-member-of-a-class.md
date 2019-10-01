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
ms.openlocfilehash: a2a5ab99ff68e6dce783a2fd986ee6e8c15ae858
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701169"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a><span data-ttu-id="b3bad-102">Impossibile fare riferimento a un membro di istanza di una classe all'interno di un metodo condiviso o di un inizializzatore di membri condivisi senza un'istanza esplicita della classe</span><span class="sxs-lookup"><span data-stu-id="b3bad-102">Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class</span></span>
<span data-ttu-id="b3bad-103">Si è tentato di fare riferimento a un membro non condiviso di una classe all'interno di una procedura condivisa.</span><span class="sxs-lookup"><span data-stu-id="b3bad-103">You have tried to refer to a non-shared member of a class from within a shared procedure.</span></span> <span data-ttu-id="b3bad-104">Nell'esempio seguente viene illustrata una situazione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="b3bad-104">The following example demonstrates such a situation.</span></span>  
  
```vb  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="b3bad-105">Nell'esempio precedente, l'istruzione di assegnazione `x = 10` genera questo messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="b3bad-105">In the preceding example, the assignment statement `x = 10` generates this error message.</span></span> <span data-ttu-id="b3bad-106">Questo perché una procedura condivisa sta tentando di accedere a una variabile di istanza.</span><span class="sxs-lookup"><span data-stu-id="b3bad-106">This is because a shared procedure is attempting to access an instance variable.</span></span>  
  
 <span data-ttu-id="b3bad-107">La variabile `x` è un membro di istanza perché non è dichiarata come [condivisa](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="b3bad-107">The variable `x` is an instance member because it is not declared as [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="b3bad-108">Ogni istanza della classe `sample` contiene la propria variabile singola `x`.</span><span class="sxs-lookup"><span data-stu-id="b3bad-108">Each instance of class `sample` contains its own individual variable `x`.</span></span> <span data-ttu-id="b3bad-109">Quando un'istanza imposta o modifica il valore di `x`, non influisce sul valore di `x` in nessun'altra istanza.</span><span class="sxs-lookup"><span data-stu-id="b3bad-109">When one instance sets or changes the value of `x`, it does not affect the value of `x` in any other instance.</span></span>  
  
 <span data-ttu-id="b3bad-110">Tuttavia, la procedura `setX` è `Shared` tra tutte le istanze della classe `sample`.</span><span class="sxs-lookup"><span data-stu-id="b3bad-110">However, the procedure `setX` is `Shared` among all instances of class `sample`.</span></span> <span data-ttu-id="b3bad-111">Ciò significa che non è associato a una sola istanza della classe, ma funziona in modo indipendente dalle singole istanze.</span><span class="sxs-lookup"><span data-stu-id="b3bad-111">This means it is not associated with any one instance of the class, but rather operates independently of individual instances.</span></span> <span data-ttu-id="b3bad-112">Poiché non dispone di una connessione a un'istanza specifica, `setX` non è in grado di accedere a una variabile di istanza.</span><span class="sxs-lookup"><span data-stu-id="b3bad-112">Because it has no connection with a particular instance, `setX` cannot access an instance variable.</span></span> <span data-ttu-id="b3bad-113">Deve funzionare solo su variabili `Shared`.</span><span class="sxs-lookup"><span data-stu-id="b3bad-113">It must operate only on `Shared` variables.</span></span> <span data-ttu-id="b3bad-114">Quando `setX` imposta o modifica il valore di una variabile condivisa, il nuovo valore è disponibile per tutte le istanze della classe.</span><span class="sxs-lookup"><span data-stu-id="b3bad-114">When `setX` sets or changes the value of a shared variable, that new value is available to all instances of the class.</span></span>  
  
 <span data-ttu-id="b3bad-115">**ID errore:** BC30369</span><span class="sxs-lookup"><span data-stu-id="b3bad-115">**Error ID:** BC30369</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b3bad-116">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b3bad-116">To correct this error</span></span>  
  
1. <span data-ttu-id="b3bad-117">Decidere se si desidera che il membro venga condiviso tra tutte le istanze della classe o mantenuti singoli per ogni istanza.</span><span class="sxs-lookup"><span data-stu-id="b3bad-117">Decide whether you want the member to be shared among all instances of the class, or kept individual for each instance.</span></span>  
  
2. <span data-ttu-id="b3bad-118">Se si desidera che una sola copia del membro venga condivisa tra tutte le istanze, aggiungere la parola chiave `Shared` alla dichiarazione del membro.</span><span class="sxs-lookup"><span data-stu-id="b3bad-118">If you want a single copy of the member to be shared among all instances, add the `Shared` keyword to the member declaration.</span></span> <span data-ttu-id="b3bad-119">Mantenere la parola chiave `Shared` nella dichiarazione di routine.</span><span class="sxs-lookup"><span data-stu-id="b3bad-119">Retain the `Shared` keyword in the procedure declaration.</span></span>  
  
3. <span data-ttu-id="b3bad-120">Se si desidera che ogni istanza disponga di una copia singola del membro, non specificare `Shared` per la dichiarazione del membro.</span><span class="sxs-lookup"><span data-stu-id="b3bad-120">If you want each instance to have its own individual copy of the member, do not specify `Shared` for the member declaration.</span></span> <span data-ttu-id="b3bad-121">Rimuovere la parola chiave `Shared` dalla dichiarazione di routine.</span><span class="sxs-lookup"><span data-stu-id="b3bad-121">Remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3bad-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3bad-122">See also</span></span>

- [<span data-ttu-id="b3bad-123">Shared</span><span class="sxs-lookup"><span data-stu-id="b3bad-123">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)

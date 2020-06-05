---
title: La matrice è fissa o temporaneamente bloccata
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: 4a86460104b6c4d9d6791e60f6f377cec0030425
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363033"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="b6574-102">La matrice è fissa o temporaneamente bloccata (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6574-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="b6574-103">Questo errore presenta le possibili cause seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6574-103">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="b6574-104">Utilizzo `ReDim` di per modificare il numero di elementi di una matrice di dimensioni fisse.</span><span class="sxs-lookup"><span data-stu-id="b6574-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
- <span data-ttu-id="b6574-105">Ridimensionamento di una matrice dinamica a livello di modulo, in cui un elemento è stato passato come argomento a una routine.</span><span class="sxs-lookup"><span data-stu-id="b6574-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="b6574-106">Se viene passato un elemento, la matrice viene bloccata per impedire la deallocazione della memoria per il parametro Reference all'interno della procedura.</span><span class="sxs-lookup"><span data-stu-id="b6574-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
- <span data-ttu-id="b6574-107">Tentativo di assegnare un valore a una `Variant` variabile contenente una matrice, ma l'oggetto `Variant` è attualmente bloccato.</span><span class="sxs-lookup"><span data-stu-id="b6574-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b6574-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b6574-108">To correct this error</span></span>  
  
1. <span data-ttu-id="b6574-109">Rendere la matrice originale dinamica anziché fissa dichiarando `ReDim` (se la matrice è dichiarata all'interno di una routine) o dichiarando tale matrice senza specificare il numero di elementi (se la matrice viene dichiarata a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="b6574-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2. <span data-ttu-id="b6574-110">Determinare se è effettivamente necessario passare l'elemento, perché è visibile all'interno di tutte le routine del modulo.</span><span class="sxs-lookup"><span data-stu-id="b6574-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3. <span data-ttu-id="b6574-111">Determinare gli elementi che bloccano `Variant` e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="b6574-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6574-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6574-112">See also</span></span>

- [<span data-ttu-id="b6574-113">Matrici</span><span class="sxs-lookup"><span data-stu-id="b6574-113">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)

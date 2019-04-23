---
title: La matrice è fissa o temporaneamente bloccata (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: c74d9524ff64101ba6002e133b93c9b80e8f50a9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337968"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="99b25-102">La matrice è fissa o temporaneamente bloccata (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99b25-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="99b25-103">Questo errore sono le seguenti cause possibili:</span><span class="sxs-lookup"><span data-stu-id="99b25-103">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="99b25-104">Usando `ReDim` per modificare il numero di elementi di una matrice di dimensioni fisse.</span><span class="sxs-lookup"><span data-stu-id="99b25-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
-   <span data-ttu-id="99b25-105">Ridimensionamento di una matrice dinamica a livello di modulo, in cui un elemento è stato passato come argomento a una routine.</span><span class="sxs-lookup"><span data-stu-id="99b25-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="99b25-106">Se viene passato un elemento, la matrice è bloccata per evitare la deallocazione di memoria per il parametro di riferimento all'interno della routine.</span><span class="sxs-lookup"><span data-stu-id="99b25-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
-   <span data-ttu-id="99b25-107">Tentativo di assegnare un valore a un `Variant` variabile che contiene una matrice, ma il `Variant` è attualmente bloccato.</span><span class="sxs-lookup"><span data-stu-id="99b25-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="99b25-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="99b25-108">To correct this error</span></span>  
  
1. <span data-ttu-id="99b25-109">Rendere la matrice originale dinamica anziché fissa dichiarandolo con `ReDim` (se la matrice viene dichiarata all'interno di una procedura), oppure dichiarandolo senza specificare il numero di elementi (se la matrice viene dichiarata a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="99b25-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2. <span data-ttu-id="99b25-110">Determinare se è realmente necessario passare l'elemento, dato che è visibile all'interno di tutte le procedure nel modulo.</span><span class="sxs-lookup"><span data-stu-id="99b25-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3. <span data-ttu-id="99b25-111">Determinare quali blocchi di `Variant` e porvi rimedio.</span><span class="sxs-lookup"><span data-stu-id="99b25-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99b25-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99b25-112">See also</span></span>

- [<span data-ttu-id="99b25-113">Matrici</span><span class="sxs-lookup"><span data-stu-id="99b25-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)

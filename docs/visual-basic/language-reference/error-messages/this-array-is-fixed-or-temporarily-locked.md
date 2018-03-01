---
title: "La matrice è fissa o temporaneamente bloccata (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: adff10d4ae61e45402df64ebaa3baf146371ff9e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="742e1-102">La matrice è fissa o temporaneamente bloccata (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="742e1-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="742e1-103">Questo errore sono le seguenti cause possibili:</span><span class="sxs-lookup"><span data-stu-id="742e1-103">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="742e1-104">Utilizzando `ReDim` per modificare il numero di elementi di una matrice di dimensioni fisse.</span><span class="sxs-lookup"><span data-stu-id="742e1-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
-   <span data-ttu-id="742e1-105">Ridimensionamento di una matrice dinamica a livello di modulo, in cui un elemento è stato passato come argomento a una routine.</span><span class="sxs-lookup"><span data-stu-id="742e1-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="742e1-106">Se un elemento viene passato, la matrice è bloccata per impedire la deallocazione di memoria per il parametro di riferimento all'interno della routine.</span><span class="sxs-lookup"><span data-stu-id="742e1-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
-   <span data-ttu-id="742e1-107">Il tentativo di assegnare un valore a un `Variant` variabile che contiene una matrice, ma la `Variant` è attualmente bloccato.</span><span class="sxs-lookup"><span data-stu-id="742e1-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="742e1-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="742e1-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="742e1-109">Rendere la matrice originale dinamica anziché dichiarandola con `ReDim` (se è dichiarata all'interno di una stored procedure), sia che venga dichiarata senza specificare il numero di elementi (se la matrice viene dichiarata a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="742e1-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2.  <span data-ttu-id="742e1-110">Determinare se sia necessario per passare l'elemento, dato che è visibile all'interno di tutte le procedure nel modulo.</span><span class="sxs-lookup"><span data-stu-id="742e1-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3.  <span data-ttu-id="742e1-111">Stabilire cosa blocca il `Variant` e correzione.</span><span class="sxs-lookup"><span data-stu-id="742e1-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="742e1-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="742e1-112">See Also</span></span>  
 [<span data-ttu-id="742e1-113">Array</span><span class="sxs-lookup"><span data-stu-id="742e1-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)

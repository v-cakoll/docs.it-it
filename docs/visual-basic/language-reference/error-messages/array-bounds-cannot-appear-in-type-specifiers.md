---
title: I limiti di matrice non possono trovarsi negli identificatori di tipo
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 770f86ca960110965b6917a22d284678ff8b6f8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="835e4-102">I limiti di matrice non possono trovarsi negli identificatori di tipo</span><span class="sxs-lookup"><span data-stu-id="835e4-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="835e4-103">Le dimensioni di matrice non possono essere dichiarate come parte di un identificatore di tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="835e4-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="835e4-104">**ID errore:** BC30638</span><span class="sxs-lookup"><span data-stu-id="835e4-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="835e4-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="835e4-105">To correct this error</span></span>  
  
-   <span data-ttu-id="835e4-106">Specificare le dimensioni della matrice subito dopo il nome della variabile anziché inserire le dimensioni della matrice dopo il tipo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="835e4-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   <span data-ttu-id="835e4-107">Definire una matrice e inizializzarlo con il numero desiderato di elementi, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="835e4-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="835e4-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="835e4-108">See Also</span></span>  
 [<span data-ttu-id="835e4-109">Array</span><span class="sxs-lookup"><span data-stu-id="835e4-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)

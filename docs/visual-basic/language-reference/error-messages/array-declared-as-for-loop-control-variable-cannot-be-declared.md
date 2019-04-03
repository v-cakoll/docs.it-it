---
title: La matrice dichiarata come variabile per il controllo del ciclo non può essere dichiarata con dimensione iniziale
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: bee3bcd3701945f5cf77f6761defc8be77acf49f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843578"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="f90b3-102">La matrice dichiarata come variabile per il controllo del ciclo non può essere dichiarata con dimensione iniziale</span><span class="sxs-lookup"><span data-stu-id="f90b3-102">Array declared as for loop control variable cannot be declared with an initial size</span></span>
<span data-ttu-id="f90b3-103">Oggetto `For Each` ciclo viene utilizzato come una matrice relativa *elemento* esegue l'inizializzazione della variabile di iterazione della matrice.</span><span class="sxs-lookup"><span data-stu-id="f90b3-103">A `For Each` loop uses an array as its *element* iteration variable but initializes that array.</span></span>  
  
 <span data-ttu-id="f90b3-104">Le istruzioni seguenti mostrano come questo errore può essere generato.</span><span class="sxs-lookup"><span data-stu-id="f90b3-104">The following statements show how this error can be generated.</span></span>  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 <span data-ttu-id="f90b3-105">Il primo `For Each` istruzione è il modo corretto per accedere agli elementi di `arrayList`.</span><span class="sxs-lookup"><span data-stu-id="f90b3-105">The first `For Each` statement is the correct way to access elements of `arrayList`.</span></span> <span data-ttu-id="f90b3-106">Il secondo `For Each` istruzione genera questo errore.</span><span class="sxs-lookup"><span data-stu-id="f90b3-106">The second `For Each` statement generates this error.</span></span>  
  
 <span data-ttu-id="f90b3-107">**ID errore:** BC32039</span><span class="sxs-lookup"><span data-stu-id="f90b3-107">**Error ID:** BC32039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f90b3-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f90b3-108">To correct this error</span></span>  
  
-   <span data-ttu-id="f90b3-109">Rimuovere l'inizializzazione dalla dichiarazione del *elemento* variabile di iterazione.</span><span class="sxs-lookup"><span data-stu-id="f90b3-109">Remove the initialization from the declaration of the *element* iteration variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f90b3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f90b3-110">See also</span></span>

- [<span data-ttu-id="f90b3-111">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="f90b3-111">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="f90b3-112">Matrici</span><span class="sxs-lookup"><span data-stu-id="f90b3-112">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="f90b3-113">Raccolte</span><span class="sxs-lookup"><span data-stu-id="f90b3-113">Collections</span></span>](../../../standard/collections/index.md)

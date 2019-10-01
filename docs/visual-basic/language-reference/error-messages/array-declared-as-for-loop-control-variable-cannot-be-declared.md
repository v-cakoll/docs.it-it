---
title: La matrice dichiarata come variabile per il controllo del ciclo non può essere dichiarata con dimensione iniziale
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: 9e8bb7b79b5a770c3c92e47d8e7c01c5b83d6061
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701214"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="a47a8-102">La matrice dichiarata come variabile per il controllo del ciclo non può essere dichiarata con dimensione iniziale</span><span class="sxs-lookup"><span data-stu-id="a47a8-102">Array declared as for loop control variable cannot be declared with an initial size</span></span>
<span data-ttu-id="a47a8-103">Un ciclo `For Each` usa una matrice come variabile di iterazione dell' *elemento* , ma Inizializza la matrice.</span><span class="sxs-lookup"><span data-stu-id="a47a8-103">A `For Each` loop uses an array as its *element* iteration variable but initializes that array.</span></span>  
  
 <span data-ttu-id="a47a8-104">Nelle istruzioni seguenti viene illustrato come è possibile generare questo errore.</span><span class="sxs-lookup"><span data-stu-id="a47a8-104">The following statements show how this error can be generated.</span></span>  
  
```vb  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 <span data-ttu-id="a47a8-105">La prima istruzione `For Each` rappresenta il modo corretto per accedere agli elementi di `arrayList`.</span><span class="sxs-lookup"><span data-stu-id="a47a8-105">The first `For Each` statement is the correct way to access elements of `arrayList`.</span></span> <span data-ttu-id="a47a8-106">La seconda istruzione `For Each` genera questo errore.</span><span class="sxs-lookup"><span data-stu-id="a47a8-106">The second `For Each` statement generates this error.</span></span>  
  
 <span data-ttu-id="a47a8-107">**ID errore:** BC32039</span><span class="sxs-lookup"><span data-stu-id="a47a8-107">**Error ID:** BC32039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a47a8-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a47a8-108">To correct this error</span></span>  
  
- <span data-ttu-id="a47a8-109">Rimuovere l'inizializzazione dalla dichiarazione della variabile di iterazione dell' *elemento* .</span><span class="sxs-lookup"><span data-stu-id="a47a8-109">Remove the initialization from the declaration of the *element* iteration variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a47a8-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a47a8-110">See also</span></span>

- [<span data-ttu-id="a47a8-111">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="a47a8-111">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="a47a8-112">Matrici</span><span class="sxs-lookup"><span data-stu-id="a47a8-112">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="a47a8-113">Raccolte</span><span class="sxs-lookup"><span data-stu-id="a47a8-113">Collections</span></span>](../../../standard/collections/index.md)

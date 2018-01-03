---
title: "La matrice dichiarata come variabile per il controllo del ciclo non può essere dichiarata con dimensione iniziale"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords: BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef36f14d5323a4592afe59573e249d8cfb218df9
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="faf3b-102">La matrice dichiarata come variabile per il controllo del ciclo non può essere dichiarata con dimensione iniziale</span><span class="sxs-lookup"><span data-stu-id="faf3b-102">Array declared as for loop control variable cannot be declared with an initial size</span></span>
<span data-ttu-id="faf3b-103">Oggetto `For Each` ciclo utilizza una matrice come relativo *elemento* variabile di iterazione l'inizializzazione di matrice.</span><span class="sxs-lookup"><span data-stu-id="faf3b-103">A `For Each` loop uses an array as its *element* iteration variable but initializes that array.</span></span>  
  
 <span data-ttu-id="faf3b-104">Le istruzioni seguenti mostrano come questo errore può essere generato.</span><span class="sxs-lookup"><span data-stu-id="faf3b-104">The following statements show how this error can be generated.</span></span>  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 <span data-ttu-id="faf3b-105">Il primo `For Each` istruzione è il modo corretto per accedere agli elementi di `arrayList`.</span><span class="sxs-lookup"><span data-stu-id="faf3b-105">The first `For Each` statement is the correct way to access elements of `arrayList`.</span></span> <span data-ttu-id="faf3b-106">Il secondo `For Each` istruzione genera questo errore.</span><span class="sxs-lookup"><span data-stu-id="faf3b-106">The second `For Each` statement generates this error.</span></span>  
  
 <span data-ttu-id="faf3b-107">**ID errore:** BC32039</span><span class="sxs-lookup"><span data-stu-id="faf3b-107">**Error ID:** BC32039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="faf3b-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="faf3b-108">To correct this error</span></span>  
  
-   <span data-ttu-id="faf3b-109">Rimuovere l'inizializzazione dalla dichiarazione del *elemento* variabile di iterazione.</span><span class="sxs-lookup"><span data-stu-id="faf3b-109">Remove the initialization from the declaration of the *element* iteration variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faf3b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="faf3b-110">See Also</span></span>  
 [<span data-ttu-id="faf3b-111">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="faf3b-111">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="faf3b-112">Array</span><span class="sxs-lookup"><span data-stu-id="faf3b-112">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="faf3b-113">Raccolte</span><span class="sxs-lookup"><span data-stu-id="faf3b-113">Collections</span></span>](../../../standard/collections/index.md)

---
title: Le matrici dichiarate come membri di struttura non possono essere dichiarate con una grandezza iniziale
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 983154a144a79991c86db5056ad0e0e563a3ba73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="df12f-102">Le matrici dichiarate come membri di struttura non possono essere dichiarate con una grandezza iniziale</span><span class="sxs-lookup"><span data-stu-id="df12f-102">Arrays declared as structure members cannot be declared with an initial size</span></span>
<span data-ttu-id="df12f-103">Matrice in una struttura è dichiarata con una dimensione iniziale.</span><span class="sxs-lookup"><span data-stu-id="df12f-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="df12f-104">Non è possibile inizializzare qualsiasi elemento di struttura e la dichiarazione di una dimensione di matrice è una forma di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="df12f-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>  
  
 <span data-ttu-id="df12f-105">**ID errore:** BC31043</span><span class="sxs-lookup"><span data-stu-id="df12f-105">**Error ID:** BC31043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="df12f-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="df12f-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="df12f-107">Definire la matrice della struttura come dinamica (dimensione iniziale).</span><span class="sxs-lookup"><span data-stu-id="df12f-107">Define the array in your structure as dynamic (no initial size).</span></span>  
  
2.  <span data-ttu-id="df12f-108">Se è necessaria una determinata dimensione della matrice, è possibile ridimensionare una matrice dinamica con un [istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md) quando viene eseguito il codice.</span><span class="sxs-lookup"><span data-stu-id="df12f-108">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="df12f-109">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="df12f-109">The following example illustrates this.</span></span>  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="df12f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df12f-110">See Also</span></span>  
 [<span data-ttu-id="df12f-111">Array</span><span class="sxs-lookup"><span data-stu-id="df12f-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="df12f-112">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="df12f-112">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)

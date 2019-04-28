---
title: Le matrici dichiarate come membri di struttura non possono essere dichiarate con una grandezza iniziale
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 5d58b531b670715716e849cd37227bc899195df6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935369"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="7d299-102">Le matrici dichiarate come membri di struttura non possono essere dichiarate con una grandezza iniziale</span><span class="sxs-lookup"><span data-stu-id="7d299-102">Arrays declared as structure members cannot be declared with an initial size</span></span>
<span data-ttu-id="7d299-103">Matrice in una struttura è dichiarata con una dimensione iniziale.</span><span class="sxs-lookup"><span data-stu-id="7d299-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="7d299-104">Non è possibile inizializzare qualsiasi elemento di struttura e la dichiarazione di una dimensione della matrice è una forma di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="7d299-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>  
  
 <span data-ttu-id="7d299-105">**ID errore:** BC31043</span><span class="sxs-lookup"><span data-stu-id="7d299-105">**Error ID:** BC31043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7d299-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7d299-106">To correct this error</span></span>  
  
1. <span data-ttu-id="7d299-107">Definire la matrice in una struttura come dinamico (Nessuna dimensione iniziale).</span><span class="sxs-lookup"><span data-stu-id="7d299-107">Define the array in your structure as dynamic (no initial size).</span></span>  
  
2. <span data-ttu-id="7d299-108">Se è necessaria una determinata dimensione della matrice, è possibile ridimensionare una matrice dinamica con un [istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md) quando viene eseguito il codice.</span><span class="sxs-lookup"><span data-stu-id="7d299-108">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="7d299-109">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7d299-109">The following example illustrates this.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7d299-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d299-110">See also</span></span>

- [<span data-ttu-id="7d299-111">Matrici</span><span class="sxs-lookup"><span data-stu-id="7d299-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="7d299-112">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="7d299-112">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)

---
title: Le matrici dichiarate come membri di struttura non possono essere dichiarate con una grandezza iniziale
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: de9d77aa9ea853b6f044e91878044115588ca77c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701242"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="d30a9-102">Le matrici dichiarate come membri di struttura non possono essere dichiarate con una grandezza iniziale</span><span class="sxs-lookup"><span data-stu-id="d30a9-102">Arrays declared as structure members cannot be declared with an initial size</span></span>
<span data-ttu-id="d30a9-103">Una matrice in una struttura viene dichiarata con una dimensione iniziale.</span><span class="sxs-lookup"><span data-stu-id="d30a9-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="d30a9-104">Non è possibile inizializzare alcun elemento della struttura e la dichiarazione di una dimensione della matrice è una forma di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="d30a9-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>  
  
 <span data-ttu-id="d30a9-105">**ID errore:** BC31043</span><span class="sxs-lookup"><span data-stu-id="d30a9-105">**Error ID:** BC31043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d30a9-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d30a9-106">To correct this error</span></span>  
  
1. <span data-ttu-id="d30a9-107">Definire la matrice nella struttura come dinamica (nessuna dimensione iniziale).</span><span class="sxs-lookup"><span data-stu-id="d30a9-107">Define the array in your structure as dynamic (no initial size).</span></span>  
  
2. <span data-ttu-id="d30a9-108">Se è necessaria una determinata dimensione della matrice, è possibile ridimensionare una matrice dinamica con un' [istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md) quando il codice è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d30a9-108">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="d30a9-109">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d30a9-109">The following example illustrates this.</span></span>  
  
    ```vb  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d30a9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d30a9-110">See also</span></span>

- [<span data-ttu-id="d30a9-111">Matrici</span><span class="sxs-lookup"><span data-stu-id="d30a9-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="d30a9-112">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="d30a9-112">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)

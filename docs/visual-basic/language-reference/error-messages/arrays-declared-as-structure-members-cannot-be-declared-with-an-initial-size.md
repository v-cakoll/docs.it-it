---
title: Le matrici dichiarate come membri di struttura non possono essere dichiarate con una grandezza iniziale
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 83342b780c0fa7c3a2e0a6797b80ef788117ae92
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250149"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="4bde7-102">Le matrici dichiarate come membri di struttura non possono essere dichiarate con una grandezza iniziale</span><span class="sxs-lookup"><span data-stu-id="4bde7-102">Arrays declared as structure members cannot be declared with an initial size</span></span>

<span data-ttu-id="4bde7-103">Una matrice in una struttura viene dichiarata con una dimensione iniziale.</span><span class="sxs-lookup"><span data-stu-id="4bde7-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="4bde7-104">Non è possibile inizializzare alcun elemento della struttura e la dichiarazione di una dimensione della matrice è una forma di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="4bde7-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>

<span data-ttu-id="4bde7-105">**ID errore:** BC31043</span><span class="sxs-lookup"><span data-stu-id="4bde7-105">**Error ID:** BC31043</span></span>

## <a name="example"></a><span data-ttu-id="4bde7-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4bde7-106">Example</span></span>

<span data-ttu-id="4bde7-107">L'esempio seguente genera l'BC31043:</span><span class="sxs-lookup"><span data-stu-id="4bde7-107">The following example generates BC31043:</span></span>

```vb
Structure DemoStruct
    Public demoArray(9) As Integer
End Structure
```

## <a name="to-correct-this-error"></a><span data-ttu-id="4bde7-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4bde7-108">To correct this error</span></span>

1. <span data-ttu-id="4bde7-109">Definire la matrice nella struttura come dinamica (nessuna dimensione iniziale).</span><span class="sxs-lookup"><span data-stu-id="4bde7-109">Define the array in your structure as dynamic (no initial size).</span></span>

2. <span data-ttu-id="4bde7-110">Se è necessaria una determinata dimensione della matrice, è possibile ridimensionare una matrice dinamica con un' [istruzione ReDim](../statements/redim-statement.md) quando il codice è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4bde7-110">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="4bde7-111">Questa condizione è illustrata nell'esempio che segue.</span><span class="sxs-lookup"><span data-stu-id="4bde7-111">The following example illustrates this:</span></span>
  
    ```vb
    Structure DemoStruct
        Public demoArray() As Integer
    End Structure
    Sub UseStruct()
        Dim struct As DemoStruct  
        ReDim struct.demoArray(9)
        Struct.demoArray(2) = 777
    End Sub  
    ```
  
## <a name="see-also"></a><span data-ttu-id="4bde7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bde7-112">See also</span></span>

- [<span data-ttu-id="4bde7-113">Matrici</span><span class="sxs-lookup"><span data-stu-id="4bde7-113">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="4bde7-114">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="4bde7-114">How to: Declare a Structure</span></span>](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)

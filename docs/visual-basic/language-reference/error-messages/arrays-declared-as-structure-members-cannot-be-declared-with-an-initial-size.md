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
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>Le matrici dichiarate come membri di struttura non possono essere dichiarate con una grandezza iniziale

Una matrice in una struttura viene dichiarata con una dimensione iniziale. Non è possibile inizializzare alcun elemento della struttura e la dichiarazione di una dimensione della matrice è una forma di inizializzazione.

**ID errore:** BC31043

## <a name="example"></a>Esempio

L'esempio seguente genera l'BC31043:

```vb
Structure DemoStruct
    Public demoArray(9) As Integer
End Structure
```

## <a name="to-correct-this-error"></a>Per correggere l'errore

1. Definire la matrice nella struttura come dinamica (nessuna dimensione iniziale).

2. Se è necessaria una determinata dimensione della matrice, è possibile ridimensionare una matrice dinamica con un' [istruzione ReDim](../statements/redim-statement.md) quando il codice è in esecuzione. Questa condizione è illustrata nell'esempio che segue.
  
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
  
## <a name="see-also"></a>Vedere anche

- [Matrici](../../programming-guide/language-features/arrays/index.md)
- [Procedura: Dichiarare una struttura](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)

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
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>Le matrici dichiarate come membri di struttura non possono essere dichiarate con una grandezza iniziale
Una matrice in una struttura viene dichiarata con una dimensione iniziale. Non è possibile inizializzare alcun elemento della struttura e la dichiarazione di una dimensione della matrice è una forma di inizializzazione.  
  
 **ID errore:** BC31043  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Definire la matrice nella struttura come dinamica (nessuna dimensione iniziale).  
  
2. Se è necessaria una determinata dimensione della matrice, è possibile ridimensionare una matrice dinamica con un' [istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md) quando il codice è in esecuzione. Questa condizione è illustrata nell'esempio seguente.  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Procedura: Dichiarare una struttura](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)

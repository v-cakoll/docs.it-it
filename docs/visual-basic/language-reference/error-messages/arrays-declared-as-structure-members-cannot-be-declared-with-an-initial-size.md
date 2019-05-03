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
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>Le matrici dichiarate come membri di struttura non possono essere dichiarate con una grandezza iniziale
Matrice in una struttura è dichiarata con una dimensione iniziale. Non è possibile inizializzare qualsiasi elemento di struttura e la dichiarazione di una dimensione della matrice è una forma di inizializzazione.  
  
 **ID errore:** BC31043  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Definire la matrice in una struttura come dinamico (Nessuna dimensione iniziale).  
  
2. Se è necessaria una determinata dimensione della matrice, è possibile ridimensionare una matrice dinamica con un [istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md) quando viene eseguito il codice. Questa condizione è illustrata nell'esempio seguente.  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Procedura: Dichiarare una struttura](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)

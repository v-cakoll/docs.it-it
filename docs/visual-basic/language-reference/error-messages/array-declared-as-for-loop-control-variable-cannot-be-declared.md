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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935382"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a>La matrice dichiarata come variabile per il controllo del ciclo non può essere dichiarata con dimensione iniziale
Oggetto `For Each` ciclo viene utilizzato come una matrice relativa *elemento* esegue l'inizializzazione della variabile di iterazione della matrice.  
  
 Le istruzioni seguenti mostrano come questo errore può essere generato.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 Il primo `For Each` istruzione è il modo corretto per accedere agli elementi di `arrayList`. Il secondo `For Each` istruzione genera questo errore.  
  
 **ID errore:** BC32039  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Rimuovere l'inizializzazione dalla dichiarazione del *elemento* variabile di iterazione.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Raccolte](../../../standard/collections/index.md)

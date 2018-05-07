---
title: La matrice dichiarata come variabile per il controllo del ciclo non può essere dichiarata con dimensione iniziale
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: f6cf397b1e76313ab399d5e39a43ae0263df619c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a>La matrice dichiarata come variabile per il controllo del ciclo non può essere dichiarata con dimensione iniziale
Oggetto `For Each` ciclo utilizza una matrice come relativo *elemento* variabile di iterazione l'inizializzazione di matrice.  
  
 Le istruzioni seguenti mostrano come questo errore può essere generato.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 Il primo `For Each` istruzione è il modo corretto per accedere agli elementi di `arrayList`. Il secondo `For Each` istruzione genera questo errore.  
  
 **ID errore:** BC32039  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Rimuovere l'inizializzazione dalla dichiarazione del *elemento* variabile di iterazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Array](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Raccolte](../../../standard/collections/index.md)

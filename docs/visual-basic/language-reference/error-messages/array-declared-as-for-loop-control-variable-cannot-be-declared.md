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
ms.openlocfilehash: 0635e1b18b24a241fabad6d67da34f8dde9530db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
 [Raccolte](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)

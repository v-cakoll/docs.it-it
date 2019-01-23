---
title: Clausola Handles (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Handles
- vb.Handles
helpviewer_keywords:
- Handles keyword [Visual Basic]
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
ms.openlocfilehash: 45fa54d7f7a3e167ffe0545cc3edf6a24900b2b3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492962"
---
# <a name="handles-clause-visual-basic"></a>Clausola Handles (Visual Basic)
Dichiara che una routine gestisce un evento specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
proceduredeclaration Handles eventlist  
```  
  
## <a name="parts"></a>Parti  
 `proceduredeclaration`  
 Dichiarazione `Sub` per la routine che gestirà l'evento.  
  
 `eventlist`  
 Elenco degli eventi che devono essere gestiti da `proceduredeclaration`. Gli eventi devono essere generati dalla classe base per la classe corrente o da un oggetto dichiarato usando la parola chiave `WithEvents`.  
  
## <a name="remarks"></a>Note  
 Usare la parola chiave `Handles` alla fine di una dichiarazione di routine per fare in modo che la routine gestisca eventi generati da una variabile oggetto dichiarata con la parola chiave `WithEvents` . La parola chiave `Handles` può anche essere usata in una classe derivata per gestire eventi da una classe base.  
  
 La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze. Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento. L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione. Per altre informazioni, vedere [istruzione AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md).  
  
 Per gli eventi personalizzati, l'applicazione richiama la funzione di accesso `AddHandler` dell'evento quando aggiunge la routine come gestore eventi. Per altre informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrEvents#2](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_1.vb)]  
  
 L'esempio seguente illustra come una classe derivata può usare l'istruzione `Handles` per gestire un evento da una classe base.  
  
 [!code-vb[VbVbalrEvents#3](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_2.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente contiene due gestori eventi dei pulsanti per un **WPF Application** progetto.  
  
 [!code-vb[VbVbalrEvents#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_3.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio che segue equivale a quello precedente. L'oggetto `eventlist` nella clausola `Handles` contiene gli eventi per entrambi i pulsanti.  
  
 [!code-vb[VbVbalrEvents#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_4.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
- [Istruzione AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [Istruzione RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Istruzione RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
- [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)

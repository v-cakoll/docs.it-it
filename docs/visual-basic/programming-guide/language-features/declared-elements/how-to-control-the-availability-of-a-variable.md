---
title: 'Procedura: Controllare la disponibilità di una variabile (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
ms.openlocfilehash: 4d5db7fe474d8732e0ae37f3d95d0187eef68ec9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582488"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a>Procedura: Controllare la disponibilità di una variabile (Visual Basic)
È possibile controllare la disponibilità di una variabile specificando relativi *livello di accesso*. Il livello di accesso determina il tipo di codice dispone dell'autorizzazione per leggere o scrivere nella variabile.  
  
-   *Le variabili membro* (definito a livello di modulo e all'esterno di qualsiasi routine) predefinito per l'accesso pubblico, che significa che qualsiasi codice che possa visualizzarli può accedervi. È possibile modificare questo specificando un modificatore di accesso.  
  
-   *Le variabili locali* (definito all'interno di una routine) nominalmente hanno accesso pubblico, anche se solo il codice all'interno della routine può accedervi. Non è possibile modificare il livello di accesso di una variabile locale, ma è possibile modificare il livello di accesso della routine che lo contiene.  
  
 Per altre informazioni, vedere [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="private-and-public-access"></a>Accesso pubblico e privato  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a>Per rendere accessibile solo dall'interno il modulo, classe o struttura di una variabile  
  
1.  Sul posto di [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) per la variabile all'interno di modulo, classe o struttura, ma all'esterno di qualsiasi routine.  
  
2.  Includere il [privati](../../../../visual-basic/language-reference/modifiers/private.md) parola chiave nel `Dim` istruzione.  
  
     È possibile leggere o scrivere nella variabile da un punto qualsiasi all'interno di modulo, classe o struttura, ma non da al suo esterno.  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a>Per rendere accessibile da qualsiasi codice che è possibile visualizzarlo una variabile  
  
1.  Per una variabile membro, posizionare il `Dim` istruzione per la variabile all'interno di un modulo, classe o struttura, ma all'esterno di qualsiasi routine.  
  
2.  Includere il [pubbliche](../../../../visual-basic/language-reference/modifiers/public.md) parola chiave nel `Dim` istruzione.  
  
     È possibile leggere o scrivere nella variabile da qualsiasi codice che interagisce con l'assembly.  
  
 -oppure-  
  
1.  Per una variabile locale, posizionare il `Dim` istruzione per la variabile all'interno di una routine.  
  
2.  Non includere il `Public` parola chiave nel `Dim` istruzione.  
  
     È possibile leggere o scrivere nella variabile da un punto qualsiasi all'interno della routine, ma non da al suo esterno.  
  
## <a name="protected-and-friend-access"></a>Protetto e l'accesso Friend  
 È possibile limitare il livello di accesso di una variabile alla relativa classe e tutte le classi derivate o al relativo assembly. È anche possibile specificare l'unione di queste limitazioni, che consente l'accesso dal codice in qualsiasi classe derivata oppure in qualsiasi altro punto nello stesso assembly. A questo scopo è necessario combinare le `Protected` e `Friend` parole chiave nella stessa dichiarazione.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a>Per rendere accessibile solo dall'interno la relativa classe e tutte le classi derivate di una variabile  
  
1.  Posizione di `Dim` istruzione per la variabile all'interno di una classe, ma all'esterno di qualsiasi routine.  
  
2.  Includere il [protetti](../../../../visual-basic/language-reference/modifiers/protected.md) parola chiave nel `Dim` istruzione.  
  
     È possibile leggere o scrivere nella variabile da un punto qualsiasi all'interno della classe, oltre che dall'interno tutte le classi derivate da quest'ultimo, ma non all'esterno di qualsiasi classe nella catena di derivazione.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a>Per rendere accessibile solo da nello stesso assembly in una variabile  
  
1.  Posizione di `Dim` istruzione per la variabile all'interno di un modulo, classe o struttura, ma all'esterno di qualsiasi routine.  
  
2.  Includere il [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) parola chiave nel `Dim` istruzione.  
  
     È possibile leggere o scrivere nella variabile da un punto qualsiasi all'interno di modulo, classe o struttura, nonché da qualsiasi codice nello stesso assembly, ma non all'esterno dell'assembly.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra le dichiarazioni delle variabili con `Public`, `Protected`, `Friend`, `Protected Friend`, e `Private` livelli di accesso. Si noti che quando la `Dim` istruzione specifica un livello di accesso, non è necessario includere il `Dim` (parola chiave).  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Il più restrittivo del livello di accesso di una variabile, usare minori saranno le probabilità che codice dannoso può rendere non corretta di esso.  
  
## <a name="see-also"></a>Vedere anche
- [Livelli di accesso in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Public](../../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../../visual-basic/language-reference/modifiers/private.md)

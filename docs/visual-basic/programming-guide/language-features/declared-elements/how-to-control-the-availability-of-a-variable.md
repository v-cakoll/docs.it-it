---
title: 'Procedura: controllare la disponibilità di una variabile (Visual Basic)'
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
ms.openlocfilehash: 27ee5d3405ea24c0754cffa85e9b89b2ac561e42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652168"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a>Procedura: controllare la disponibilità di una variabile (Visual Basic)
È possibile controllare la disponibilità di una variabile specificando il relativo *livello di accesso*. Il livello di accesso determina il codice dispone dell'autorizzazione di lettura o scrittura per la variabile.  
  
-   *Variabili membro* (definito a livello di modulo e all'esterno di qualsiasi routine) predefinito per l'accesso pubblico, che significa che qualsiasi codice che possano essere visualizzate può accedervi. È possibile modificare questo specificando un modificatore di accesso.  
  
-   *Le variabili locali* (definito all'interno di una stored procedure) nominalmente avere accesso pubblico, sebbene sia possibile accedervi solo codice all'interno della routine. Non è possibile modificare il livello di accesso di una variabile locale, ma è possibile modificare il livello di accesso della routine che lo contiene.  
  
 Per ulteriori informazioni, vedere [accedere livelli in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="private-and-public-access"></a>Accesso pubblico e privato  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a>Per rendere accessibile solo dall'interno il modulo, classe o struttura di una variabile  
  
1.  Sul posto di [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md) per la variabile all'interno di modulo, classe o struttura, ma all'esterno di qualsiasi routine.  
  
2.  Includere il [privata](../../../../visual-basic/language-reference/modifiers/private.md) parola chiave nel `Dim` istruzione.  
  
     È possibile leggere o scrivere alla variabile da un punto qualsiasi all'interno di modulo, classe o struttura, ma non dall'esterno.  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a>Per rendere accessibile da qualsiasi codice che può essere visualizzato una variabile  
  
1.  Per una variabile membro, inserire il `Dim` istruzione per la variabile all'interno di un modulo, classe o struttura, ma all'esterno di qualsiasi routine.  
  
2.  Includere il [pubblica](../../../../visual-basic/language-reference/modifiers/public.md) parola chiave nel `Dim` istruzione.  
  
     È possibile leggere o scrivere nella variabile da qualsiasi codice che interagisce con l'assembly.  
  
 oppure  
  
1.  Per una variabile locale, inserire il `Dim` istruzione per la variabile all'interno di una stored procedure.  
  
2.  Non includere il `Public` parola chiave nel `Dim` istruzione.  
  
     È possibile leggere o scrivere alla variabile da un punto qualsiasi all'interno della routine, ma non dall'esterno.  
  
## <a name="protected-and-friend-access"></a>Protetto e l'accesso Friend  
 È possibile limitare il livello di accesso di una variabile di classe e tutte le classi derivate, o al relativo assembly. È inoltre possibile specificare l'unione di queste limitazioni, che consente l'accesso dal codice in qualsiasi classe derivata o in qualsiasi altra posizione nello stesso assembly. A questo scopo è necessario combinare il `Protected` e `Friend` parole chiave nella stessa dichiarazione.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a>Per rendere accessibile solo dall'interno di classe e tutte le classi derivate di una variabile  
  
1.  Sul posto di `Dim` istruzione per la variabile all'interno di una classe, ma all'esterno di qualsiasi routine.  
  
2.  Includere il [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) parola chiave nel `Dim` istruzione.  
  
     Consente di leggere o scrivere alla variabile da un punto qualsiasi all'interno della classe, nonché dall'interno di qualsiasi classe derivata da esso, ma non dall'esterno di qualsiasi classe nella catena di derivazione.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a>Per rendere accessibile solo dall'interno dello stesso assembly di una variabile  
  
1.  Sul posto di `Dim` istruzione per la variabile all'interno di un modulo, classe o struttura, ma all'esterno di qualsiasi routine.  
  
2.  Includere il [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) parola chiave nel `Dim` istruzione.  
  
     È possibile leggere o scrivere alla variabile da un punto qualsiasi all'interno di modulo, classe o struttura, nonché da qualsiasi codice nello stesso assembly, ma non dall'esterno dell'assembly.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra le dichiarazioni di variabili con `Public`, `Protected`, `Friend`, `Protected Friend`, e `Private` livelli di accesso. Si noti che quando il `Dim` istruzione specifica un livello di accesso, non è necessario includere il `Dim` (parola chiave).  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Più restrittivo il livello di accesso di una variabile, minori saranno le probabilità di codice dannoso può rendere non corretto utilizzano di esso.  
  
## <a name="see-also"></a>Vedere anche  
 [Livelli di accesso in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Public](../../../../visual-basic/language-reference/modifiers/public.md)  
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [Private](../../../../visual-basic/language-reference/modifiers/private.md)

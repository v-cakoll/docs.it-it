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
ms.openlocfilehash: 84aaeecdbd3cc8ab12589c0342b982bf3f1c8529
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582623"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a>Procedura: controllare la disponibilità di una variabile (Visual Basic)
Per controllare la disponibilità di una variabile, è necessario specificarne il *livello di accesso*. Il livello di accesso determina quale codice dispone dell'autorizzazione per la lettura o la scrittura nella variabile.  
  
- Per impostazione predefinita, le *variabili membro* (definite a livello di modulo e all'esterno di qualsiasi routine) per l'accesso pubblico, ovvero qualsiasi codice in grado di visualizzarle possono accedervi. È possibile modificare questa impostazione specificando un modificatore di accesso.  
  
- Le *variabili locali* (definite all'interno di una routine) hanno nominalmente accesso pubblico, anche se solo il codice all'interno della procedura può accedervi. Non è possibile modificare il livello di accesso di una variabile locale, ma è possibile modificare il livello di accesso della routine che la contiene.  
  
 Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="private-and-public-access"></a>Accesso privato e pubblico  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a>Per rendere una variabile accessibile solo dall'interno del modulo, della classe o della struttura  
  
1. Inserire l' [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) per la variabile all'interno del modulo, della classe o della struttura, ma all'esterno di qualsiasi routine.  
  
2. Includere la parola chiave [private](../../../../visual-basic/language-reference/modifiers/private.md) nell'istruzione `Dim`.  
  
     È possibile leggere o scrivere nella variabile da qualsiasi punto all'interno del modulo, della classe o della struttura, ma non dall'esterno.  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a>Per rendere una variabile accessibile da qualsiasi codice in grado di visualizzarlo  
  
1. Per una variabile membro, inserire l'istruzione `Dim` per la variabile all'interno di un modulo, una classe o una struttura, ma all'esterno di qualsiasi routine.  
  
2. Includere la parola chiave [public](../../../../visual-basic/language-reference/modifiers/public.md) nell'istruzione `Dim`.  
  
     È possibile leggere o scrivere nella variabile da qualsiasi codice che interagisce con l'assembly.  
  
 oppure  
  
1. Per una variabile locale, inserire l'istruzione `Dim` per la variabile all'interno di una routine.  
  
2. Non includere la parola chiave `Public` nell'istruzione `Dim`.  
  
     È possibile leggere o scrivere nella variabile da qualsiasi punto all'interno della procedura, ma non dall'esterno.  
  
## <a name="protected-and-friend-access"></a>Accesso protetto e Friend  
 È possibile limitare il livello di accesso di una variabile alla relativa classe ed eventuali classi derivate o al relativo assembly. È anche possibile specificare l'Unione di queste limitazioni, che consente l'accesso dal codice in qualsiasi classe derivata o in un'altra posizione nello stesso assembly. È possibile specificare questa Unione combinando le parole chiave `Protected` e `Friend` nella stessa dichiarazione.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a>Per rendere una variabile accessibile solo dall'interno della relativa classe e delle classi derivate  
  
1. Inserire l'istruzione `Dim` per la variabile all'interno di una classe, ma all'esterno di qualsiasi routine.  
  
2. Includere la parola chiave [protected](../../../../visual-basic/language-reference/modifiers/protected.md) nell'istruzione `Dim`.  
  
     È possibile leggere o scrivere nella variabile da qualsiasi punto all'interno della classe, nonché da qualsiasi classe derivata, ma non dall'esterno di alcuna classe nella catena di derivazione.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a>Per rendere una variabile accessibile solo dall'interno dello stesso assembly  
  
1. Inserire l'istruzione `Dim` per la variabile all'interno di un modulo, una classe o una struttura, ma all'esterno di qualsiasi routine.  
  
2. Includere la parola chiave [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) nell'istruzione `Dim`.  
  
     È possibile leggere o scrivere nella variabile da qualsiasi punto all'interno del modulo, della classe o della struttura, nonché da qualsiasi codice nello stesso assembly, ma non dall'esterno dell'assembly.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono illustrate le dichiarazioni di variabili con i livelli di accesso `Public`, `Protected`, `Friend`, `Protected Friend` e `Private`. Si noti che quando l'istruzione `Dim` specifica un livello di accesso, non è necessario includere la parola chiave `Dim`.  
  
```vb  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Più restrittivo è il livello di accesso di una variabile, minore sarà la probabilità che il codice dannoso possa utilizzarlo in modo non corretto.  
  
## <a name="see-also"></a>Vedere anche

- [Livelli di accesso in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Public](../../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../../visual-basic/language-reference/modifiers/private.md)

---
title: "Procedura: controllare l'ambito di una variabile"
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: 8b21f22edea84448e3f2969c3e4b07c08a17a338
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357348"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a>Procedura: controllare l'ambito di una variabile (Visual Basic)
In genere, una variabile è nell' *ambito*o visibile per riferimento, in tutta l'area in cui viene dichiarata. In alcuni casi, il livello di *accesso* della variabile può influenzare il proprio ambito.  
  
 Per altre informazioni, vedere [Scope in Visual Basic](scope.md).  
  
## <a name="scope-at-block-or-procedure-level"></a>Ambito a livello di blocco o di procedura  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a>Per rendere una variabile visibile solo all'interno di un blocco  
  
- Inserire l' [istruzione Dim](../../../language-reference/statements/dim-statement.md) per la variabile tra le istruzioni di inizializzazione e terminazione del blocco, ad esempio tra le `For` istruzioni e `Next` di un `For` ciclo.  
  
     È possibile fare riferimento alla variabile solo dall'interno del blocco.  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a>Per rendere una variabile visibile solo all'interno di una routine  
  
- Inserire l' `Dim` istruzione per la variabile all'interno della routine, ma all'esterno di qualsiasi blocco (ad esempio un `With` blocco... `End With` ).  
  
     È possibile fare riferimento alla variabile solo dalla procedura, incluso all'interno di qualsiasi blocco contenuto nella procedura.  
  
## <a name="scope-at-module-or-namespace-level"></a>Ambito a livello di modulo o di spazio dei nomi  
 Per praticità, il *livello del modulo* a singolo termine si applica ugualmente a moduli, classi e strutture. Il livello di accesso di una variabile a livello di modulo ne determina l'ambito. Lo spazio dei nomi che contiene il modulo, la classe o la struttura influenza anche l'ambito.  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a>Per rendere visibile una variabile in un modulo, una classe o una struttura  
  
1. Inserire l' `Dim` istruzione per la variabile all'interno del modulo, della classe o della struttura, ma all'esterno di qualsiasi routine.  
  
2. Includere la parola chiave [private](../../../language-reference/modifiers/private.md) nell' `Dim` istruzione.  
  
3. È possibile fare riferimento alla variabile da qualsiasi punto all'interno del modulo, della classe o della struttura, ma non dall'esterno.  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a>Per rendere visibile una variabile in uno spazio dei nomi  
  
1. Inserire l' `Dim` istruzione per la variabile all'interno del modulo, della classe o della struttura, ma all'esterno di qualsiasi routine.  
  
2. Includere la parola chiave [Friend](../../../language-reference/modifiers/friend.md) o [public](../../../language-reference/modifiers/public.md) nell' `Dim` istruzione.  
  
3. È possibile fare riferimento alla variabile da qualsiasi punto all'interno dello spazio dei nomi che contiene il modulo, la classe o la struttura.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene dichiarata una variabile a livello di modulo e la relativa visibilità viene limitata al codice all'interno del modulo.  
  
```vb  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 Nell'esempio precedente, tutte le procedure definite in module `demonstrateScope` possono fare riferimento alla `String` variabile `strMsg` . Quando `usePrivateVariable` viene chiamata la stored procedure, viene visualizzato il contenuto della variabile stringa `strMsg` in una finestra di dialogo.  
  
 Con la seguente modifica all'esempio precedente, `strMsg` è possibile fare riferimento alla variabile di stringa dal codice in qualsiasi punto dello spazio dei nomi della relativa dichiarazione.  
  
```vb  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Più ristretto è l'ambito di una variabile, minore è il numero di opportunità disponibili per farvi riferimento accidentalmente al posto di un'altra variabile con lo stesso nome. È anche possibile ridurre al minimo i problemi di corrispondenza dei riferimenti.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Più ristretto è l'ambito di una variabile, minore è la probabilità che il codice dannoso possa utilizzarlo in modo non corretto.  
  
## <a name="see-also"></a>Vedere anche

- [Ambito in Visual Basic](scope.md)
- [Durata in Visual Basic](lifetime.md)
- [Livelli di accesso in Visual Basic](access-levels.md)
- [Variabili](../variables/index.md)
- [Dichiarazione di variabile](../variables/variable-declaration.md)
- [Istruzione Dim](../../../language-reference/statements/dim-statement.md)

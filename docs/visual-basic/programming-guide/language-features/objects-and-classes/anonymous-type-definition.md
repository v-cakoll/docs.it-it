---
title: Definizione di tipo anonimo (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 179fb9773fde2631666498d54894037b2bbfd087
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="anonymous-type-definition-visual-basic"></a>Definizione di tipo anonimo (Visual Basic)
In risposta alla dichiarazione di un'istanza di un tipo anonimo, il compilatore crea una nuova definizione di classe che contiene le proprietà per il tipo specificate.  
  
## <a name="compiler-generated-code"></a>Codice generato dal compilatore  
 Per la seguente definizione di `product`, il compilatore crea una nuova definizione di classe contenente proprietà `Name`, `Price`, e `OnHand`.  
  
 [!code-vb[VbVbalrAnonymousTypes#25](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_1.vb)]  
  
 La definizione della classe contiene le definizioni di proprietà simile al seguente. Si noti che non vi è alcun `Set` metodo per la proprietà chiave. I valori delle proprietà chiave sono di sola lettura.  
  
```vb  
Public Class $Anonymous1  
    Private _name As String  
    Private _price As Double  
    Private _onHand As Integer  
     Public ReadOnly Property Name() As String  
        Get  
            Return _name  
        End Get  
    End Property  
  
    Public ReadOnly Property Price() As Double  
        Get  
            Return _price  
        End Get  
    End Property  
  
    Public Property OnHand() As Integer  
        Get  
            Return _onHand  
        End Get  
        Set(ByVal Value As Integer)  
            _onHand = Value  
        End Set  
    End Property  
  
End Class  
```  
  
 Inoltre, le definizioni di tipo anonimo contengono un costruttore predefinito. Non sono consentiti costruttori che richiedono parametri.  
  
 Se una dichiarazione di tipo anonimo contiene almeno una proprietà chiave, la definizione del tipo esegue l'override di tre membri ereditati da <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, e <xref:System.Object.ToString%2A>. Se viene dichiarata alcuna proprietà chiave, solo <xref:System.Object.ToString%2A> viene sottoposto a override. Le sostituzioni forniscono le funzionalità seguenti:  
  
-   `Equals` Restituisce `True` se due istanze di tipo anonimo sono la stessa istanza o se soddisfano le condizioni seguenti:  
  
    -   Hanno lo stesso numero di proprietà.  
  
    -   Le proprietà vengono dichiarate nello stesso ordine, con gli stessi nomi e gli stessi tipi dedotti. Confronti tra nomi non è rilevanti.  
  
    -   Almeno una delle proprietà è una proprietà chiave e `Key` (parola chiave) viene applicato alle stesse proprietà.  
  
    -   Confronto tra ogni coppia corrispondente di proprietà chiave restituisce `True`.  
  
     Ad esempio, negli esempi seguenti, `Equals` restituisce `True` solo per `employee01` e `employee08`. Il commento prima di ogni riga specifica il motivo per cui corrisponde la nuova istanza `employee01`.  
  
     [!code-vb[VbVbalrAnonymousTypes#24](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_2.vb)]  
  
-   `GetHashcode` fornisce un algoritmo di GetHashCode adeguatamente univoco. L'algoritmo utilizza solo le proprietà chiave per calcolare il codice hash.  
  
-   `ToString` Restituisce una stringa concatenata dei valori delle proprietà, come illustrato nell'esempio seguente. Chiave e le proprietà non chiave sono inclusione.  
  
     [!code-vb[VbVbalrAnonymousTypes#29](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_3.vb)]  
  
 Proprietà denominate in modo esplicito di un tipo anonimo non è in conflitto con questi metodi generati. Ovvero, non è possibile utilizzare `.Equals`, `.GetHashCode`, o `.ToString` per assegnare un nome di una proprietà.  
  
 Definizioni di tipo anonimo che comprendono almeno una proprietà chiave implementano anche il <xref:System.IEquatable%601?displayProperty=nameWithType> interfaccia, in cui `T` è il tipo del tipo anonimo.  
  
> [!NOTE]
>  Dichiarazioni di tipo anonimo creare lo stesso tipo anonimo solo se si verificano nello stesso assembly, le relative proprietà hanno gli stessi nomi e gli stessi tipi dedotti, nello stesso ordine in cui sono dichiarate le proprietà e le stesse proprietà sono contrassegnate come proprietà chiave.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Procedura: Dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)

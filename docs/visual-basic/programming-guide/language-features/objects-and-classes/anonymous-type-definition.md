---
title: Definizione di tipo anonimo (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 832d56f5c51aea87185f36ec306c3fec036a40e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780848"
---
# <a name="anonymous-type-definition-visual-basic"></a>Definizione di tipo anonimo (Visual Basic)

In risposta alla dichiarazione di un'istanza di un tipo anonimo, il compilatore crea una nuova definizione di classe che contiene le proprietà specificate per il tipo.

## <a name="compiler-generated-code"></a>Codice generato dal compilatore

Per la seguente definizione di `product`, il compilatore crea una nuova definizione di classe che contiene le proprietà `Name`, `Price`, e `OnHand`.

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

La definizione della classe contiene le definizioni delle proprietà simile al seguente. Si noti che non vi è alcun `Set` metodo per la proprietà chiave. I valori delle proprietà di chiave sono di sola lettura.

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

Inoltre, le definizioni di tipo anonimo contengono un costruttore predefinito. I costruttori che richiedono parametri non sono consentiti.

Se una dichiarazione di tipo anonimo contiene almeno una proprietà chiave, la definizione del tipo esegue l'override di tre membri ereditati da <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, e <xref:System.Object.ToString%2A>. Se nessuna proprietà chiave viene dichiarata, solo <xref:System.Object.ToString%2A> viene sottoposto a override. Le sostituzioni offrono le funzionalità seguenti:

- `Equals` Restituisce `True` se due istanze di tipo anonimo sono la stessa istanza o se soddisfano le condizioni seguenti:

  - Hanno lo stesso numero di proprietà.

  - Le proprietà vengono dichiarate nello stesso ordine, con gli stessi nomi e gli stessi tipi dedotti. I confronti tra nomi non sono tra maiuscole e minuscole.

  - Almeno una delle proprietà è una proprietà chiave e il `Key` viene applicata la parola chiave per le stesse proprietà.

  - Confronto tra ogni coppia corrispondente di proprietà di chiave restituisce `True`.

    Ad esempio, negli esempi seguenti `Equals` restituisce `True` solo per `employee01` e `employee08`. Il commento prima di ogni riga specifica il motivo per cui la nuova istanza non corrisponde `employee01`.

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- `GetHashcode` fornisce un algoritmo GetHashCode univoco in modo appropriato. L'algoritmo Usa solo le proprietà della chiave per calcolare il codice hash.

- `ToString` Restituisce una stringa concatenata dei valori delle proprietà, come illustrato nell'esempio seguente. Sono incluse sia chiave e le proprietà non chiave.

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

Proprietà denominate in modo esplicito di un tipo anonimo non è in conflitto con questi metodi generati. Vale a dire, non è possibile usare `.Equals`, `.GetHashCode`, o `.ToString` per assegnare un nome di una proprietà.

Le definizioni di tipo anonimo che include almeno una proprietà chiave implementano anche il <xref:System.IEquatable%601?displayProperty=nameWithType> interfaccia, in cui `T` è il tipo del tipo anonimo.

> [!NOTE]
> Dichiarazioni di tipo anonimo creare lo stesso tipo anonimo solo se si verificano nello stesso assembly, le relative proprietà hanno gli stessi nomi e gli stessi tipi dedotti, nello stesso ordine in cui sono dichiarate le proprietà e le stesse proprietà vengono contrassegnate come proprietà chiave.

## <a name="see-also"></a>Vedere anche

- [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Procedura: Dedurre i nomi delle proprietà e i tipi nelle dichiarazioni di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)

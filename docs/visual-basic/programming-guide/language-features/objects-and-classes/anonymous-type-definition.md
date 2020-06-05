---
title: Definizione di tipo anonimo
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 952eb295cc71eab5d0ad6e18f2b697a9b701b434
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404901"
---
# <a name="anonymous-type-definition-visual-basic"></a>Definizione di tipo anonimo (Visual Basic)

In risposta alla dichiarazione di un'istanza di un tipo anonimo, il compilatore crea una nuova definizione di classe che contiene le proprietà specificate per il tipo.

## <a name="compiler-generated-code"></a>Codice generato dal compilatore

Per la definizione seguente di `product` , il compilatore crea una nuova definizione di classe che contiene le proprietà `Name` , `Price` e `OnHand` .

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

La definizione della classe contiene definizioni di proprietà simili a quelle riportate di seguito. Si noti che non esiste alcun `Set` metodo per le proprietà chiave. I valori delle proprietà chiave sono di sola lettura.

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

Inoltre, le definizioni di tipo anonimo contengono un costruttore senza parametri. I costruttori che richiedono parametri non sono consentiti.

Se una dichiarazione di tipo anonimo contiene almeno una proprietà chiave, la definizione del tipo esegue l'override di tre membri ereditati da <xref:System.Object> : <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> e <xref:System.Object.ToString%2A> . Se non viene dichiarata alcuna proprietà chiave, <xref:System.Object.ToString%2A> viene eseguito l'override di. Le sostituzioni forniscono le funzionalità seguenti:

- `Equals`restituisce `True` se due istanze di tipo anonimo sono la stessa istanza o se soddisfano le condizioni seguenti:

  - Hanno lo stesso numero di proprietà.

  - Le proprietà vengono dichiarate nello stesso ordine, con gli stessi nomi e gli stessi tipi dedotti. I confronti tra nomi non fanno distinzione tra maiuscole e minuscole.

  - Almeno una delle proprietà è una proprietà chiave e la `Key` parola chiave viene applicata alle stesse proprietà.

  - Il confronto di ogni coppia corrispondente di proprietà chiave restituisce `True` .

    Negli esempi seguenti, ad esempio, `Equals` restituisce `True` solo per `employee01` e `employee08` . Il commento prima di ogni riga specifica il motivo per cui la nuova istanza non corrisponde `employee01` .

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- `GetHashcode`fornisce un algoritmo GetHashCode univoco in modo appropriato. L'algoritmo usa solo le proprietà chiave per calcolare il codice hash.

- `ToString`Restituisce una stringa di valori di proprietà concatenati, come illustrato nell'esempio seguente. Sono incluse entrambe le proprietà chiave e non chiave.

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

Le proprietà denominate in modo esplicito di un tipo anonimo non possono essere in conflitto con questi metodi generati. Ovvero, non è possibile utilizzare `.Equals` , `.GetHashCode` o `.ToString` per assegnare un nome a una proprietà.

Anche le definizioni di tipo anonimo che includono almeno una proprietà chiave implementano l' <xref:System.IEquatable%601?displayProperty=nameWithType> interfaccia, dove `T` è il tipo del tipo anonimo.

> [!NOTE]
> Le dichiarazioni di tipo anonimo creano lo stesso tipo anonimo solo se si trovano nello stesso assembly, le relative proprietà hanno gli stessi nomi e gli stessi tipi inferiti, le proprietà vengono dichiarate nello stesso ordine e le stesse proprietà sono contrassegnate come proprietà chiave.

## <a name="see-also"></a>Vedere anche

- [Tipi anonimi](anonymous-types.md)
- [Procedura: dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)

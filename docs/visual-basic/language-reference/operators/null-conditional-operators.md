---
title: Operatori condizionali null (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: b83435b8448b53eca63aac0519e9eed2f7dfa9f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62028691"
---
# <a name="-and--null-conditional-operators-visual-basic"></a>?. e? operatori condizionali null () (Visual Basic)

Testa il valore dell'operando a sinistra i valori null (`Nothing`) prima di eseguire un accesso ai membri (`?.`) o un indice (`?()`) operazione; restituisce `Nothing` se l'operando sinistro `Nothing`. Si noti che nelle espressioni che restituiscono in genere i tipi di valore, l'operatore condizionale null restituisce un <xref:System.Nullable%601>.

Questi operatori consentono di scrivere meno codice per gestire i controlli null, in particolare quando decrescente in strutture di dati. Ad esempio:

```vb
' Nothing if customers is Nothing  
Dim length As Integer? = customers?.Length  

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()   
```

Per il confronto, il codice alternativo per il primo di tali espressioni senza un operatore condizionale null è:

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

Gli operatori condizionali Null causano corto circuiti.  Se un'operazione in una catena di operazioni di indice e accesso ai membri condizionali restituisce `Nothing`, il resto del viene arrestata l'esecuzione della catena.  Nell'esempio riportato di seguito `C(E)` non viene valutato se `A`, `B`, o `C` restituisce `Nothing`.

```vb
A?.B?.C?(E);
```

Un altro uso per l'accesso ai membri condizionali null è richiamare delegati in modo thread-safe scrivendo molto meno codice.  L'esempio seguente definisce due tipi, una `NewsBroadcaster` e un `NewsReceiver`. Nuovi elementi vengono inviati al ricevitore per il `NewsBroadcaster.SendNews` delegare.

```vb
Public Module NewsBroadcaster
   Dim SendNews As Action(Of String) 

   Public Sub Main()
      Dim rec As New NewsReceiver()
      Dim rec2 As New NewsReceiver()
      SendNews?.Invoke("Just in: A newsworthy item...")
   End Sub

   Public Sub Register(client As Action(Of String))
      SendNews = SendNews.Combine({SendNews, client})
   End Sub
End Module

Public Class NewsReceiver
   Public Sub New()
      NewsBroadcaster.Register(AddressOf Me.DisplayNews)
   End Sub

   Public Sub DisplayNews(newsItem As String)
      Console.WriteLine(newsItem)
   End Sub
End Class
```

Se non esistono elementi nel `SendNews` elenco di chiamate, il `SendNews` delegare genera un <xref:System.NullReferenceException>. Prima di operatori condizionali null, di codice come il seguente garantito che l'elenco di chiamate del delegato non è stato `Nothing`:

```vb  
SendNews = SendNews.Combine({SendNews, client})  
If SendNews IsNot Nothing Then 
   SendNews("Just in...")
End If
```

Ora tutto è molto più semplice:  

```vb
SendNews = SendNews.Combine({SendNews, client})  
SendNews?.Invoke("Just in...")
```

Il codice creato in questo modo è thread-safe perché il compilatore genera il codice per valutare `SendNews` una sola volta, mantenendo il risultato in una variabile temporanea. È necessario chiamare esplicitamente il metodo `Invoke` perché non esiste una sintassi di chiamata dei delegati con condizione Null `SendNews?(String)`.  

## <a name="see-also"></a>Vedere anche

- [Operatori (Visual Basic)](index.md)
- [Guida per programmatori Visual Basic](../../../visual-basic/programming-guide/index.md)
- [Riferimenti per il linguaggio Visual Basic](../../../visual-basic/language-reference/index.md)

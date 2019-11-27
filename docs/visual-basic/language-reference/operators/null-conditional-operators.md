---
title: Operatori condizionali null
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 003f579a7128bbe2462b7fbe7057de03e61bfbe6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348292"
---
# <a name="-and--null-conditional-operators-visual-basic"></a>?. e? () operatori condizionali null (Visual Basic)

Verifica il valore dell'operando sinistro per null (`Nothing`) prima di eseguire un'operazione di accesso ai membri (`?.`) o di indice (`?()`). Restituisce `Nothing` se l'operando sinistro restituisce `Nothing`. Si noti che nelle espressioni che in genere restituiscono tipi di valore, l'operatore condizionale null restituisce un <xref:System.Nullable%601>.

Questi operatori consentono di scrivere meno codice per gestire i controlli null, soprattutto in caso di decrescente in strutture di dati. Di seguito è riportato un esempio:

```vb
' Nothing if customers is Nothing
Dim length As Integer? = customers?.Length

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()
```

Per il confronto, il codice alternativo per la prima di queste espressioni senza un operatore condizionale null è:

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

In alcuni casi è necessario eseguire un'azione su un oggetto che può essere null, in base al valore di un membro booleano sull'oggetto, ad esempio la proprietà booleana `IsAllowedFreeShipping` nell'esempio seguente:

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
  ApplyFreeShippingToOrders(customer)
End If
```

È possibile abbreviare il codice ed evitare di verificare manualmente la presenza di valori null usando l'operatore condizionale null come indicato di seguito:

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

Gli operatori condizionali Null causano corto circuiti.  Se un'operazione in una catena di operazioni di accesso ai membri condizionali e di indice restituisce `Nothing`, il resto dell'esecuzione della catena viene arrestato.  Nell'esempio seguente `C(E)` non viene valutato se `A`, `B`o `C` restituisce `Nothing`.

```vb
A?.B?.C?(E)
```

Un altro utilizzo per l'accesso ai membri condizionali null consiste nel richiamare i delegati in modo thread-safe con molto meno codice.  Nell'esempio seguente vengono definiti due tipi, una `NewsBroadcaster` e una `NewsReceiver`. Gli elementi di notizie vengono inviati al destinatario dal delegato `NewsBroadcaster.SendNews`.

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

Se non sono presenti elementi nell'elenco chiamate `SendNews`, il delegato `SendNews` genera un'<xref:System.NullReferenceException>. Prima degli operatori condizionali null, il codice simile al seguente verifica che l'elenco chiamate del delegato non sia stato `Nothing`:

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

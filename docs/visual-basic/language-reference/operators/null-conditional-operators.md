---
title: Operatori condizionali null (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: c29362a1e335e18b66821919e266b1ce57774692
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50195992"
---
# <a name="-and--null-conditional-operators-visual-basic"></a>?. e? operatori condizionali null () (Visual Basic)

Testa il valore dell'operando a sinistra i valori null (`Nothing`) prima di eseguire un accesso ai membri (`?.`) o un indice (`?()`) operazione; restituisce `Nothing` se l'operando sinistro `Nothing`. Si noti che, nelle espressioni di che normalmente restituisce i tipi di valore, l'operatore condizionale null restituisce un <xref:System.Nullable%601>.

Questi operatori consentono di scrivere meno codice per gestire i controlli null, in particolare quando decrescente in strutture di dati. Ad esempio:

```vb
Dim length As Integer? = customers?.Length  ' Nothing if customers is Nothing  
Dim first As Customer = customers?(0)  ' Nothing if customers is Nothing  
Dim count As Integer? = customers?(0)?.Orders?.Count()  ' Nothing if customers, the first customer, or Orders is Nothing  
```

Per il confronto, il codice alternativo per il primo di tali espressioni senza un operatore condizionale null è:

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

Gli operatori condizionali Null causano corto circuiti.  Se un'operazione in una catena di operazioni di indice e accesso ai membri condizionali non restituisce nulla, il resto dell'esecuzione della catena verrà interrotta.  Nell'esempio seguente, non viene valutato c (e) se `A`, `B`, o `C` non restituisce alcun valore.

```vb
A?.B?.C?(E);
```

Un altro uso per l'accesso ai membri condizionali null è richiamare delegati in modo thread-safe scrivendo molto meno codice.  In passato era necessario codice simile al seguente:  

```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```

Ora tutto è molto più semplice:  

```vb
PropertyChanged?.Invoke(…)
```

Il codice creato in questo modo è thread-safe perché il compilatore genera il codice per valutare `PropertyChanged` una sola volta, mantenendo il risultato in una variabile temporanea. È necessario chiamare esplicitamente il metodo `Invoke` perché non esiste una sintassi di chiamata dei delegati con condizione Null `PropertyChanged?(e)`.  

## <a name="see-also"></a>Vedere anche

- [Operatori (Visual Basic)](index.md)
- [Guida per programmatori Visual Basic](../../../visual-basic/programming-guide/index.md)
- [Riferimenti per il linguaggio Visual Basic](../../../visual-basic/language-reference/index.md)  

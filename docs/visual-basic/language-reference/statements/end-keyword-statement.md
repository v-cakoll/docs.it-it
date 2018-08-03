---
title: Estremità &lt;parola chiave&gt; istruzione (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 8137434bfd8c26144d78b1761b784cdba4894eaf
ms.sourcegitcommit: 7fe772c6c05a982153655d618c826e9839d39cac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/03/2018
ms.locfileid: "33605264"
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a>Estremità &lt;parola chiave&gt; istruzione (Visual Basic)

Quando è seguito da una parola chiave aggiuntiva, termina la definizione del blocco di istruzione introdotta dalla parola chiave.

## <a name="syntax"></a>Sintassi

```vb
End AddHandler
End Class
End Enum
End Event
End Function
End Get
End If
End Interface
End Module
End Namespace
End Operator
End Property
End RaiseEvent  
End RemoveHandler  
End Select
End Set
End Structure
End Sub
End SyncLock
End Try
End While
End With  
```  
  
## <a name="parts"></a>Parti

|Parte|Descrizione|
|---|---|
|`End`|Obbligatorio. Termina la definizione dell'elemento di programmazione.|
|`AddHandler`|Necessario per terminare un' `AddHandler` funzione di accesso iniziato da un oggetto corrispondente `AddHandler` istruzione in un oggetto personalizzato [istruzione Event](event-statement.md).|
|`Class`|Necessario per terminare una definizione di classe iniziata da un oggetto corrispondente [istruzione Class](class-statement.md).|
|`Enum`|Necessario per terminare una definizione di enumerazione iniziata da un oggetto corrispondente [istruzione Enum](enum-statement.md).|
|`Event`|Necessario per terminare una `Custom` definizione di evento avviato da un oggetto corrispondente [istruzione Event](event-statement.md).|  
|`Function`|Necessario per terminare una `Function` definizione della stored procedure iniziato da un oggetto corrispondente [istruzione Function](function-statement.md). Se l'esecuzione rileva un `End Function` istruzione, restituisce il controllo al codice chiama.|
|`Get`|Necessario per terminare una `Property` definizione della stored procedure iniziato da un oggetto corrispondente [Get Statement](get-statement.md). Se l'esecuzione rileva un `End Get` istruzione, controllo viene restituito all'istruzione che richiede il valore della proprietà.|
|`If`|Necessario per terminare un `If`... `Then`... `Else` iniziata da un oggetto corrispondente `If` istruzione. Vedere [se... Quindi... Istruzione else](if-then-else-statement.md).|
|`Interface`|Necessario per terminare una definizione di interfaccia iniziata da un oggetto corrispondente [Interface (istruzione)](interface-statement.md).|
|`Module`|Necessario per terminare una definizione di modulo iniziata da un oggetto corrispondente [Module Statement](module-statement.md).|
|`Namespace`|Necessario per terminare una definizione dello spazio dei nomi iniziata da un oggetto corrispondente [istruzione Namespace](namespace-statement.md).|
|`Operator`|Necessario per terminare una definizione di operatore iniziata da un oggetto corrispondente [Operator Statement](operator-statement.md).|
|`Property`|Necessario per terminare una definizione di proprietà iniziata da un oggetto corrispondente [Property Statement](property-statement.md).|
|`RaiseEvent`|Necessario per terminare una `RaiseEvent` funzione di accesso iniziato da un oggetto corrispondente `RaiseEvent` istruzione in un oggetto personalizzato [istruzione Event](event-statement.md).|
|`RemoveHandler`|Necessario per terminare una `RemoveHandler` funzione di accesso iniziato da un oggetto corrispondente `RemoveHandler` istruzione in un oggetto personalizzato [istruzione Event](event-statement.md).|
|`Select`|Necessario per terminare un `Select`... `Case` iniziata da un oggetto corrispondente `Select` istruzione. Vedere [Seleziona... Istruzione case](select-case-statement.md).  
|`Set`|Necessario per terminare una `Property` definizione della stored procedure iniziato da un oggetto corrispondente [istruzione Set](set-statement.md). Se l'esecuzione rileva un `End Set` istruzione, controllo viene restituito all'istruzione che imposta il valore della proprietà.  
|`Structure`|Necessario per terminare una definizione di struttura iniziata da un oggetto corrispondente [istruzione Structure](structure-statement.md).  
|`Sub`|Necessario per terminare una `Sub` definizione della stored procedure iniziato da un oggetto corrispondente [istruzione Sub](sub-statement.md). Se l'esecuzione rileva un `End Sub` istruzione, restituisce il controllo al codice chiama.  
|`SyncLock`|Necessario per terminare una `SyncLock` iniziata da un oggetto corrispondente `SyncLock` istruzione. Visualizzare [istruzione SyncLock](synclock-statement.md).  
|`Try`|Necessario per terminare un `Try`... `Catch`... `Finally` iniziata da un oggetto corrispondente `Try` istruzione. Vedere [Try... Catch... Istruzione finally](try-catch-finally-statement.md).  
|`While`|Necessario per terminare una `While` iniziato da un oggetto corrispondente definizione del ciclo `While` istruzione. Vedere [mentre... End While (istruzione)](while-end-while-statement.md).  
|`With`| Necessario per terminare una `With` iniziata da un oggetto corrispondente `With` istruzione. Vedere [con... Terminare con istruzione](with-end-with-statement.md).  
|||
  
## <a name="directives"></a>Direttive

Quando è preceduta da un simbolo di cancelletto (`#`), il `End` (parola chiave) termina un blocco di pre-elaborazione introdotto dall'istruzione corrispondente.  

```vb
#End ExternalSource
#End If
#End Region
```

|Parte|Descrizione|
|---|---|
|`#End`|Obbligatorio. Termina la definizione del blocco di pre-elaborazione.|
|`ExternalSource`|Necessario per terminare un blocco di origine esterna iniziato da un oggetto corrispondente [#ExternalSource direttiva](../directives/externalsource-directive.md).|
|`If`|Necessario per terminare un blocco di compilazione condizionale iniziato da un oggetto corrispondente `#If` direttiva. Vedere [#If... Then... #Else direttive](../directives/if-then-else-directives.md).|
|`Region`|Necessario per terminare un blocco di area di origine iniziato da un oggetto corrispondente [#Region direttiva](../directives/region-directive.md).|
|||

## <a name="remarks"></a>Note

Il [istruzione End](end-statement.md), senza una parola chiave aggiuntiva, termina l'esecuzione immediatamente.

## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  

Il `End` alcuna parola chiave aggiuntiva, l'istruzione non è supportato.  
  
## <a name="see-also"></a>Vedere anche

[Istruzione End](end-statement.md)

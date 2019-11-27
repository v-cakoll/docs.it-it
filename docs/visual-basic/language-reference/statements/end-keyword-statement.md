---
title: Istruzione End <keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 87f4724cc036e6e0bdf0b558854a4034f45b9ab5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343743"
---
# <a name="end-keyword-statement-visual-basic"></a>End \<parola chiave > Statement (Visual Basic)

Quando seguito da una parola chiave aggiuntiva, termina la definizione del blocco di istruzioni introdotto da tale parola chiave.

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
|`End`|Obbligatoria. Termina la definizione dell'elemento di programmazione.|
|`AddHandler`|Obbligatorio per terminare una funzione di accesso `AddHandler` iniziata da un'istruzione `AddHandler` corrispondente in un' [istruzione di evento](event-statement.md)personalizzata.|
|`Class`|Obbligatorio per terminare una definizione di classe iniziata da un' [istruzione di classe](class-statement.md)corrispondente.|
|`Enum`|Obbligatorio per terminare una definizione di enumerazione iniziata da un' [istruzione enum](enum-statement.md)corrispondente.|
|`Event`|Obbligatorio per terminare una definizione di evento `Custom` iniziata da un' [istruzione di evento](event-statement.md)corrispondente.|  
|`Function`|Obbligatorio per terminare una definizione di routine `Function` iniziata da un' [istruzione Function](function-statement.md)corrispondente. Se l'esecuzione rileva un'istruzione `End Function`, il controllo viene restituito al codice chiamante.|
|`Get`|Obbligatorio per terminare una definizione di routine `Property` iniziata da un' [istruzione Get](get-statement.md)corrispondente. Se l'esecuzione rileva un'istruzione `End Get`, il controllo torna all'istruzione che richiede il valore della proprietà.|
|`If`|Obbligatorio per terminare una definizione del blocco `If`...`Then`...`Else` iniziata da un'istruzione `If` corrispondente. Vedere [if... Quindi... Else (istruzione](if-then-else-statement.md)).|
|`Interface`|Obbligatorio per terminare una definizione di interfaccia iniziata da un' [istruzione di interfaccia](interface-statement.md)corrispondente.|
|`Module`|Obbligatorio per terminare la definizione di un modulo iniziata da un' [istruzione del modulo](module-statement.md)corrispondente.|
|`Namespace`|Obbligatorio per terminare una definizione dello spazio dei nomi iniziata da un' [istruzione dello spazio dei nomi](namespace-statement.md)corrispondente.|
|`Operator`|Obbligatorio per terminare la definizione di un operatore iniziata da un' [istruzione di operatore](operator-statement.md)corrispondente.|
|`Property`|Obbligatorio per terminare una definizione di proprietà iniziata da un' [istruzione Property](property-statement.md)corrispondente.|
|`RaiseEvent`|Obbligatorio per terminare una funzione di accesso `RaiseEvent` iniziata da un'istruzione `RaiseEvent` corrispondente in un' [istruzione di evento](event-statement.md)personalizzata.|
|`RemoveHandler`|Obbligatorio per terminare una funzione di accesso `RemoveHandler` iniziata da un'istruzione `RemoveHandler` corrispondente in un' [istruzione di evento](event-statement.md)personalizzata.|
|`Select`|Obbligatorio per terminare un `Select`...`Case` definizione del blocco iniziata da un'istruzione `Select` corrispondente. Vedere [Select... Istruzione case](select-case-statement.md).  
|`Set`|Obbligatorio per terminare una definizione di routine `Property` iniziata da un' [istruzione set](set-statement.md)corrispondente. Se l'esecuzione rileva un'istruzione `End Set`, il controllo torna all'istruzione impostando il valore della proprietà.  
|`Structure`|Obbligatorio per terminare una definizione di struttura iniziata da un' [istruzione di struttura](structure-statement.md)corrispondente.  
|`Sub`|Obbligatorio per terminare una definizione di routine `Sub` iniziata da un' [istruzione secondaria](sub-statement.md)corrispondente. Se l'esecuzione rileva un'istruzione `End Sub`, il controllo viene restituito al codice chiamante.  
|`SyncLock`|Obbligatorio per terminare una definizione di blocco `SyncLock` iniziata da un'istruzione `SyncLock` corrispondente. Vedere l' [istruzione SyncLock](synclock-statement.md).  
|`Try`|Obbligatorio per terminare una definizione del blocco `Try`...`Catch`...`Finally` iniziata da un'istruzione `Try` corrispondente. Vedere [try... Rileva... Istruzione finally](try-catch-finally-statement.md).  
|`While`|Obbligatorio per terminare una definizione del ciclo `While` iniziata da un'istruzione `While` corrispondente. Vedi [while... End While (istruzione](while-end-while-statement.md)).  
|`With`| Obbligatorio per terminare una definizione di blocco `With` iniziata da un'istruzione `With` corrispondente. Vedi [con... Termina con l'istruzione](with-end-with-statement.md).  
|||
  
## <a name="directives"></a>Direttive

Quando è preceduto da un simbolo di cancelletto (`#`), la parola chiave `End` termina un blocco di pre-elaborazione introdotto dalla direttiva corrispondente.  

```vb
#End ExternalSource
#End If
#End Region
```

|Parte|Descrizione|
|---|---|
|`#End`|Obbligatoria. Termina la definizione del blocco di pre-elaborazione.|
|`ExternalSource`|Obbligatorio per terminare un blocco di origine esterno iniziato da una [direttiva #ExternalSource](../directives/externalsource-directive.md)corrispondente.|
|`If`|Obbligatorio per terminare un blocco di compilazione condizionale iniziato da una direttiva `#If` corrispondente. Vedere [#If... Quindi... #Else direttive](../directives/if-then-else-directives.md).|
|`Region`|Obbligatorio per terminare un blocco di area di origine iniziato da una [direttiva #Region](../directives/region-directive.md)corrispondente.|
|||

## <a name="remarks"></a>Note

L' [istruzione End](end-statement.md), senza una parola chiave aggiuntiva, termina immediatamente l'esecuzione.

## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  

L'istruzione `End`, senza una parola chiave aggiuntiva, non è supportata.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione End](end-statement.md)

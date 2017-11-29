---
title: Fine &lt;parola chiave&gt; istruzione (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.EndDefinition
helpviewer_keywords: End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf0ac1221f8a85a8a43599d9c5ec210884205e5e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a>Fine &lt;parola chiave&gt; istruzione (Visual Basic)
Quando è seguito da una parola chiave aggiuntiva, termina la definizione del blocco di istruzioni introdotto dalla parola chiave.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
 `End`  
 Obbligatorio. Termina la definizione dell'elemento di programmazione.  
  
 `AddHandler`  
 Necessaria per terminare un `AddHandler` funzione di accesso iniziata da un oggetto corrispondente `AddHandler` istruzione in un oggetto personalizzato [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `Class`  
 È necessario terminare una definizione di classe iniziata da un oggetto corrispondente [istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md).  
  
 `Enum`  
 È necessario terminare una definizione di enumerazione iniziata da un oggetto corrispondente [istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 `Event`  
 Necessaria per terminare un `Custom` definizione di evento iniziata da un oggetto corrispondente [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `Function`  
 Necessaria per terminare un `Function` iniziato mediante una corrispondente definizione della stored procedure [istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md). Se l'esecuzione incontra un `End``Function` istruzione, controllo viene restituito il codice chiamante.  
  
 `Get`  
 Necessaria per terminare un `Property` iniziato mediante una corrispondente definizione della stored procedure [l'istruzione Get](../../../visual-basic/language-reference/statements/get-statement.md). Se l'esecuzione incontra un `End``Get` istruzione, controllo viene restituito all'istruzione che richiede il valore della proprietà.  
  
 `If`  
 Necessaria per terminare un `If`... `Then`... `Else` iniziata da un oggetto corrispondente `If` istruzione. Vedere [se... Quindi... Istruzione else](../../../visual-basic/language-reference/statements/if-then-else-statement.md).  
  
 `Interface`  
 È necessario terminare una definizione di interfaccia iniziata da un oggetto corrispondente [istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md).  
  
 `Module`  
 È necessario terminare una definizione di modulo iniziata da un oggetto corrispondente [istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
 `Namespace`  
 È necessario terminare una definizione di spazio dei nomi iniziata da un oggetto corrispondente [istruzione Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md).  
  
 `Operator`  
 È necessario terminare una definizione di operatore iniziata da un oggetto corrispondente [Operator (istruzione)](../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 `Property`  
 È necessario terminare una definizione di proprietà iniziata da un oggetto corrispondente [istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md).  
  
 `RaiseEvent`  
 Necessaria per terminare un `RaiseEvent` funzione di accesso iniziata da un oggetto corrispondente `RaiseEvent` istruzione in un oggetto personalizzato [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `RemoveHandler`  
 Necessaria per terminare un `RemoveHandler` funzione di accesso iniziata da un oggetto corrispondente `RemoveHandler` istruzione in un oggetto personalizzato [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `Select`  
 Necessaria per terminare un `Select`... `Case` iniziata da un oggetto corrispondente `Select` istruzione. Vedere [Seleziona... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
 `Set`  
 Necessaria per terminare un `Property` iniziato mediante una corrispondente definizione della stored procedure [istruzione Set](../../../visual-basic/language-reference/statements/set-statement.md). Se l'esecuzione incontra un `End``Set` istruzione, controllo viene restituito all'istruzione che imposta il valore della proprietà.  
  
 `Structure`  
 È necessario terminare una definizione di struttura iniziata da un oggetto corrispondente [istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md).  
  
 `Sub`  
 Necessaria per terminare un `Sub` iniziato mediante una corrispondente definizione della stored procedure [istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md). Se l'esecuzione incontra un `End``Sub` istruzione, controllo viene restituito il codice chiamante.  
  
 `SyncLock`  
 Necessaria per terminare un `SyncLock` iniziata da un oggetto corrispondente `SyncLock` istruzione. Vedere [istruzione SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md).  
  
 `Try`  
 Necessaria per terminare un `Try`... `Catch`... `Finally` iniziata da un oggetto corrispondente `Try` istruzione. Vedere [provare... Catch... Istruzione finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 `While`  
 Necessaria per terminare un `While` ciclo iniziata da un oggetto corrispondente `While` istruzione. Vedere [mentre... End While (istruzione)](../../../visual-basic/language-reference/statements/while-end-while-statement.md).  
  
 `With`  
 Necessaria per terminare un `With` iniziata da un oggetto corrispondente `With` istruzione. Vedere [con... Terminare con l'istruzione](../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="remarks"></a>Note  
 Il [istruzione End](../../../visual-basic/language-reference/statements/end-statement.md), senza una parola chiave aggiuntiva, termina immediatamente l'esecuzione.  
  
 Quando è preceduta da un simbolo di cancelletto (`#`), il `End` (parola chiave) termina un blocco di pre-elaborazione introdotto dalla direttiva corrispondente.  
  
 `#End`  
 Obbligatorio. Termina la definizione del blocco di pre-elaborazione.  
  
 `#ExternalSource`  
 È necessario terminare un blocco di codice sorgente esterno iniziato da un oggetto corrispondente [#ExternalSource direttiva](../../../visual-basic/language-reference/directives/externalsource-directive.md).  
  
 `#If`  
 È necessario terminare un blocco di compilazione condizionale iniziato da un oggetto corrispondente `#If` direttiva. Vedere [#If... Then... #Else direttive](../../../visual-basic/language-reference/directives/if-then-else-directives.md).  
  
 `#Region`  
 È necessario terminare un blocco di area di origine iniziato da un oggetto corrispondente [#Region direttiva](../../../visual-basic/language-reference/directives/region-directive.md).  
  
## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  
 Il `End` istruzione, senza la parola chiave aggiuntiva, non è supportata.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione End](../../../visual-basic/language-reference/statements/end-statement.md)

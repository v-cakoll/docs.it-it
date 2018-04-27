---
title: Overload dell'operatore
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 42a28f34dda77ecff47f0765335fc29e4418529e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="operator-overloads"></a>Overload dell'operatore
Overload degli operatori consente ai tipi di framework di vengono visualizzati come se fossero primitive di linguaggio predefinito.  
  
 Anche se è consentito e utili in alcuni casi, gli overload degli operatori deve essere utilizzata con cautela. Esistono molti casi, in operatore che l'overload è stato eccessivo, ad esempio l'avvio di finestre di progettazione framework come utilizzare gli operatori per le operazioni che devono essere metodi semplici. Le linee guida seguenti consentono di decidere quando e come utilizzare l'overload degli operatori.  
  
 **X evitare** definizione overload degli operatori, tranne nei tipi che dovrebbero risultare come tipi primitivi (predefiniti).  
  
 **✓ Provare a** definizione overload degli operatori in un tipo che deve essere, ad esempio un tipo primitivo.  
  
 Ad esempio, <xref:System.String?displayProperty=nameWithType> è `operator==` e `operator!=` definito.  
  
 **✓ SI** definire gli overload degli operatori in strutture che rappresentano numeri (ad esempio <xref:System.Decimal?displayProperty=nameWithType>).  
  
 **X non** essere mentre quando si definiscono gli overload degli operatori.  
  
 Overload dell'operatore è utile nei casi in cui è immediatamente ovvio il risultato dell'operazione sarà. Ad esempio, è opportuno essere in grado di sottrarre uno <xref:System.DateTime> da un altro `DateTime` e ottenere un <xref:System.TimeSpan>. Tuttavia, non è appropriata per utilizzare l'operatore union logico per le query di unione due database, o utilizzare l'operatore di spostamento per scrivere in un flusso.  
  
 **X non** forniscono gli overload di operatori, a meno che almeno uno degli operandi è di tipo che definisce l'overload.  
  
 **✓ SI** overload degli operatori in modo simmetrico.  
  
 Ad esempio, se si esegue l'overload di `operator==`, inoltre, è necessario eseguire l'overload di `operator!=`. Analogamente, se esegue l'overload di `operator<`, è inoltre necessario eseguire l'overload di `operator>`e così via.  
  
 **✓ Provare a** fornendo i metodi con nomi descrittivi che corrispondono a ogni operatore di overload.  
  
 Molti linguaggi non supportano l'overload degli operatori. Per questo motivo, è consigliabile che i tipi di overload degli operatori includono un metodo secondario con un nome specifico di dominio appropriato che fornisce una funzionalità equivalente.  
  
 Nella tabella seguente contiene un elenco di operatori e i nomi di metodo descrittivo corrispondente.  
  
|Simbolo dell'operatore c#|Nome dei metadati|Nome descrittivo|  
|-------------------------|-------------------|-------------------|  
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|  
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|  
|`+ (binary)`|`op_Addition`|`Add`|  
|`- (binary)`|`op_Subtraction`|`Subtract`|  
|`* (binary)`|`op_Multiply`|`Multiply`|  
|`/`|`op_Division`|`Divide`|  
|`%`|`op_Modulus`|`Mod or Remainder`|  
|`^`|`op_ExclusiveOr`|`Xor`|  
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|  
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|  
|`&&`|`op_LogicalAnd`|`And`|  
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|  
|`=`|`op_Assign`|`Assign`|  
|`<<`|`op_LeftShift`|`LeftShift`|  
|`>>`|`op_RightShift`|`RightShift`|  
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|  
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|  
|`==`|`op_Equality`|`Equals`|  
|`!=`|`op_Inequality`|`Equals`|  
|`>`|`op_GreaterThan`|`CompareTo`|  
|`<`|`op_LessThan`|`CompareTo`|  
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|  
|`<=`|`op_LessThanOrEqual`|`CompareTo`|  
|`*=`|`op_MultiplicationAssignment`|`Multiply`|  
|`-=`|`op_SubtractionAssignment`|`Subtract`|  
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|  
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|  
|`%=`|`op_ModulusAssignment`|`Mod`|  
|`+=`|`op_AdditionAssignment`|`Add`|  
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|  
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|  
|`,`|`op_Comma`|`Comma`|  
|`/=`|`op_DivisionAssignment`|`Divide`|  
|`--`|`op_Decrement`|`Decrement`|  
|`++`|`op_Increment`|`Increment`|  
|`- (unary)`|`op_UnaryNegation`|`Negate`|  
|`+ (unary)`|`op_UnaryPlus`|`Plus`|  
|`~`|`op_OnesComplement`|`OnesComplement`|  
  
### <a name="overloading-operator-"></a>Overload dell'operatore = =  
 L'overload `operator ==` è piuttosto complessi. La semantica dell'operatore desidera essere compatibili con molti altri membri, ad esempio <xref:System.Object.Equals%2A?displayProperty=nameWithType>.  
  
### <a name="conversion-operators"></a>Operatori di conversione  
 Gli operatori di conversione sono gli operatori unari che consentono la conversione da un tipo a un altro. Gli operatori devono essere definiti come membri statici in cui l'operando o il tipo restituito. Esistono due tipi di operatori di conversione: implicite ed esplicite.  
  
 **X non** forniscono un operatore di conversione se tale conversione non è previsto chiaramente dagli utenti finali.  
  
 **X non** definire operatori di conversione di fuori di dominio del tipo.  
  
 Ad esempio, <xref:System.Int32>, <xref:System.Double>, e <xref:System.Decimal> sono tutti i tipi numerici, mentre <xref:System.DateTime> non. Pertanto, non deve essere presente nessun operatore di conversione per convertire un `Double(long)` per un `DateTime`. In questo caso è preferibile utilizzare un costruttore.  
  
 **X non** forniscono un operatore di conversione implicita, se la conversione è potenzialmente perdita di dati.  
  
 Ad esempio, deve essere presente una conversione implicita da `Double` a `Int32` perché `Double` ha una gamma più ampia rispetto a `Int32`. Anche se la conversione è potenzialmente perdita di dati, è possibile specificare un operatore di conversione esplicita.  
  
 **X non** generare eccezioni da cast impliciti.  
  
 È molto difficile per gli utenti finali a comprendere ciò che accade, poiché potrebbero non essere consapevoli che una conversione viene eseguita.  
  
 **✓ SI** throw <xref:System.InvalidCastException?displayProperty=nameWithType> se una chiamata a un operatore cast comporta una perdita di dati conversione e il contratto dell'operatore non consente conversioni perdita di dati.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)

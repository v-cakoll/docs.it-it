---
title: Overload dell'operatore
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ca42d25a5f3456c6a10eff76d7015656322abae
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43874056"
---
# <a name="operator-overloads"></a>Overload dell'operatore
Overload degli operatori consentono tipi di framework venga visualizzato come se fossero primitive di linguaggio predefinito.  
  
 Sebbene sia consentita e utili in alcuni casi, gli overload degli operatori deve essere utilizzata con cautela. Ci sono molti i casi in cui operatore l'overload è stato fatto un uso improprio, ad esempio quando le finestre di progettazione di framework iniziato a usare gli operatori per le operazioni che devono essere metodi semplici. Le linee guida seguenti consentono di decidere quando e come usare l'overload degli operatori.  
  
 **X AVOID** definizione overload degli operatori, tranne nei tipi che dovrebbero risultare come tipi primitivi (predefiniti).  
  
 **✓ CONSIDER** definizione overload degli operatori in un tipo che deve essere, ad esempio un tipo primitivo.  
  
 Ad esempio, <xref:System.String?displayProperty=nameWithType> ha `operator==` e `operator!=` definito.  
  
 **✓ DO** definire gli overload degli operatori in strutture che rappresentano numeri (ad esempio <xref:System.Decimal?displayProperty=nameWithType>).  
  
 **X DO NOT** essere mentre quando si definiscono gli overload degli operatori.  
  
 L'overload degli operatori è utile nei casi in cui è immediatamente ovvio quale sarà il risultato dell'operazione. Ad esempio, è opportuno essere in grado di sottrarre uno <xref:System.DateTime> da un altro `DateTime` e ottenere un <xref:System.TimeSpan>. Non è tuttavia appropriata per utilizzare l'operatore union logico per le query di unione due database o usare l'operatore di spostamento per scrivere in un flusso.  
  
 **X DO NOT** forniscono gli overload di operatori, a meno che almeno uno degli operandi è di tipo che definisce l'overload.  
  
 **✓ DO** overload degli operatori in modo simmetrico.  
  
 Ad esempio, se si esegue l'overload di `operator==`, è anche necessario eseguire l'overload di `operator!=`. In modo analogo, se si esegue l'overload di `operator<`, è anche necessario eseguire l'overload di `operator>`e così via.  
  
 **✓ CONSIDER** fornendo i metodi con nomi descrittivi che corrispondono a ogni operatore di overload.  
  
 Molti linguaggi non supportano l'overload degli operatori. Per questo motivo, è consigliabile che i tipi che eseguono l'overload degli operatori includono un metodo secondario con un nome specifico di dominio appropriato che fornisce una funzionalità equivalente.  
  
 Nella tabella seguente contiene un elenco di operatori e i nomi di metodo descrittivo corrispondente.  
  
|Simbolo operatore c#|Nome dei metadati|Nome descrittivo|  
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
 L'overload `operator ==` è piuttosto complicata. La semantica dell'operatore desidera essere compatibili con molti altri membri, ad esempio <xref:System.Object.Equals%2A?displayProperty=nameWithType>.  
  
### <a name="conversion-operators"></a>Operatori di conversione  
 Gli operatori di conversione sono gli operatori unari che consentono la conversione da un tipo a altro. Gli operatori devono essere definiti come membri statici su operando o il tipo restituito. Esistono due tipi di operatori di conversione: implicite ed esplicite.  
  
 **X DO NOT** forniscono un operatore di conversione se tale conversione non è previsto chiaramente dagli utenti finali.  
  
 **X DO NOT** definire operatori di conversione di fuori di dominio del tipo.  
  
 Ad esempio, <xref:System.Int32>, <xref:System.Double>, e <xref:System.Decimal> sono tutti i tipi numerici, mentre <xref:System.DateTime> non. Pertanto, non vi sarà alcun operatore di conversione per convertire un `Double(long)` a un `DateTime`. In tal caso è preferibile utilizzare un costruttore.  
  
 **X DO NOT** forniscono un operatore di conversione implicita, se la conversione è potenzialmente perdita di dati.  
  
 Ad esempio, deve essere presente una conversione implicita da `Double` al `Int32` poiché `Double` dispone di una gamma più ampia rispetto a `Int32`. Anche se la conversione è potenzialmente con perdita di dati, è possibile specificare un operatore di conversione esplicita.  
  
 **X DO NOT** generare eccezioni da cast impliciti.  
  
 È molto difficile per gli utenti finali a comprendere ciò che avviene, in quanto potrebbero non essere consapevoli che una conversione ha luogo.  
  
 **✓ DO** throw <xref:System.InvalidCastException?displayProperty=nameWithType> se una chiamata a un operatore cast comporta una perdita di dati conversione e il contratto dell'operatore non consente conversioni perdita di dati.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)  
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)

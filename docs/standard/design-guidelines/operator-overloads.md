---
title: Overload dell'operatore
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
ms.openlocfilehash: 893b7d1f76dfb059a0ddca77dfd8654812e9ae12
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289733"
---
# <a name="operator-overloads"></a>Overload dell'operatore
Gli overload degli operatori consentono la visualizzazione di tipi di Framework come se fossero primitive di linguaggio incorporati.

 Sebbene sia consentito e utile in alcune situazioni, gli overload degli operatori devono essere usati con cautela. In molti casi l'overload degli operatori è stato abusato, ad esempio quando le finestre di progettazione del Framework hanno iniziato a usare gli operatori per le operazioni che devono essere metodi semplici. Le linee guida seguenti consentono di decidere quando e come usare l'overload degli operatori.

 ❌EVITARE di definire gli overload degli operatori, ad eccezione dei tipi che dovrebbero avere un aspetto simile ai tipi primitivi (incorporati).

 ✔️ CONSIDERARE la definizione di overload degli operatori in un tipo che dovrebbe essere simile a un tipo primitivo.

 Ad esempio, <xref:System.String?displayProperty=nameWithType> ha `operator==` e `operator!=` definito.

 ✔️ definiscono gli overload degli operatori negli struct che rappresentano i numeri (ad esempio <xref:System.Decimal?displayProperty=nameWithType> ).

 ❌NON è carino quando si definiscono gli overload degli operatori.

 L'overload degli operatori è utile nei casi in cui è immediatamente evidente quale sarà il risultato dell'operazione. Ad esempio, è sensato poter sottrarre un <xref:System.DateTime> oggetto da un altro `DateTime` e ottenere un <xref:System.TimeSpan> . Tuttavia, non è consigliabile usare l'operatore di unione logica per unire due query di database o per usare l'operatore Shift per scrivere in un flusso.

 ❌Non fornire overload degli operatori a meno che almeno uno degli operandi sia del tipo che definisce l'overload.

 ✔️ gli operatori di overload in modo simmetrico.

 Se, ad esempio, si esegue l'overload di `operator==` , è necessario anche eseguire l'overload di `operator!=` . Analogamente, se si esegue l'overload di `operator<` , è inoltre necessario eseguire l'overload di `operator>` e così via.

 ✔️ considerare la possibilità di fornire metodi con nomi descrittivi che corrispondono a ogni operatore di overload.

 Molti linguaggi non supportano l'overload degli operatori. Per questo motivo, è consigliabile che i tipi che gli operatori di overload includano un metodo secondario con un nome appropriato specifico del dominio che fornisca funzionalità equivalenti.

 La tabella seguente contiene un elenco di operatori e i nomi di metodo descrittivi corrispondenti.

|Simbolo dell'operatore C#|Nome dei metadati|Nome descrittivo|
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

### <a name="overloading-operator-"></a>Overload Operator = =
 L'overload `operator ==` è piuttosto complesso. La semantica dell'operatore deve essere compatibile con diversi altri membri, ad esempio <xref:System.Object.Equals%2A?displayProperty=nameWithType> .

### <a name="conversion-operators"></a>Operatori di conversione
 Gli operatori di conversione sono operatori unari che consentono la conversione da un tipo a un altro. Gli operatori devono essere definiti come membri statici nell'operando o nel tipo restituito. Esistono due tipi di operatori di conversione: implicito ed esplicito.

 ❌Non fornire un operatore di conversione se tale conversione non è chiaramente prevista dagli utenti finali.

 ❌NON definire operatori di conversione al di fuori del dominio di un tipo.

 Ad esempio, <xref:System.Int32> , <xref:System.Double> e <xref:System.Decimal> sono tutti tipi numerici, mentre <xref:System.DateTime> non è. Pertanto, non deve essere presente alcun operatore di conversione per convertire un oggetto `Double(long)` in un oggetto `DateTime` . In tal caso, è preferibile un costruttore.

 ❌NON fornire un operatore di conversione implicita se la conversione è potenzialmente perdita di perdite.

 Ad esempio, non deve essere presente una conversione implicita da `Double` a `Int32` perché `Double` ha un intervallo più ampio rispetto a `Int32` . È possibile fornire un operatore di conversione esplicito anche se la conversione è potenzialmente perdita di perdite.

 ❌Non generare eccezioni da cast impliciti.

 È molto difficile per gli utenti finali comprendere ciò che accade, perché potrebbero non essere consapevoli del fatto che è stata eseguita una conversione.

 ✔️ generano <xref:System.InvalidCastException?displayProperty=nameWithType> se una chiamata a un operatore cast comporta una conversione con perdita di dati e il contratto dell'operatore non consente le conversioni con perdita di dati.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di membri](member.md)
- [Linee guida per la progettazione di Framework](index.md)

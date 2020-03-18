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
ms.openlocfilehash: 0999e94c8d77396b237522e89c51206ce1226718
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400568"
---
# <a name="operator-overloads"></a>Overload dell'operatore
Gli overload degli operatori consentono ai tipi di framework di apparire come se fossero primitive di linguaggio incorporate.

 Sebbene siano consentiti e utili in alcune situazioni, gli overload dell'operatore devono essere usati con cautela. Esistono molti casi in cui l'overload degli operatori è stato abusato, ad esempio quando i progettisti del framework hanno iniziato a utilizzare gli operatori per le operazioni che devono essere metodi semplici. Le linee guida seguenti dovrebbero aiutare a decidere quando e come usare l'overload dell'operatore.

 ❌AVOID che definisce gli overload degli operatori, ad eccezione dei tipi che dovrebbero avere l'aspetto di tipi primitivi (incorporati).

 ✔️ CONSIDER che definisce gli overload dell'operatore in un tipo che dovrebbe sembrare un tipo primitivo.

 Ad <xref:System.String?displayProperty=nameWithType> esempio, `operator==` `operator!=` ha e definito.

 ✔️ dedefinire gli overload degli operatori in <xref:System.Decimal?displayProperty=nameWithType>struct che rappresentano numeri (ad esempio ).

 ❌NON essere carino quando si definiscono gli overload dell'operatore.

 L'overload dell'operatore è utile nei casi in cui è immediatamente evidente quale sarà il risultato dell'operazione. Ad esempio, ha senso essere in <xref:System.DateTime> grado `DateTime` di <xref:System.TimeSpan>sottrarre uno dall'altro e ottenere un . Tuttavia, non è appropriato utilizzare l'operatore di unione logica per unionare due query di database o utilizzare l'operatore shift per scrivere in un flusso.

 ❌DO NOT fornire overload dell'operatore a meno che almeno uno degli operandi sia del tipo che definisce l'overload.

 ✔️ gli operatori DO eseguono l'overload degli operatori in modo simmetrico.

 Ad esempio, se `operator==`si esegue l'overload di , è necessario eseguire anche l'overload di `operator!=`. Analogamente, se `operator<`si esegue l'overload di , è necessario eseguire anche l'overload di `operator>`, e così via.

 ✔️ CONSIDER che forniscono metodi con nomi descrittivi che corrispondono a ogni operatore di overload.

 Molti linguaggi non supportano l'overload degli operatori. Per questo motivo, è consigliabile che i tipi che eseguono l'overload degli operatori includano un metodo secondario con un nome specifico di dominio appropriato che fornisce funzionalità equivalenti.

 La tabella seguente contiene un elenco di operatori e i nomi dei metodi descrittivi corrispondenti.

|Simbolo dell'operatore di C|Nome metadati|Nome descrittivo|
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

### <a name="overloading-operator-"></a>Operatore di Overloading
 Sovraccaricare `operator ==` è piuttosto complicato. La semantica dell'operatore deve essere compatibile con <xref:System.Object.Equals%2A?displayProperty=nameWithType>diversi altri membri, ad esempio .

### <a name="conversion-operators"></a>Operatori di conversione
 Gli operatori di conversione sono operatori unari che consentono la conversione da un tipo a un altro. Gli operatori devono essere definiti come membri statici nell'operando o nel tipo restituito. Esistono due tipi di operatori di conversione: implicito ed esplicito.

 ❌NON fornire un operatore di conversione se tale conversione non è chiaramente prevista dagli utenti finali.

 ❌NON definire operatori di conversione all'esterno del dominio di un tipo.

 Ad <xref:System.Int32>esempio, <xref:System.Double>, <xref:System.Decimal> e sono tutti <xref:System.DateTime> tipi numerici, mentre non lo è. Pertanto, non deve essere presente `Double(long)` alcun `DateTime`operatore di conversione per convertire un oggetto in un oggetto . In tal caso, è preferibile utilizzare un costruttore.

 ❌NON fornire un operatore di conversione implicito se la conversione è potenzialmente lossy.

 Ad esempio, non deve essere `Double` presente `Int32` `Double` una conversione `Int32`implicita da a perché ha un intervallo più ampio di . Un operatore di conversione esplicito può essere fornito anche se la conversione è potenzialmente lossy.

 ❌DO NOT generare eccezioni da cast impliciti.

 È molto difficile per gli utenti finali capire cosa sta succedendo, perché potrebbero non essere consapevoli che è in corso una conversione.

 ✔️ DO <xref:System.InvalidCastException?displayProperty=nameWithType> throw se una chiamata a un operatore cast genera una conversione lossy e il contratto dell'operatore non consente conversioni con perdita di dati.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)

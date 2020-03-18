---
title: Parole chiave di C#
ms.date: 03/07/2017
f1_keywords:
- cs.keywords
helpviewer_keywords:
- keywords [C#]
- C# language, keywords
- Visual C#, keywords
- '@ keyword'
ms.assetid: e929b0f2-4b92-4d37-8060-23d323b098ad
ms.openlocfilehash: 928917d25b5f3f97c4b8cdff85efdaa1957be41e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79399315"
---
# <a name="c-keywords"></a>Parole chiave di C#

Le parole chiave sono identificatori riservati predefiniti che hanno significati particolari per il compilatore. Non possono essere usati come identificatori nel programma a meno che non includano il prefisso `@`. Ad esempio, `@if` è un identificatore valido mentre `if` non lo è, perché `if` è una parola chiave.  
  
 Nella prima tabella di questo argomento vengono elencate le parole chiave che sono identificatori riservati in qualsiasi parte di un programma C#. Nella seconda tabella di questo argomento vengono elencate le parole chiave contestuali in C#. Le parole chiave contestuali hanno un significato speciale solo in un contesto limitato del programma e possono essere usate come identificatori al di fuori di tale contesto. In genere, le nuove parole chiave aggiunte al linguaggio C# vengono aggiunte come parole chiave contestuali per evitare problemi con i programmi scritti nelle versioni precedenti.  
  
|||||  
|---|---|---|---|  
|[astratto](abstract.md)|[Come](../operators/type-testing-and-cast.md#as-operator)|[base](base.md)|[Bool](../builtin-types/bool.md)|  
|[Pausa](break.md)|[byte](../builtin-types/integral-numeric-types.md)|[case](switch.md)|[generazione](try-catch.md)|  
|[Char](../builtin-types/char.md)|[selezionata](checked.md)|[Classe](class.md)|[const](const.md)|  
|[Continuare](continue.md)|[Decimale](../builtin-types/floating-point-numeric-types.md)|[Predefinito](default.md)|[Delegato](../builtin-types/reference-types.md)|  
|[fare](do.md)|[Doppia](../builtin-types/floating-point-numeric-types.md)|[else](if-else.md)|[Enum](../builtin-types/enum.md)|  
|[Evento](event.md)|[Esplicito](../operators/user-defined-conversion-operators.md)|[Extern](extern.md)|[false](../builtin-types/bool.md)|  
|[Infine](try-finally.md)|[Fisso](fixed-statement.md)|[Galleggiante](../builtin-types/floating-point-numeric-types.md)|[Per](for.md)|  
|[Foreach](foreach-in.md)|[Goto](goto.md)|[Se](if-else.md)|[Implicita](../operators/user-defined-conversion-operators.md)|  
|[in](in.md)|[Int](../builtin-types/integral-numeric-types.md)|[Interfaccia](interface.md)|[Interno](internal.md)|
|[È](is.md)|[lock](lock-statement.md)|[Lungo](../builtin-types/integral-numeric-types.md)|[Namespace](namespace.md)|
|[Nuovo](../operators/new-operator.md)|[Null](null.md)|[Oggetto](../builtin-types/reference-types.md)|[Operatore](../operators/operator-overloading.md)|
|[Cambio](out.md)|[prevalere](override.md)|[Params](params.md)|[Privato](private.md)|
|[Protetto](protected.md)|[pubblico](public.md)|[Readonly](readonly.md)|[ref](ref.md)|
|[Ritorno](return.md)|[sbyte](../builtin-types/integral-numeric-types.md)|[Sigillato](sealed.md)|[short](../builtin-types/integral-numeric-types.md)||
[sizeof](../operators/sizeof.md)|[stackalloc](../operators/stackalloc.md)|[Statico](static.md)|[Stringa](../builtin-types/reference-types.md)|
|[struct](../builtin-types/struct.md)|[Interruttore](switch.md)|[Questo](this.md)|[generazione](throw.md)|
|[true](../builtin-types/bool.md)|[Provare](try-catch.md)|[Typeof](../operators/type-testing-and-cast.md#typeof-operator)|[uint](../builtin-types/integral-numeric-types.md)|
|[Ulong](../builtin-types/integral-numeric-types.md)|[non selezionata](unchecked.md)|[Pericoloso](unsafe.md)|[ushort](../builtin-types/integral-numeric-types.md)|
|[Utilizzando](using.md)|[utilizzando statica](using-static.md)|[Virtuale](virtual.md)|[Vuoto](../builtin-types/void.md)|
|[Volatile](volatile.md)|[mentre](while.md)|

## <a name="contextual-keywords"></a>Parole chiave contestuali

 Una parola chiave contestuale viene usata per conferire un significato particolare nel codice, ma non è una parola riservata in C#. Alcune parole chiave contestuali, ad esempio `partial` e `where`, hanno significati speciali in due o più contesti.  
  
||||  
|---|---|---|  
|[aggiungi](add.md)|[alias](extern-alias.md)|[Ascendente](ascending.md)|
|[Async](async.md)|[Attendono](../operators/await.md)|[da parte di](by.md)|
|[Discendente](descending.md)|[dinamico](../builtin-types/reference-types.md)|[Uguale](equals.md)|
|[Da](from-clause.md)|[get](get.md)|[Globale](../operators/namespace-alias-qualifier.md)|
|[utenti](group-clause.md)|[In](into.md)|[Unirsi](join-clause.md)|
|[Lasciare](let-clause.md)|[nameof](../operators/nameof.md)|[on](on.md)|
|[Orderby](orderby-clause.md)|[partial (tipo)](partial-type.md)|[partial (metodo)](partial-method.md)|
|[rimozione](remove.md)|[Selezionare](select-clause.md)|[Impostare](set.md)|
|[non gestito (vincolo di tipo generico)](where-generic-type-constraint.md)|[Valore](value.md)|[Var](var.md)|
|[when (condizione di filtro)](when.md)|[where (vincolo di tipo generico)](where-generic-type-constraint.md)|[where (clausola query)](where-clause.md)|
|[yield](yield.md)| | |
  
## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)

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
ms.openlocfilehash: 251046a8bd825a90d817965f9f747d08d4492197
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102034"
---
# <a name="c-keywords"></a>Parole chiave di C#

Le parole chiave sono identificatori riservati predefiniti che hanno significati particolari per il compilatore. Non possono essere usati come identificatori nel programma a meno che non includano il prefisso `@`. Ad esempio, `@if` è un identificatore valido mentre `if` non lo è, perché `if` è una parola chiave.  
  
 Nella prima tabella di questo argomento vengono elencate le parole chiave che sono identificatori riservati in qualsiasi parte di un programma C#. Nella seconda tabella di questo argomento vengono elencate le parole chiave contestuali in C#. Le parole chiave contestuali hanno un significato speciale solo in un contesto limitato del programma e possono essere usate come identificatori al di fuori di tale contesto. In genere, le nuove parole chiave aggiunte al linguaggio C# vengono aggiunte come parole chiave contestuali per evitare problemi con i programmi scritti nelle versioni precedenti.  
  
|||||  
|---|---|---|---|  
|[astratto](abstract.md)|[Come](../operators/type-testing-and-cast.md#as-operator)|[base](base.md)|[bool](../builtin-types/bool.md)|  
|[break](break.md)|[byte](../builtin-types/integral-numeric-types.md)|[Caso](switch.md)|[generazione](try-catch.md)|  
|[char](../builtin-types/char.md)|[Controllato](checked.md)|[Classe](class.md)|[const](const.md)|  
|[Continuare](continue.md)|[decimal](../builtin-types/floating-point-numeric-types.md)|[Predefinito](default.md)|[Delegato](../builtin-types/reference-types.md)|  
|[do](do.md)|[double](../builtin-types/floating-point-numeric-types.md)|[else](if-else.md)|[enum](../builtin-types/enum.md)|  
|[event](event.md)|[Esplicito](../operators/user-defined-conversion-operators.md)|[extern](extern.md)|[false](../builtin-types/bool.md)|  
|[Infine](try-finally.md)|[Fisso](fixed-statement.md)|[float](../builtin-types/floating-point-numeric-types.md)|[for](for.md)|  
|[Foreach](foreach-in.md)|[goto](goto.md)|[if](if-else.md)|[Implicita](../operators/user-defined-conversion-operators.md)|  
|[in](in.md)|[int](../builtin-types/integral-numeric-types.md)|[Interfaccia](interface.md)|[internal](internal.md)|
|[is](is.md)|[lock](lock-statement.md)|[long](../builtin-types/integral-numeric-types.md)|[Namespace](namespace.md)|
|[Nuovo](../operators/new-operator.md)|[Null](null.md)|[Oggetto](../builtin-types/reference-types.md)|[Operatore](../operators/operator-overloading.md)|
|[Cambio](out.md)|[override](override.md)|[params](params.md)|[private](private.md)|
|[protected](protected.md)|[public](public.md)|[Readonly](readonly.md)|[ref](ref.md)|
|[return](return.md)|[sbyte](../builtin-types/integral-numeric-types.md)|[sealed](sealed.md)|[short](../builtin-types/integral-numeric-types.md)||
[sizeof](../operators/sizeof.md)|[stackalloc](../operators/stackalloc.md)|[static](static.md)|[string](../builtin-types/reference-types.md)|
|[struct](../builtin-types/struct.md)|[switch](switch.md)|[this](this.md)|[throw](throw.md)|
|[true](../builtin-types/bool.md)|[Provare](try-catch.md)|[Typeof](../operators/type-testing-and-cast.md#typeof-operator)|[uint](../builtin-types/integral-numeric-types.md)|
|[Ulong](../builtin-types/integral-numeric-types.md)|[unchecked](unchecked.md)|[Pericoloso](unsafe.md)|[ushort](../builtin-types/integral-numeric-types.md)|
|[Utilizzando](using.md)|[virtuale](virtual.md)|[void](../builtin-types/void.md)|[volatile](volatile.md)|
|[while](while.md)|

## <a name="contextual-keywords"></a>Parole chiave contestuali

 Una parola chiave contestuale viene usata per conferire un significato particolare nel codice, ma non è una parola riservata in C#. Alcune parole chiave contestuali, ad esempio `partial` e `where`, hanno significati speciali in due o più contesti.  
  
||||  
|---|---|---|  
|[aggiungi](add.md)|[alias](extern-alias.md)|[ascending](ascending.md)|
|[async](async.md)|[Attendono](../operators/await.md)|[by](by.md)|
|[descending](descending.md)|[dinamico](../builtin-types/reference-types.md)|[equals](equals.md)|
|[from](from-clause.md)|[get](get.md)|[Globale](../operators/namespace-alias-qualifier.md)|
|[utenti](group-clause.md)|[into](into.md)|[Unirsi](join-clause.md)|
|[Lasciare](let-clause.md)|[nameof](../operators/nameof.md)|[su](on.md)|
|[Orderby](orderby-clause.md)|[partial (tipo)](partial-type.md)|[partial (metodo)](partial-method.md)|
|[rimozione](remove.md)|[Selezionare](select-clause.md)|[Impostare](set.md)|
|[non gestito (vincolo di tipo generico)](where-generic-type-constraint.md)|[value](value.md)|[var](var.md)|
|[when (condizione di filtro)](when.md)|[where (vincolo di tipo generico)](where-generic-type-constraint.md)|[where (clausola query)](where-clause.md)|
|[yield](yield.md)| | |
  
## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)

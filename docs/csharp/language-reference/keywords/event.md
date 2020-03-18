---
title: event - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
helpviewer_keywords:
- event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
ms.openlocfilehash: eb1805ed55921497fea88e6b39989c876ef003d1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713562"
---
# <a name="event-c-reference"></a>event (riferimenti per C

La parola chiave `event` viene usata per dichiarare un evento in una classe autore.

## <a name="example"></a>Esempio

L'esempio seguente illustra come dichiarare e generare un evento che usa <xref:System.EventHandler> come tipo di delegato sottostante. Per l'esempio di codice completo in <xref:System.EventHandler%601> cui viene illustrato anche come utilizzare il tipo delegato generico e come sottoscrivere un evento e creare un metodo del gestore eventi, vedere [Come pubblicare eventi conformi alle linee guida](../../programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)di .NET Framework .

[!code-csharp[csrefKeywordsModifiers#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#7)]

Gli eventi sono un tipo di delegati multicast speciali che possono essere chiamati solo dall'interno della classe o dello struct in cui sono dichiarati (la classe autore). Se altre classi o altri struct sottoscrivono l'evento, i metodi di gestione eventi corrispondenti verranno chiamati quando la classe publisher genera l'evento. Per altre informazioni e altri esempi di codice, vedere [Eventi](../../programming-guide/events/index.md) e [Delegati](../../programming-guide/delegates/index.md).

Gli eventi possono essere contrassegnati come [public](./public.md), [private](./private.md), [protected](./protected.md), [internal](./internal.md), [protected internal](./protected-internal.md)o private [protected](./private-protected.md). Questi modificatori di accesso definiscono in che modo gli utenti della classe possono accedere all'evento. Per altre informazioni, vedere [Modificatori di accesso](../../programming-guide/classes-and-structs/access-modifiers.md).

## <a name="keywords-and-events"></a>Parole chiave ed eventi

Agli eventi si applicano le parole chiave seguenti.

|Parola chiave|Descrizione|Per ulteriori informazioni|
|-------------|-----------------|--------------------------|
|[Statico](./static.md)|Rende l'evento disponibile per i chiamanti in qualsiasi momento, anche se non esiste alcuna istanza della classe.|[Classi statiche e membri di classi statiche](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|
|[Virtuale](./virtual.md)|Consente alle classi derivate di eseguire l'override del comportamento dell'evento tramite la parola chiave [override](./override.md).|[Ereditarietà](../../programming-guide/classes-and-structs/inheritance.md)|
|[Sigillato](./sealed.md)|Specifica che per le classi derivate l'evento non è più virtuale.||
|[astratto](./abstract.md)|Il compilatore non genererà i blocchi di funzioni di accesso degli eventi `add` e `remove` e pertanto le classi derivate dovranno fornire la propria implementazione.||

Un evento può essere dichiarato statico mediante la parola chiave [static](./static.md). Ciò rende l'evento disponibile per i chiamanti in qualsiasi momento, anche se non esiste alcuna istanza della classe. Per ulteriori informazioni, vedere [Classi statiche e Membri di classi statiche](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).

Un evento può essere contrassegnato come virtuale mediante la parola chiave [virtual](./virtual.md). Ciò consente alle classi derivate di eseguire l'override del comportamento dell'evento tramite la parola chiave [override](./override.md). Per altre informazioni, vedere [Ereditarietà](../../programming-guide/classes-and-structs/inheritance.md). Un evento che esegue l'override di un evento virtuale può anche essere contrassegnato come [sealed](./sealed.md), in modo che non risulti più virtuale per le classi derivate. Infine, un evento può essere dichiarato [abstract](./abstract.md), in modo che il compilatore non generi blocchi di funzioni di accesso agli eventi `add` e `remove`. Le classi derivate devono pertanto fornire la propria implementazione.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](./index.md)
- [aggiungi](./add.md)
- [rimozione](./remove.md)
- [Modificatori](index.md)
- [Come combinare delegati (delegati multicast)](../../programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)

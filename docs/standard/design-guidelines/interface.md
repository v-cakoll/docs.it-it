---
title: Progettazione di interfacce
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
ms.openlocfilehash: f589d47d5b945179430275598996b2fb77e92848
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289031"
---
# <a name="interface-design"></a>Progettazione di interfacce
Sebbene la maggior parte delle API venga modellata con le classi e gli struct, esistono casi in cui le interfacce sono più appropriate o sono l'unica opzione.

 CLR non supporta l'ereditarietà multipla, ovvero le classi CLR non possono ereditare da più di una classe di base, ma consente ai tipi di implementare una o più interfacce, oltre a ereditare da una classe base. Pertanto, le interfacce vengono spesso utilizzate per ottenere l'effetto di più ereditarietà. Ad esempio, <xref:System.IDisposable> è un'interfaccia che consente ai tipi di supportare la disposizione indipendente da qualsiasi altra gerarchia di ereditarietà in cui desiderano partecipare.

 L'altra situazione in cui la definizione di un'interfaccia è appropriata è la creazione di un'interfaccia comune che può essere supportata da diversi tipi, inclusi alcuni tipi di valore. I tipi di valore non possono ereditare da tipi diversi da <xref:System.ValueType> , ma possono implementare interfacce, quindi l'utilizzo di un'interfaccia è l'unica opzione per fornire un tipo di base comune.

 ✔️ definire un'interfaccia se è necessario che alcune API comuni siano supportate da un set di tipi che includono tipi di valore.

 ✔️ VALUTARE la definizione di un'interfaccia se è necessario supportare la relativa funzionalità sui tipi che già ereditano da un altro tipo.

 ❌EVITARE di usare le interfacce del marcatore (interfacce senza membri).

 Se è necessario contrassegnare una classe come avente una caratteristica specifica (marcatore), in generale, usare un attributo personalizzato anziché un'interfaccia.

 ✔️ forniscono almeno un tipo che è un'implementazione di un'interfaccia.

 Questa operazione consente di convalidare la progettazione dell'interfaccia. Ad esempio, <xref:System.Collections.Generic.List%601> è un'implementazione dell' <xref:System.Collections.Generic.IList%601> interfaccia.

 ✔️ forniscono almeno un'API che utilizza ogni interfaccia definita, ovvero un metodo che accetta l'interfaccia come un parametro o una proprietà tipizzata come interfaccia.

 Questa operazione consente di convalidare la progettazione dell'interfaccia. Ad esempio, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> utilizza l' <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interfaccia.

 ❌NON aggiungere membri a un'interfaccia precedentemente spedita.

 In questo modo si interrompono le implementazioni dell'interfaccia. È necessario creare una nuova interfaccia per evitare problemi di controllo delle versioni.

 Fatta eccezione per le situazioni descritte in queste linee guida, è consigliabile, in generale, scegliere classi anziché interfacce nella progettazione di librerie riutilizzabili di codice gestito.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di tipi](type.md)
- [Linee guida per la progettazione di Framework](index.md)

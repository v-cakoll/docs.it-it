---
title: Progettazione di interfacce
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
ms.openlocfilehash: 06b2e0d281314f3bd6346a7dbbd8bb56928fe58b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709296"
---
# <a name="interface-design"></a>Progettazione di interfacce
Sebbene la maggior parte delle API venga modellata con le classi e gli struct, esistono casi in cui le interfacce sono più appropriate o sono l'unica opzione.  
  
 CLR non supporta l'ereditarietà multipla, ovvero le classi CLR non possono ereditare da più di una classe di base, ma consente ai tipi di implementare una o più interfacce, oltre a ereditare da una classe base. Pertanto, le interfacce vengono spesso utilizzate per ottenere l'effetto di più ereditarietà. Ad esempio, <xref:System.IDisposable> è un'interfaccia che consente ai tipi di supportare la disposizione indipendente da qualsiasi altra gerarchia di ereditarietà in cui desiderano partecipare.  
  
 L'altra situazione in cui la definizione di un'interfaccia è appropriata è la creazione di un'interfaccia comune che può essere supportata da diversi tipi, inclusi alcuni tipi di valore. I tipi di valore non possono ereditare da tipi diversi da <xref:System.ValueType>, ma possono implementare interfacce, quindi l'utilizzo di un'interfaccia è l'unica opzione per fornire un tipo di base comune.  
  
 **✓ DO** definire un'interfaccia se è necessario alcune API comuni devono essere supportati da un set di tipi che include i tipi di valore.  
  
 **✓ CONSIDER** che definisce un'interfaccia se è necessario supportare le funzionalità nei tipi che ereditano già da un altro tipo.  
  
 **X AVOID** utilizzano interfacce marcatore (interfacce senza membri).  
  
 Se è necessario contrassegnare una classe come avente una caratteristica specifica (marcatore), in generale, usare un attributo personalizzato anziché un'interfaccia.  
  
 **✓ DO** fornire almeno un tipo che è un'implementazione di un'interfaccia.  
  
 Questa operazione consente di convalidare la progettazione dell'interfaccia. <xref:System.Collections.Generic.List%601>, ad esempio, è un'implementazione dell'interfaccia <xref:System.Collections.Generic.IList%601>.  
  
 **✓ DO** forniscono almeno una API che utilizza ciascuna interfaccia definita (un metodo che utilizza l'interfaccia come un parametro o una proprietà tipizzato come l'interfaccia).  
  
 Questa operazione consente di convalidare la progettazione dell'interfaccia. Ad esempio, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> utilizza l'interfaccia <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType>.  
  
 **X DO NOT** aggiungere membri a un'interfaccia che è già stata distribuita.  
  
 In questo modo si interrompono le implementazioni dell'interfaccia. È necessario creare una nuova interfaccia per evitare problemi di controllo delle versioni.  
  
 Fatta eccezione per le situazioni descritte in queste linee guida, è consigliabile, in generale, scegliere classi anziché interfacce nella progettazione di librerie riutilizzabili di codice gestito.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)

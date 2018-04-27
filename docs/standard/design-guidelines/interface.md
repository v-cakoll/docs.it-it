---
title: Progettazione di interfacce
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8636653ca856693961cbfc73e9170410ed2cd361
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="interface-design"></a>Progettazione di interfacce
Sebbene la maggior parte delle API vengono modellate meglio utilizzando le classi e struct, vi sono casi in cui le interfacce sono più adatti o l'unica opzione.  
  
 Common Language Runtime non supporta l'ereditarietà multipla (ad esempio, le classi CLR non possono ereditare da più di una classe di base), ma consente i tipi implementare una o più interfacce, oltre che eredita da una classe di base. Pertanto, vengono spesso utilizzate per ottenere l'effetto di ereditarietà multipla. Ad esempio, <xref:System.IDisposable> è un'interfaccia che consente ai tipi di supporto disposability indipendente da qualsiasi altra gerarchia di ereditarietà in cui si desidera partecipare.  
  
 L'altro caso in cui la definizione di un'interfaccia è appropriata è durante la creazione di un'interfaccia comune che può essere supportata dai diversi tipi, inclusi alcuni tipi di valore. Tipi di valore non possono ereditare da tipi diversi da <xref:System.ValueType>, ma possono implementare interfacce, pertanto, utilizzando un'interfaccia è l'unica opzione per fornire un tipo di base comune.  
  
 **✓ SI** definire un'interfaccia se è necessario alcune API comuni devono essere supportati da un set di tipi che include i tipi di valore.  
  
 **✓ Provare a** che definisce un'interfaccia se è necessario supportare le funzionalità nei tipi che ereditano già da un altro tipo.  
  
 **X evitare** utilizzano interfacce marcatore (interfacce senza membri).  
  
 Se è necessario contrassegnare una classe come se avessero una caratteristica specifica (indicatore), in generale, utilizzare un attributo personalizzato anziché un'interfaccia.  
  
 **✓ SI** fornire almeno un tipo che è un'implementazione di un'interfaccia.  
  
 Effettuando questa consente di convalidare la progettazione dell'interfaccia. Ad esempio, <xref:System.Collections.Generic.List%601> è un'implementazione del <xref:System.Collections.Generic.IList%601> interfaccia.  
  
 **✓ SI** forniscono almeno una API che utilizza ciascuna interfaccia definita (un metodo che utilizza l'interfaccia come un parametro o una proprietà tipizzato come l'interfaccia).  
  
 Effettuando questa consente di convalidare la progettazione dell'interfaccia. Ad esempio, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> utilizza il <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interfaccia.  
  
 **X non** aggiungere membri a un'interfaccia che è già stata distribuita.  
  
 Questa operazione causa l'interruzione implementazioni dell'interfaccia. Per evitare problemi di controllo delle versioni, è necessario creare una nuova interfaccia.  
  
 Ad eccezione di situazioni descritte in queste linee guida, è consigliabile, in generale, scegliere classi anziché le interfacce nella progettazione di librerie di codice gestito riutilizzabili.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)

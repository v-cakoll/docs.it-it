---
title: Progettazione di interfacce
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
author: KrzysztofCwalina
ms.openlocfilehash: a017b34ab410824e3ddac4365e5711840fb50031
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148730"
---
# <a name="interface-design"></a>Progettazione di interfacce
Sebbene la maggior parte delle API sono meglio modellate utilizzando le classi e struct, vi sono casi in cui le interfacce sono più appropriate oppure sono l'unica opzione.  
  
 CLR non supporta l'ereditarietà multipla (ad esempio, le classi CLR non possono ereditare da più di una classe di base), ma consente i tipi implementare una o più interfacce, oltre che eredita da una classe di base. Pertanto, interfacce vengono spesso usate per ottenere l'effetto dell'ereditarietà multipla. Ad esempio, <xref:System.IDisposable> è un'interfaccia che consente ai tipi di supporto disposability indipendente da qualsiasi altra gerarchia di ereditarietà in cui si desidera partecipare.  
  
 L'altra situazione in cui la definizione di un'interfaccia è appropriata è durante la creazione di un'interfaccia comune che può essere supportata dai diversi tipi, inclusi alcuni tipi di valore. I tipi di valore non possono ereditare da tipi diversi da <xref:System.ValueType>, ma possono implementare interfacce, quindi, usando un'interfaccia è l'unica opzione per fornire un tipo base comune.  
  
 **✓ DO** definire un'interfaccia se è necessario alcune API comuni devono essere supportati da un set di tipi che include i tipi di valore.  
  
 **✓ CONSIDER** che definisce un'interfaccia se è necessario supportare le funzionalità nei tipi che ereditano già da un altro tipo.  
  
 **X AVOID** utilizzano interfacce marcatore (interfacce senza membri).  
  
 Se è necessario contrassegnare una classe come se avessero una caratteristica specifica (indicatore), in generale, usare un attributo personalizzato anziché a un'interfaccia.  
  
 **✓ DO** fornire almeno un tipo che è un'implementazione di un'interfaccia.  
  
 Operazioni di questo monitoraggio consente di convalidare la progettazione dell'interfaccia. Ad esempio, <xref:System.Collections.Generic.List%601> è un'implementazione del <xref:System.Collections.Generic.IList%601> interfaccia.  
  
 **✓ DO** forniscono almeno una API che utilizza ciascuna interfaccia definita (un metodo che utilizza l'interfaccia come un parametro o una proprietà tipizzato come l'interfaccia).  
  
 Operazioni di questo monitoraggio consente di convalidare la progettazione dell'interfaccia. Ad esempio, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> utilizza il <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interfaccia.  
  
 **X DO NOT** aggiungere membri a un'interfaccia che è già stata distribuita.  
  
 Questa operazione causa l'interruzione implementazioni dell'interfaccia. È necessario creare una nuova interfaccia per evitare problemi di controllo delle versioni.  
  
 Fatta eccezione per le situazioni descritte in queste linee guida, è consigliabile, in generale, scegliere classi anziché le interfacce nella progettazione di librerie riutilizzabili di codice gestito.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)  
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)

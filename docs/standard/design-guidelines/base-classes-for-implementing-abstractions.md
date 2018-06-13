---
title: Classi base per l'implementazione di astrazioni
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c247ed7273687dbd61a6f19923b71e07e9ed960
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571508"
---
# <a name="base-classes-for-implementing-abstractions"></a>Classi base per l'implementazione di astrazioni
In teoria, una classe diventa una classe di base quando un'altra classe è derivata da esso. Ai fini di questa sezione, tuttavia, una classe di base è una classe progettata principalmente per fornire un'astrazione comune o per le altre classi di riutilizzare alcuni implementazione predefinita tramite ereditarietà. Classi di base si trovano in genere all'interno di gerarchie di ereditarietà, tra un'astrazione alla radice di una gerarchia e diverse implementazioni personalizzate nella parte inferiore.  
  
 Fungono helper di implementazione per l'implementazione di astrazioni. Ad esempio, una delle astrazioni del Framework per le raccolte ordinate di elementi è il <xref:System.Collections.Generic.IList%601> interfaccia. Implementazione di <xref:System.Collections.Generic.IList%601> non è semplice, e pertanto il Framework fornisce diverse classi di base, ad esempio <xref:System.Collections.ObjectModel.Collection%601> e <xref:System.Collections.ObjectModel.KeyedCollection%602>, che fungono da helper per l'implementazione di raccolte personalizzate.  
  
 Classi di base in genere non sono adatte a fungere da astrazioni di per sé, perché tendono a contenere una quantità eccessiva di implementazione. Ad esempio, il `Collection<T>` classe di base contiene un numero elevato di implementazione relativi al fatto che implementa il metodo non generico `IList` interfaccia (per migliore integrazione con le raccolte non generiche) e al fatto che è una raccolta di elementi archiviati in memoria in uno dei relativi campi.  
  
 Come illustrato in precedenza, le classi di base possono fornire Guida essenziale per gli utenti che devono implementare astrazioni, ma nello stesso momento possono essere significative passività. Aggiungono della superficie di attacco e aumentare la profondità delle gerarchie di ereditarietà e pertanto concettualmente complicare il framework. Pertanto, le classi di base devono essere utilizzate solo se un valore significativo forniscono agli utenti di framework. Essi deve essere evitate se forniscono valore solo per i responsabili dell'implementazione di framework, in cui è necessario considerare fortemente case delega a un'implementazione interna invece dell'ereditarietà da una classe base.  
  
 **✓ Provare a** astratta le classi di base che anche se non contengono alcun membro astratto. Questo chiaramente comunica agli utenti che la classe è progettata esclusivamente per essere ereditata.  
  
 **✓ Provare a** posizionando le classi di base in uno spazio dei nomi separato dai tipi di scenario principale. Per definizione, le classi di base sono destinate a scenari di estensibilità avanzate e pertanto non sono interessanti per la maggior parte degli utenti.  
  
 **X evitare** denominazione delle classi di base con un suffisso "Base" se la classe è destinata all'utilizzo nelle API pubbliche.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)

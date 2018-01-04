---
title: Linee guida per la progettazione di Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 38c344e4f4ede58fcb39dd638f6aa8e896e63da0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="framework-design-guidelines"></a>Linee guida per la progettazione di Framework
In questa sezione vengono fornite linee guida per la progettazione di librerie che estendono e interagiscono con .NET Framework. L'obiettivo è garantire agli sviluppatori di librerie coerenza API e la facilità di utilizzo fornendo un modello di programmazione unificato che sia indipendente dal linguaggio di programmazione utilizzato per lo sviluppo. È consigliabile seguire queste linee guida di progettazione durante lo sviluppo di classi e componenti che estendono .NET Framework. Progettazione di librerie incoerente può influire negativamente sulla produttività degli sviluppatori e sconsiglia adozione.  
  
 Le linee guida sono organizzate come indicazioni semplice con le condizioni di prefisso `Do`, `Consider`, `Avoid`, e `Do not`. Queste linee guida servono per consentire agli sviluppatori di librerie di classe di comprendere i compromessi tra diverse soluzioni. Potrebbero esistere situazioni in cui è necessario che violi queste linee guida di progettazione corretta progettazione delle librerie. Casi devono essere rari ed è importante disporre di un motivo esistano valide per la decisione.  
  
 Queste linee guida sono state estratte dal libro *linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition*, Krzysztof Cwalina e Brad Abrams.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 Vengono fornite linee guida per la denominazione di assembly, spazi dei nomi, tipi e membri nelle librerie di classi.  
  
 [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)  
 Vengono fornite linee guida per l'utilizzo di classi statiche e astratte, interfacce, enumerazioni, strutture e altri tipi.  
  
 [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)  
 Vengono fornite linee guida per la progettazione e utilizzando le proprietà, metodi, costruttori, campi, eventi, operatori e i parametri.  
  
 [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 Vengono illustrati i meccanismi di estendibilità, ad esempio la creazione di sottoclassi, utilizzando gli eventi, i membri virtuali e i callback e viene spiegato come scegliere i meccanismi che meglio soddisfano i requisiti del framework.  
  
 [Linee guida di progettazione delle eccezioni](../../../docs/standard/design-guidelines/exceptions.md)  
 Descrive linee guida di progettazione per la progettazione, generazione e l'intercettazione delle eccezioni.  
  
 [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 Vengono fornite istruzioni per l'utilizzo di tipi comuni, ad esempio matrici, attributi e raccolte che supportano la serializzazione e l'overload degli operatori di uguaglianza.  
  
 [Modelli di progettazione comuni](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 Vengono fornite linee guida per la scelta e l'implementazione delle proprietà di dipendenza e il modello dispose.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica](../../../docs/framework/get-started/overview.md)  
 [Guida di orientamento per .NET Framework](http://msdn.microsoft.com/en-us/0b46b7c6-9163-4f99-8e58-0d1ee7da8c67)  
 [Guida di sviluppo](../../../docs/framework/development-guide.md)

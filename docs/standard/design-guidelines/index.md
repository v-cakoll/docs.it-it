---
title: Linee guida per la progettazione di Framework
titleSuffix: ''
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
ms.openlocfilehash: 5a4edca70844a2b2a3972381b34efe85664f353d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276036"
---
# <a name="framework-design-guidelines"></a>Linee guida per la progettazione di Framework
In questa sezione vengono fornite le linee guida per la progettazione di librerie che estendono e interagiscono con il .NET Framework. L'obiettivo è aiutare i progettisti di librerie a garantire la coerenza e la semplicità di utilizzo dell'API offrendo un modello di programmazione unificato indipendente dal linguaggio di programmazione utilizzato per lo sviluppo. Si consiglia di seguire queste linee guida di progettazione per lo sviluppo di classi e componenti che estendono le .NET Framework. Un progetto di libreria incoerente influisce negativamente sulla produttività degli sviluppatori e sconsiglia l'adozione.  
  
 Le linee guida sono organizzate come semplici raccomandazioni precedute dai termini `Do` ,, `Consider` `Avoid` e `Do not` . Queste linee guida sono progettate per aiutare i progettisti di librerie di classi a comprendere i compromessi tra diverse soluzioni. Potrebbero essere presenti situazioni in cui la progettazione di una libreria corretta richiede la violazione di queste linee guida di progettazione. Questi casi dovrebbero essere rari ed è importante avere un motivo chiaro e interessante per la decisione.  
  
 Queste linee guida sono tratte dalle *linee guida per la progettazione di Book Framework: convenzioni, idiomi e modelli per le librerie .NET riutilizzabili, 2a edizione*, di Krzysztof Cwalina e Brad Abrams.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Linee guida per la denominazione](naming-guidelines.md)  
 Vengono fornite linee guida per la denominazione di assembly, spazi dei nomi, tipi e membri nelle librerie di classi.  
  
 [Linee guida per la progettazione di tipi](type.md)  
 Vengono fornite linee guida per l'utilizzo di classi, interfacce, enumerazioni, strutture e altri tipi statici e astratti.  
  
 [Linee guida per la progettazione di membri](member.md)  
 Vengono fornite linee guida per la progettazione e l'utilizzo di proprietà, metodi, costruttori, campi, eventi, operatori e parametri.  
  
 [Progettazione finalizzata all'estensibilità](designing-for-extensibility.md)  
 Vengono illustrati i meccanismi di estendibilità, ad esempio la sottoclasse, l'utilizzo di eventi, membri virtuali e callback e viene illustrato come scegliere i meccanismi che meglio soddisfano i requisiti del Framework.  
  
 [Linee guida di progettazione delle eccezioni](exceptions.md)  
 Descrive le linee guida di progettazione per la progettazione, la generazione e il rilevamento di eccezioni.  
  
 [Linee guida sull'utilizzo](usage-guidelines.md)  
 Vengono descritte le linee guida per l'utilizzo di tipi comuni come matrici, attributi e raccolte, il supporto della serializzazione e l'overload degli operatori di uguaglianza.  
  
 [Modelli di progettazione comuni](common-design-patterns.md)  
 Vengono fornite linee guida per la scelta e l'implementazione delle proprietà di dipendenza.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica](../../framework/get-started/overview.md)
- [Guida allo sviluppo](../../framework/development-guide.md)

---
title: Linee guida di progettazione dei tipi
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
caps.latest.revision: 13
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 53c7bccd4afb92e6afcaccf4b1c50c41f574fedb
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="type-design-guidelines"></a>Linee guida di progettazione dei tipi
Dal punto di vista di Common Language Runtime, sono disponibili solo due categorie di tipi, tipi di riferimento e tipi di valore, ma ai fini della discussione sulla progettazione di framework, i tipi di verrà diviso in gruppi logici, ognuno con il proprio regole specifiche di progettazione.  
  
 Le classi sono nel caso generale dei tipi di riferimento. Che costituiscono la maggior parte dei tipi nella maggior parte dei Framework. Classi goduto la grande diffusione per il ricco set di funzionalità orientate a oggetti che supportano e applicabilità generale. Classi di base e classi astratte sono gruppi logici speciali correlati all'estendibilità.  
  
 Le interfacce sono tipi che possono essere implementati da entrambi i tipi di riferimento e tipi di valore. In questo modo possono risultare radici di polimorfiche gerarchie di tipi di riferimento e tipi di valore. Inoltre, le interfacce consente di simulare l'ereditarietà multipla, in modo nativo non è supportato da CLR.  
  
 Gli struct sono nel caso generale dei tipi di valore e devono essere riservati per tipi semplici e di piccoli, simili a primitive di linguaggio.  
  
 Le enumerazioni sono un tipo speciale di tipi di valore utilizzato per definire una breve serie di valori, ad esempio giorni della settimana, colori della console e così via.  
  
 Le classi statiche sono tipi deve essere contenitori per i membri statici. In genere utilizzati per fornire collegamenti ad altre operazioni.  
  
 Delegati, eccezioni, gli attributi, matrici e raccolte sono tutti i casi speciali dei tipi di riferimento destinati a utilizzi specifici e linee guida per la progettazione e utilizzo vengono trattate altrove in questo manuale.  
  
 **✓ SI** assicurarsi che ogni tipo è un set ben definito di membri correlati, non solo un insieme di funzionalità non correlati casuale.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Scelta tra classi e struct](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [Progettazione di classi astratte](../../../docs/standard/design-guidelines/abstract-class.md)  
 [Progettazione di classi statiche](../../../docs/standard/design-guidelines/static-class.md)  
 [Progettazione di interfacce](../../../docs/standard/design-guidelines/interface.md)  
 [Progettazione di struct](../../../docs/standard/design-guidelines/struct.md)  
 [Progettazione di enum](../../../docs/standard/design-guidelines/enum.md)  
 [Tipi annidati](../../../docs/standard/design-guidelines/nested-types.md)  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)

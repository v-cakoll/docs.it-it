---
title: Linee guida di progettazione dei tipi
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
author: KrzysztofCwalina
ms.openlocfilehash: 16f2a095f461a406eedbd2b34b0c91d3ac43bbe5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650102"
---
# <a name="type-design-guidelines"></a>Linee guida di progettazione dei tipi
Dalla prospettiva del CLR, sono disponibili solo due categorie di tipi, tipi di riferimento e tipi di valore, ma ai fini di una discussione sulla progettazione di framework, si esegue la divisione tipi in gruppi logici, ciascuno con il proprio regole specifiche di progettazione.  
  
 Le classi sono nel caso generale dei tipi di riferimento. Rendono la maggior parte dei tipi nella maggior parte dei Framework. Le classi goduto la grande diffusione per il ricco set di funzionalità orientate a oggetti che supportano e la loro applicabilità generale. Classi di base e le classi astratte sono gruppi logici speciali correlati all'estendibilità.  
  
 Le interfacce sono tipi che possono essere implementati da entrambi i tipi di riferimento e tipi di valore. Vengono pertanto può essere usato come radici di polimorfiche gerarchie di tipi di riferimento e tipi di valore. Inoltre, le interfacce utilizzabile per simulare l'ereditarietà multipla, che non è supportato da CLR.  
  
 Gli struct sono nel caso generale dei tipi di valore e devono essere riservati per tipi semplici e di piccoli, simili alle primitive di linguaggio.  
  
 Enumerazioni rappresentano un caso speciale di tipi di valore utilizzato per definire set short di valori, ad esempio giorni della settimana, colori della console e così via.  
  
 Le classi statiche sono tipi devono essere contenitori per i membri statici. Vengono comunemente utilizzati per fornire collegamenti ad altre operazioni.  
  
 I delegati, eccezioni, gli attributi, le matrici e raccolte sono tutti i casi speciali di tipi di riferimento destinati a utilizzi specifici e le linee guida per la progettazione e utilizzo vengono trattate altrove in questo manuale.  
  
 **✓ DO** assicurarsi che ogni tipo è un set ben definito di membri correlati, non solo un insieme di funzionalità non correlati casuale.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Scelta tra classi e struct](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [Progettazione di classi astratte](../../../docs/standard/design-guidelines/abstract-class.md)  
 [Progettazione di classi statiche](../../../docs/standard/design-guidelines/static-class.md)  
 [Progettazione di interfacce](../../../docs/standard/design-guidelines/interface.md)  
 [Progettazione di struct](../../../docs/standard/design-guidelines/struct.md)  
 [Progettazione di enum](../../../docs/standard/design-guidelines/enum.md)  
 [Tipi annidati](../../../docs/standard/design-guidelines/nested-types.md)  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)

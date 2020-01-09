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
ms.openlocfilehash: 3e2fe7168bd0029d8f0e8f69a136c9089032973f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709023"
---
# <a name="type-design-guidelines"></a>Linee guida di progettazione dei tipi
Dal punto di vista di CLR, sono disponibili solo due categorie di tipi, ovvero tipi di riferimento e tipi di valore, ma ai fini di una discussione sulla progettazione del Framework, i tipi vengono suddivisi in più gruppi logici, ognuno con regole di progettazione specifiche.  
  
 Le classi sono il caso generale dei tipi di riferimento. Costituiscono la maggior parte dei tipi nella maggior parte dei Framework. Le classi devono avere la popolarità per il set completo di funzionalità orientate a oggetti che supportano e per la loro applicabilità generale. Le classi base e le classi astratte sono gruppi logici speciali correlati all'estendibilità.  
  
 Le interfacce sono tipi che possono essere implementati sia da tipi di riferimento che da tipi di valore. Possono quindi fungere da radici di gerarchie polimorfiche di tipi di riferimento e tipi di valore. Inoltre, è possibile utilizzare le interfacce per simulare l'ereditarietà multipla, che non è supportata in modo nativo da CLR.  
  
 Gli struct sono il caso generale dei tipi di valore e devono essere riservati per tipi semplici e piccoli, simili alle primitive di linguaggio.  
  
 Le enumerazioni sono un caso speciale di tipi valore usati per definire brevi set di valori, ad esempio giorni della settimana, colori della console e così via.  
  
 Le classi statiche sono tipi destinati a essere contenitori per i membri statici. Sono comunemente usati per fornire collegamenti ad altre operazioni.  
  
 I delegati, le eccezioni, gli attributi, le matrici e le raccolte sono casi speciali di tipi di riferimento destinati a utilizzi specifici, mentre le linee guida per la progettazione e l'utilizzo sono illustrate altrove in questo libro.  
  
 **✓ DO** assicurarsi che ogni tipo è un set ben definito di membri correlati, non solo un insieme di funzionalità non correlati casuale.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Scelta tra classi e struct](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [Progettazione di classi astratte](../../../docs/standard/design-guidelines/abstract-class.md)  
 [Progettazione di classi statiche](../../../docs/standard/design-guidelines/static-class.md)  
 [Progettazione di interfacce](../../../docs/standard/design-guidelines/interface.md)  
 [Progettazione di struct](../../../docs/standard/design-guidelines/struct.md)  
 [Progettazione di enum](../../../docs/standard/design-guidelines/enum.md)  
 [Tipi annidati](../../../docs/standard/design-guidelines/nested-types.md)  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)

---
title: Progettazione di classi astratte
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
ms.openlocfilehash: 018dd353024e75e9819f5a97008f2f422ecad291
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739065"
---
# <a name="abstract-class-design"></a>Progettazione di classi astratte

❌ non definiscono costruttori interni pubblici o protetti in tipi astratti.

 I costruttori devono essere pubblici solo se gli utenti dovranno creare istanze del tipo. Poiché non è possibile creare istanze di un tipo astratto, un tipo astratto con un costruttore pubblico non è progettato correttamente e fuorviante per gli utenti.

 ✔️ definire un costruttore protetto o interno in classi astratte.

 Un costruttore protetto è più comune e consente semplicemente alla classe di base di eseguire una propria inizializzazione quando vengono creati sottotipi.

 Un costruttore interno può essere usato per limitare le implementazioni concrete della classe astratta all'assembly che definisce la classe.

 ✔️ forniscono almeno un tipo concreto che eredita da ogni classe astratta distribuita.

 Questa operazione consente di convalidare la progettazione della classe astratta. Ad esempio, <xref:System.IO.FileStream?displayProperty=nameWithType> è un'implementazione della classe <xref:System.IO.Stream?displayProperty=nameWithType> abstract.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)

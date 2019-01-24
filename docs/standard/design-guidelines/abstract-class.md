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
author: KrzysztofCwalina
ms.openlocfilehash: 6eec3bb4575b89c6476e6c3410050c705141777f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550412"
---
# <a name="abstract-class-design"></a>Progettazione di classi astratte
**X DO NOT** definire costruttori interni pubblici o protetti in tipi astratti.  
  
 I costruttori devono essere pubblici solo se gli utenti dovranno creare istanze del tipo. Poiché non è possibile creare istanze di un tipo astratto, un tipo astratto con un costruttore pubblico è correttamente progettato e fuorviante per gli utenti.  
  
 **✓ DO** definiscono un protetto o un costruttore interno per le classi astratte.  
  
 Un costruttore protetto è più comune e consente semplicemente la classe di base eseguire la propria inizializzazione quando vengono creati i sottotipi.  
  
 Un costruttore interno è utilizzabile per limitare le implementazioni concrete della classe astratta per l'assembly che definisce la classe.  
  
 **✓ DO** fornire almeno un tipo concreto che eredita da ogni classe astratta che si effettua la spedizione.  
  
 Operazioni di questo monitoraggio consente di convalidare la struttura della classe astratta. Ad esempio, <xref:System.IO.FileStream?displayProperty=nameWithType> è un'implementazione del <xref:System.IO.Stream?displayProperty=nameWithType> classe astratta.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)

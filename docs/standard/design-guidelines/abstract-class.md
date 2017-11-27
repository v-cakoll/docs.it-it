---
title: Progettazione di classi astratte
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d7b680c3377cbfa40734a57f9408d9487dbf3769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="abstract-class-design"></a>Progettazione di classi astratte
**X non** definire costruttori interni pubblici o protetti in tipi astratti.  
  
 I costruttori devono essere pubblici solo se gli utenti dovranno creare istanze del tipo. Poiché è possibile creare istanze di un tipo astratto, un tipo astratto con costruttore pubblico in modo non corretto è progettato e fuorviante per gli utenti.  
  
 **✓ SI** definire un protetto o un costruttore interno per le classi astratte.  
  
 Un costruttore protetto è più comune e consente semplicemente la classe di base eseguire il proprio inizializzazione quando vengono creati i sottotipi.  
  
 Un costruttore interno può essere utilizzato per limitare le implementazioni concrete della classe astratta per l'assembly che definisce la classe.  
  
 **✓ SI** fornire almeno un tipo concreto che eredita da ogni classe astratta che si effettua la spedizione.  
  
 Effettuando questa consente di convalidare la struttura della classe astratta. Ad esempio, <xref:System.IO.FileStream?displayProperty=nameWithType> è un'implementazione del <xref:System.IO.Stream?displayProperty=nameWithType> classe astratta.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida di progettazione di tipo](../../../docs/standard/design-guidelines/type.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)

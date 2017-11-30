---
title: Progettazione di classi statiche
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 28fe3756a2881e8f746616f8275b505b1a01eada
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="static-class-design"></a>Progettazione di classi statiche
Una classe statica viene definita come una classe che contiene solo membri statici (naturalmente oltre i membri di istanza ereditati dalla <xref:System.Object?displayProperty=nameWithType> e possibilmente un costruttore privato). Alcuni linguaggi forniscono il supporto incorporato per le classi statiche. In c# 2.0 e versioni successive, quando una classe è dichiarata come statico, è astratto sealed e non i membri di istanza possono essere sottoposto a override o dichiarati.  
  
 Le classi statiche sono un compromesso tra progettazione orientata agli oggetti pura e alla semplicità. Comunemente vengono utilizzati per fornire collegamenti ad altre operazioni (ad esempio <xref:System.IO.File?displayProperty=nameWithType>), titolari di metodi di estensione o la funzionalità per i quali è non autorizzato wrapper completa orientata agli oggetti (ad esempio <xref:System.Environment?displayProperty=nameWithType>).  
  
 **✓ SI** usano le classi statiche con cautela.  
  
 Le classi statiche devono essere utilizzate solo come classi di supporto per il framework di base orientata agli oggetti.  
  
 **X non** considerare le classi statiche come un bucket esterno.  
  
 **X non** dichiarare o eseguire l'override di membri di istanza nelle classi statiche.  
  
 **✓ SI** dichiarare le classi statiche come sealed, abstract, e aggiungere un costruttore di istanza privata se il linguaggio di programmazione non dispone di supporto incorporato per le classi statiche.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida di progettazione di tipo](../../../docs/standard/design-guidelines/type.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)

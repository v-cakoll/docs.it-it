---
title: Membri virtuali
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1b7abe1dbeb7f4888dd8ee4001b410cc583935c4
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="virtual-members"></a>Membri virtuali
Membri virtuali possono essere sottoposto a override, modificandone il comportamento della sottoclasse. Sono molto simili ai callback in termini di estensibilità che forniscono, ma sono migliori in termini di prestazioni di esecuzione e il consumo di memoria. Inoltre, i membri virtuali sono più naturali in scenari che richiedono la creazione di un particolare tipo di un tipo esistente (specializzazione).  
  
 I membri virtuali offrono prestazioni migliori rispetto a callback ed eventi, ma non prestazioni migliori rispetto ai metodi non virtuali.  
  
 Lo svantaggio principale dei membri virtuali è che il comportamento di un membro virtuale può essere modificato solo in fase di compilazione. Il comportamento di un callback può essere modificato in fase di esecuzione.  
  
 I membri virtuali, come i callback (e probabilmente altro rispetto ai callback), sono costosi progettare, testare e mantenere poiché qualsiasi chiamata a un membro virtuale può essere sottoposto a override in modi imprevisti e può eseguire codice arbitrario. Inoltre, notevolmente più impegnativo in genere è necessario per definire chiaramente il contratto di membri virtuali, pertanto il costo di progettazione e la loro documentazione è elevato.  
  
 **X non** rendere i membri virtuali a meno che non si dispone di un buon motivo per eseguire questa operazione e di essere a conoscenza di tutti i costi correlati alla progettazione, test e la gestione di membri virtuali.  
  
 I membri virtuali sono meno impensabili in termini di modifiche apportate a tali senza interrompere la compatibilità. Inoltre, sono più lenti rispetto ai membri non virtuali, soprattutto perché le chiamate ai membri virtuali non vengono impostati come inline.  
  
 **✓ Provare a** limitazione estendibilità solo a quelle strettamente necessario.  
  
 **✓ SI** preferire accessibilità protetta accessibilità pubblica per i membri virtuali. I membri pubblici devono fornire extensibility (se richiesto) effettuando la chiamata a un membro virtuale protetta.  
  
 I membri pubblici di una classe devono fornire il set corretto di funzionalità per i consumer diretti di tale classe. I membri virtuali sono progettati per essere sottoposto a override nelle sottoclassi e accessibilità protetta è un ottimo modo per definire l'ambito di tutti i punti di estendibilità virtuale a cui possono essere utilizzati.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)

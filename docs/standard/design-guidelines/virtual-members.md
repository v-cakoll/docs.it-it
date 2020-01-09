---
title: Membri virtuali
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
ms.openlocfilehash: 2c1e6d9aeafa1c9d7ee4b0c2c626b6fd7be6cf99
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708971"
---
# <a name="virtual-members"></a>Membri virtuali
È possibile eseguire l'override dei membri virtuali, modificando in tal modo il comportamento della sottoclasse. Sono molto simili alle richiamate in termini di estendibilità che forniscono, ma sono migliori in termini di prestazioni di esecuzione e di utilizzo della memoria. Inoltre, i membri virtuali si sentono più naturali negli scenari che richiedono la creazione di un tipo speciale di un tipo esistente (specializzazione).  
  
 I membri virtuali offrono prestazioni migliori rispetto a callback ed eventi, ma non offrono prestazioni migliori rispetto ai metodi non virtuali.  
  
 Lo svantaggio principale dei membri virtuali è che il comportamento di un membro virtuale può essere modificato solo al momento della compilazione. Il comportamento di un callback può essere modificato in fase di esecuzione.  
  
 I membri virtuali, ad esempio i callback (e forse più di callback), sono costosi da progettare, testare e gestire perché qualsiasi chiamata a un membro virtuale può essere sottoposta a override in modi imprevedibili ed è in grado di eseguire codice arbitrario. Inoltre, la maggior parte degli sforzi è in genere necessaria per definire chiaramente il contratto dei membri virtuali, quindi il costo della progettazione e della relativa documentazione è superiore.  
  
 **X DO NOT** rendere i membri virtuali a meno che non si dispone di un buon motivo per eseguire questa operazione e di essere a conoscenza di tutti i costi correlati alla progettazione, test e la gestione di membri virtuali.  
  
 I membri virtuali sono meno indulgenti in termini di modifiche che possono essere apportate senza interruzioni della compatibilità. Sono inoltre più lenti dei membri non virtuali, soprattutto perché le chiamate a membri virtuali non sono inline.  
  
 **✓ CONSIDER** limitazione estendibilità solo a quelle strettamente necessario.  
  
 **✓ DO** preferire accessibilità protetta accessibilità pubblica per i membri virtuali. I membri pubblici devono fornire estensibilità (se necessario) chiamando un membro virtuale protetto.  
  
 I membri pubblici di una classe devono fornire il set corretto di funzionalità per i consumer diretti di tale classe. I membri virtuali sono progettati per essere sottoposti a override nelle sottoclassi e l'accessibilità protetta è un ottimo modo per definire l'ambito di tutti i punti di estendibilità virtuali in cui possono essere usati.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)

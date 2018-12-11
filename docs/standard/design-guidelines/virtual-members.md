---
title: Membri virtuali
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
author: KrzysztofCwalina
ms.openlocfilehash: 1719e9843252c25d1e799471330c6cb08211245b
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128927"
---
# <a name="virtual-members"></a>Membri virtuali
Membri virtuali possono essere sottoposto a override, in modo da modificarne il comportamento della sottoclasse. Sono molto simili ai callback in termini di estensibilità che forniscono, ma sono migliori in termini di prestazioni di esecuzione e il consumo di memoria. Inoltre, i membri virtuali sembrano più naturali negli scenari che richiedono la creazione di uno speciale tipo di un tipo esistente (specializzazione).  
  
 Membri virtuali offrono prestazioni migliori rispetto a callback ed eventi, ma non offrono prestazioni migliori rispetto ai metodi non virtuali.  
  
 Lo svantaggio principale di membri virtuali è che il comportamento di un membro virtuale può essere modificato solo al momento della compilazione. Il comportamento di un callback può essere modificato in fase di esecuzione.  
  
 Membri virtuali, ad esempio i callback e forse più di callback, sono anche costosi da progettare, testare e gestire perché tutte le chiamate a un membro virtuale possono essere sottoposto a override in modo imprevedibile e possono eseguire codice arbitrario. È inoltre molto più complessa è generalmente necessaria per definire chiaramente il contratto dei membri virtuali, in modo che il costo di progettazione e la documentazione di essi è elevato.  
  
 **X DO NOT** rendere i membri virtuali a meno che non si dispone di un buon motivo per eseguire questa operazione e di essere a conoscenza di tutti i costi correlati alla progettazione, test e la gestione di membri virtuali.  
  
 Membri virtuali sono meno tollerante in termini di modifiche che possono essere eseguite a loro senza compromettere la compatibilità. Inoltre, sono più lenti rispetto a membri non virtuale, principalmente perché le chiamate a membri virtuali non vengono impostati come inline.  
  
 **✓ CONSIDER** limitazione estendibilità solo a quelle strettamente necessario.  
  
 **✓ DO** preferire accessibilità protetta accessibilità pubblica per i membri virtuali. I membri pubblici devono fornire estendibilità (se richiesto) effettuando la chiamata a un membro virtuale protetta.  
  
 I membri pubblici di una classe devono fornire il set corretto di funzionalità per i consumer diretti di tale classe. Membri virtuali sono progettati per essere sottoposto a override nelle sottoclassi e accessibilità protetta è un ottimo modo per definire l'ambito di tutti i punti di estendibilità virtuale a cui potranno essere utilizzati.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)

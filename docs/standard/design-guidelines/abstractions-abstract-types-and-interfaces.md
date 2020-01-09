---
title: Astrazioni (interfacce e tipi astratti)
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
ms.openlocfilehash: 014144764609c8a7faa87f3d080900824f9189eb
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709582"
---
# <a name="abstractions-abstract-types-and-interfaces"></a>Astrazioni (interfacce e tipi astratti)
Un'astrazione è un tipo che descrive un contratto ma non fornisce un'implementazione completa del contratto. Le astrazioni vengono in genere implementate come classi o interfacce astratte e presentano un set ben definito di documentazione di riferimento che descrive la semantica necessaria dei tipi che implementano il contratto. Alcune delle astrazioni più importanti nel .NET Framework includono <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>e <xref:System.Object>.  
  
 È possibile estendere i Framework implementando un tipo concreto che supporta il contratto di un'astrazione e utilizzando questo tipo concreto con le API del Framework che utilizzano (operando) l'astrazione.  
  
 Un'astrazione significativa e utile che è in grado di resistere al test del tempo è molto difficile da progettare. La difficoltà principale è ottenere il set corretto di membri, non più e non meno. Se un'astrazione ha troppi membri, diventa difficile o addirittura impossibile da implementare. Se dispone di un numero troppo basso di membri per la funzionalità promessa, diventa inutile in molti scenari interessanti.  
  
 Troppe astrazioni in un Framework influiscono negativamente sull'usabilità del Framework. Spesso è piuttosto difficile comprendere un'astrazione senza capire come si inserisce nel quadro più ampio delle implementazioni concrete e delle API che operano sull'astrazione. Inoltre, i nomi delle astrazioni e i relativi membri sono necessariamente astratti, che spesso li rendono enigmatici e non accessibili senza prima capire il contesto più ampio del loro utilizzo.  
  
 Tuttavia, le astrazioni forniscono un'estendibilità estremamente potente che gli altri meccanismi di estendibilità spesso non corrispondono. Sono alla base di molti modelli di architettura, come plug-in, inversione del controllo (IoC), pipeline e così via. Sono inoltre estremamente importanti per la testabilità dei Framework. Le astrazioni corrette consentono di eseguire lo stub di dipendenze pesanti allo scopo di eseguire unit test. In sintesi, le astrazioni sono responsabili della ricchezza ricercata dei moderni Framework orientati agli oggetti.  
  
 **X DO NOT** forniscono astrazioni a meno che non vengono verificati per lo sviluppo di diverse implementazioni concrete e utilizzano le astrazioni di API.  
  
 **✓ DO** scegliere con attenzione tra una classe astratta e un'interfaccia quando si progetta un'astrazione.  
  
 **✓ CONSIDER** fornendo i test di riferimento per le implementazioni concrete di astrazioni. Tali test devono consentire agli utenti di verificare se le implementazioni implementano correttamente il contratto.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)

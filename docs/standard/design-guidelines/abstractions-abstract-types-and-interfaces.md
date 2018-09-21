---
title: Astrazioni (interfacce e tipi astratti)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ad8b2dd3dbf2a7a75c98a3115d4351dfea4e1a0
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2018
ms.locfileid: "46480682"
---
# <a name="abstractions-abstract-types-and-interfaces"></a>Astrazioni (interfacce e tipi astratti)
Un'astrazione è un tipo che descrive un contratto, ma non fornisce un'implementazione completa del contratto. Astrazioni sono in genere implementate come classi astratte o interfacce e diventano un set ben definito di documentazione di riferimento che descrive la semantica dei tipi che implementa il contratto richiesta. Alcune delle astrazioni più importanti in .NET Framework includono <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, e <xref:System.Object>.  
  
 È possibile estendere Framework implementa un tipo concreto che supporta il contratto di un'astrazione e utilizzando questo tipo concreto con framework API consumer (che viene applicato) l'astrazione.  
  
 È molto difficile progettare un'astrazione significativa e utile che è in grado di resistere alla prova di tempo. La difficoltà principale è ottenere il set corretto di membri, non è più e non un numero inferiore. Se un'astrazione ha troppi membri, diventa difficile o persino impossibile da implementare. Se è presente un numero troppo ridotto i membri per il funzionamento della promesso, diventa inutile in molti scenari interessanti.  
  
 Troppi astrazioni in un framework anche influire negativamente sull'usabilità del framework. È spesso piuttosto difficile da comprendere un'astrazione senza informazioni sulle modalità di integrazione in immagine più ampia delle implementazioni concrete e le API che viene applicato l'astrazione. Inoltre, i nomi di astrazioni e i relativi membri sono necessariamente astratti, che spesso li rende enigmatici e riducendone senza prima le informazioni sul contesto più ampio del loro utilizzo.  
  
 Tuttavia, astrazioni forniscono estensibilità estremamente potente che spesso non possono corrispondere a altri meccanismi di estendibilità. Sono alla base di molti schemi architetturali, ad esempio plug-in, inversione di controllo (IoC), le pipeline e così via. Sono anche estremamente importante per la verificabilità del Framework. Astrazioni buona rendono possibile sottoporre a stub out pesante dipendenze allo scopo di unit test. In breve, le astrazioni sono tenute alle molteplici funzionalità più attese dei framework moderno e orientato.  
  
 **X DO NOT** forniscono astrazioni a meno che non vengono verificati per lo sviluppo di diverse implementazioni concrete e utilizzano le astrazioni di API.  
  
 **✓ DO** scegliere con attenzione tra una classe astratta e un'interfaccia quando si progetta un'astrazione.  
  
 **✓ CONSIDER** fornendo i test di riferimento per le implementazioni concrete di astrazioni. Questi test dovrebbero consentire agli utenti di verificare la corretta implementazione del contratto.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)

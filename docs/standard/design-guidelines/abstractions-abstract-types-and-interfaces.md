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
ms.openlocfilehash: f5863b4ae9cad940e4dd47ef93e07763916427f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="abstractions-abstract-types-and-interfaces"></a>Astrazioni (interfacce e tipi astratti)
Un'astrazione è un tipo che descrive un contratto, ma non fornisce un'implementazione completa del contratto. Astrazioni sono in genere implementate come classi astratte o interfacce, e hanno un set ben definito della documentazione di riferimento che descrive la semantica dei tipi che implementa il contratto richiesta. Le astrazioni più importanti in .NET Framework includono <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, e <xref:System.Object>.  
  
 È possibile estendere Framework implementando un tipo concreto che supporta il contratto di astrazione e utilizzo di questo tipo concreto con framework API consumer (eseguito) l'astrazione.  
  
 Un'astrazione utile e significativa che è in grado di resistere il test di tempo è molto difficile da progettare. La difficoltà principale sta per diventare il set corretto di membri, non sono più presenti e non un numero inferiore. Se un'astrazione ha troppi membri, diventa difficili o impossibili da implementare. Se dispone di membri insufficienti per la funzionalità promesso, diventa inutilizzabile in molti scenari interessanti.  
  
 Troppi astrazioni in un framework anche influire negativamente sull'usabilità del framework. È spesso molto difficile da comprendere un'astrazione senza conoscere come si inserisca nell'immagine più grande di API che viene applicato l'astrazione e le implementazioni concrete. Inoltre, i nomi di astrazioni e i relativi membri sono necessariamente astratti che spesso rende difficile e inaccessibile senza prima conoscere il contesto più ampio del loro utilizzo.  
  
 Tuttavia, astrazioni forniscono estensibilità estremamente efficaci che spesso non possono corrispondere a altri meccanismi di estensibilità. Sono alla base di molti modelli di architettura, ad esempio plug-in, inversione di controllo (IoC), le pipeline e così via. Sono inoltre estremamente importante per la testabilità del Framework. Buona astrazioni rendono possibile sottoporre a stub pesante dipendenze allo scopo di unit test. In breve, le astrazioni sono responsabili per la ricchezza dei framework orientata agli oggetti moderno ricercata.  
  
 **X non** forniscono astrazioni a meno che non vengono verificati per lo sviluppo di diverse implementazioni concrete e utilizzano le astrazioni di API.  
  
 **✓ SI** scegliere con attenzione tra una classe astratta e un'interfaccia quando si progetta un'astrazione.  
  
 **✓ Provare a** fornendo i test di riferimento per le implementazioni concrete di astrazioni. Tali test dovrebbero consentire agli utenti di verificare la corretta implementazione del contratto.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)

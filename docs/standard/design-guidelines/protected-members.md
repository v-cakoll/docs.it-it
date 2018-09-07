---
title: Membri protetti
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4574dffc3f9dd1b60d655bfde33a4ddc1a81d350
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44068976"
---
# <a name="protected-members"></a>Membri protetti
Membri protetti da soli non forniscono alcun estendibilità, ma estendibilità tramite la creazione di sottoclassi può rendere più potenti. Possono essere utilizzati per esporre le opzioni di personalizzazione avanzate senza complicare inutilmente l'interfaccia pubblica principale.  
  
 Le finestre di progettazione di Framework necessario prestare attenzione con i membri protetti perché il nome "protetto" può dare un senso di protezione fasullo. Chiunque sia in grado di sottoclasse di una classe non sealed e protetta con accesso membri e quindi le stesse procedure di codifica difensive utilizzate per i membri pubblici applicano ai membri protetti.  
  
 **✓ CONSIDER** utilizzando membri per la personalizzazione avanzata protetti.  
  
 **✓ DO** trattare i membri protetti nelle classi non sealed come public allo scopo di analisi di sicurezza, documentazione e compatibilità.  
  
 Chiunque può ereditare da una classe e accedere ai membri protetti.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)

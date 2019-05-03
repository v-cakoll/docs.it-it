---
title: Membri protetti
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: KrzysztofCwalina
ms.openlocfilehash: 7d940f10799df2efc6c6d031781e1ef7cf777dd6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937397"
---
# <a name="protected-members"></a>Membri protetti
Membri protetti da soli non forniscono alcun estendibilità, ma estendibilità tramite la creazione di sottoclassi può rendere più potenti. Possono essere utilizzati per esporre le opzioni di personalizzazione avanzate senza complicare inutilmente l'interfaccia pubblica principale.  
  
 Le finestre di progettazione di Framework necessario prestare attenzione con i membri protetti perché il nome "protetto" può dare un senso di protezione fasullo. Chiunque sia in grado di sottoclasse di una classe non sealed e protetta con accesso membri e quindi le stesse procedure di codifica difensive utilizzate per i membri pubblici applicano ai membri protetti.  
  
 **✓ CONSIDER** utilizzando membri per la personalizzazione avanzata protetti.  
  
 **✓ DO** trattare i membri protetti nelle classi non sealed come public allo scopo di analisi di sicurezza, documentazione e compatibilità.  
  
 Chiunque può ereditare da una classe e accedere ai membri protetti.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)

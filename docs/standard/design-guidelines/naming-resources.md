---
title: Denominazione di risorse
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7cfda4e6a340d040de02903b9b64f0339751c5c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="naming-resources"></a>Denominazione di risorse
Poiché possono fare riferimento a risorse localizzabili mediante determinati oggetti come se fossero proprietà, convenzioni di denominazione per le risorse sono simili alle linee guida di proprietà.  
  
 **✓ SI** utilizzare il sistema Pascal le chiavi di risorsa.  
  
 **✓ SI** forniscono descrittivo anziché identificatori breve.  
  
 **X non** utilizzare parole chiave specifiche della lingua dei linguaggi CLR principale.  
  
 **✓ SI** utilizzare solo caratteri alfanumerici e caratteri di sottolineatura nei nomi delle risorse.  
  
 **✓ SI** utilizzare la seguente convenzione di denominazione per le risorse di messaggio eccezione.  
  
 L'identificatore di risorsa deve essere il nome del tipo di eccezione e un identificatore breve dell'eccezione:  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)

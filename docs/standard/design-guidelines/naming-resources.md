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
ms.openlocfilehash: a5b53fc383e6fc9a5f056bab4eabde9979cd734b
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43875109"
---
# <a name="naming-resources"></a>Denominazione di risorse
Poiché possono fare riferimento a risorse localizzabili tramite determinati oggetti come se fossero proprietà, convenzioni di denominazione per le risorse sono simili alle linee guida per la proprietà.  
  
 **✓ DO** utilizzare il sistema Pascal le chiavi di risorsa.  
  
 **✓ DO** forniscono descrittivo anziché identificatori breve.  
  
 **X DO NOT** utilizzare parole chiave specifiche della lingua dei linguaggi CLR principale.  
  
 **✓ DO** utilizzare solo caratteri alfanumerici e caratteri di sottolineatura nei nomi delle risorse.  
  
 **✓ DO** utilizzare la seguente convenzione di denominazione per le risorse di messaggio eccezione.  
  
 L'identificatore della risorsa deve essere il nome del tipo di eccezione e un identificatore breve dell'eccezione:  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)

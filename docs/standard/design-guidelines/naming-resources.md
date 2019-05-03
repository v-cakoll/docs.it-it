---
title: Denominazione di risorse
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
author: KrzysztofCwalina
ms.openlocfilehash: 44627aafd9ec779625413a0862412a8f6c408109
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756884"
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
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)

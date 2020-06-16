---
title: Denominazione di risorse
description: Esaminare le linee guida per la denominazione delle risorse in .NET, che sono simili alle linee guida per la denominazione delle proprietà.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: 765337bcf9fad4f9a8c9272a15b5c77d02770471
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768248"
---
# <a name="naming-resources"></a>Denominazione di risorse
Poiché è possibile fare riferimento alle risorse localizzabili tramite determinati oggetti come se fossero proprietà, le linee guida per la denominazione delle risorse sono simili alle linee guida della proprietà.

 ✔️ utilizzare sistema Pascal nelle chiavi di risorsa.

 ✔️ forniscono identificatori descrittivi anziché brevi.

 ❌Non usare parole chiave specifiche del linguaggio dei linguaggi CLR principali.

 ✔️ utilizzano solo caratteri alfanumerici e caratteri di sottolineatura nelle risorse di denominazione.

 ✔️ utilizzare la convenzione di denominazione seguente per le risorse dei messaggi di eccezione.

 L'identificatore di risorsa deve essere il nome del tipo di eccezione più un identificatore breve dell'eccezione:

 `ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`
 `ArgumentExceptionFileNameIsMalformed`

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](index.md)
- [Linee guida per la denominazione](naming-guidelines.md)

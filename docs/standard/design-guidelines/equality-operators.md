---
title: Operatori di uguaglianza
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: bd36b98af25db2921c164ac359188997d379a270
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280050"
---
# <a name="equality-operators"></a>Operatori di uguaglianza
In questa sezione viene illustrato l'overload degli operatori di uguaglianza e si fa riferimento a `operator==` e `operator!=` come operatori di uguaglianza.

 ❌Non eseguire l'overload di uno degli operatori di uguaglianza e non dell'altro.

 ✔️ Assicurarsi che <xref:System.Object.Equals%2A?displayProperty=nameWithType> e gli operatori di uguaglianza abbiano esattamente la stessa semantica e caratteristiche di prestazioni simili.

 Questo significa spesso che `Object.Equals` deve essere sottoposto a override quando gli operatori di uguaglianza sono sottoposti a overload.

 ❌EVITARE di generare eccezioni dagli operatori di uguaglianza.

 Ad esempio, restituisce false se uno degli argomenti è null anziché generare `NullReferenceException` .

## <a name="equality-operators-on-value-types"></a>Operatori di uguaglianza sui tipi di valore
 ✔️ ESEGUONO l'overload degli operatori di uguaglianza sui tipi di valore, se l'uguaglianza è significativa.

 Nella maggior parte dei linguaggi di programmazione non è disponibile un'implementazione predefinita di `operator==` per i tipi di valore.

## <a name="equality-operators-on-reference-types"></a>Operatori di uguaglianza sui tipi di riferimento
 ❌EVITARE l'overload degli operatori di uguaglianza sui tipi di riferimento modificabili.

 Molti linguaggi hanno operatori di uguaglianza predefiniti per i tipi di riferimento. Gli operatori incorporati in genere implementano l'uguaglianza dei riferimenti e molti sviluppatori sono sorpresi quando il comportamento predefinito viene modificato nell'uguaglianza dei valori.

 Questo problema è mitigato per i tipi di riferimento non modificabili perché l'immutabilità rende molto più difficile notare la differenza tra uguaglianza dei riferimenti e uguaglianza dei valori.

 ❌EVITARE l'overload degli operatori di uguaglianza sui tipi di riferimento se l'implementazione è significativamente più lenta rispetto a quella dell'uguaglianza dei riferimenti.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](index.md)
- [Linee guida sull'utilizzo](usage-guidelines.md)

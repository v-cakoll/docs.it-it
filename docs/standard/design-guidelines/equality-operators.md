---
title: Operatori di uguaglianza
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
caps.latest.revision: 13
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cd740e9b7a5d38229b3564bfeca003fc4d189624
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="equality-operators"></a>Operatori di uguaglianza
In questa sezione illustra l'overload degli operatori di uguaglianza e fa riferimento a `operator==` e `operator!=` come operatori di uguaglianza.  
  
 **X non** overload degli operatori di uguaglianza e non in altro.  
  
 **✓ SI** assicurarsi che <xref:System.Object.Equals%2A?displayProperty=nameWithType> e gli operatori di uguaglianza hanno esattamente la stessa semantica e caratteristiche di prestazioni simili.  
  
 Ciò significa che spesso `Object.Equals` deve essere sottoposto a override quando sono sottoposti a overload gli operatori di uguaglianza.  
  
 **X evitare** generazione di eccezioni da operatori di uguaglianza.  
  
 Ad esempio, restituisce false se uno degli argomenti è null anziché generare `NullReferenceException`.  
  
## <a name="equality-operators-on-value-types"></a>Operatori di uguaglianza sui tipi di valore  
 **✓ SI** eseguire l'overload degli operatori di uguaglianza sui tipi di valore, se l'uguaglianza è significativo.  
  
 La maggior parte dei linguaggi di programmazione, non vi è Nessuna implementazione predefinita di `operator==` per i tipi di valore.  
  
## <a name="equality-operators-on-reference-types"></a>Operatori di uguaglianza sui tipi di riferimento  
 **X evitare** overload degli operatori di uguaglianza sui tipi di riferimento modificabile.  
  
 Molte lingue hanno operatori di uguaglianza predefinito per i tipi di riferimento. Gli operatori incorporati in genere implementano l'uguaglianza di riferimento e molti sviluppatori sono testati quando viene modificato il comportamento predefinito per l'uguaglianza di valore.  
  
 Questo problema viene ridotta per i tipi di riferimento non modificabile in quanto rende molto più difficile da notare la differenza tra uguaglianza di riferimento e uguaglianza immutabilità.  
  
 **X evitare** overload degli operatori di uguaglianza sui tipi di riferimento se l'implementazione sarebbe notevolmente più lento rispetto a quello di uguaglianza di riferimento.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)

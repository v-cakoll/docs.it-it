---
title: Thread safety nelle espressioni regolari
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework regular expressions, threads
- regular expressions, threads
- searching with regular expressions, threads
- parsing text with regular expressions, threads
- pattern-matching with regular expressions, threads
ms.assetid: 7c4a167b-5236-4cde-a2ca-58646230730f
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b4cfa24da8083eac01275ad76f5c2db974b39a25
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="thread-safety-in-regular-expressions"></a>Thread safety nelle espressioni regolari
La <xref:System.Text.RegularExpressions.Regex> classe stessa è thread-safe e non modificabile (sola lettura). Ciò significa che è possibile creare oggetti **Regex** in qualsiasi thread e condividerli fra i thread; i metodi corrispondenti possono essere chiamati da qualsiasi thread e non modificano in nessun caso uno stato globale.  
  
 Tuttavia, gli oggetti di risultato (**corrispondenza** e **MatchCollection**) restituito da **Regex** deve essere usato su un singolo thread. Sebbene molti di questi oggetti non siano modificabili a livello logico, le loro implementazioni potrebbero ritardare l'elaborazione di determinati risultati per migliorare le prestazioni; di conseguenza, i chiamanti dovranno serializzare l'accesso a tali oggetti.  
  
 Se risulta necessario condividere oggetti risultato **Regex** su più thread, tali oggetti possono essere convertiti in istanze thread-safe chiamando i relativi metodi sincronizzati. Fatta eccezione per gli enumeratori, tutte le classi di espressioni regolari sono thread-safe o possono essere convertite in oggetti thread-safe mediante un metodo sincronizzato.  
  
 L'unica eccezione è costituita dagli enumeratori. Un'applicazione deve serializzare le chiamate agli enumeratori di raccolta. La regola indica che se una raccolta può essere enumerata in più thread contemporaneamente, è necessario sincronizzare i metodi di enumeratore sull'oggetto radice della raccolta attraversata dall'enumeratore.  
  
## <a name="see-also"></a>Vedere anche  
 [Espressioni regolari di .NET](../../../docs/standard/base-types/regular-expressions.md)

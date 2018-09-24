---
title: Thread safety nelle espressioni regolari
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET Framework regular expressions, threads
- regular expressions, threads
- searching with regular expressions, threads
- parsing text with regular expressions, threads
- pattern-matching with regular expressions, threads
ms.assetid: 7c4a167b-5236-4cde-a2ca-58646230730f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c0bcab0757bc48f6a8216dd5878f0289e49a275
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46537371"
---
# <a name="thread-safety-in-regular-expressions"></a>Thread safety nelle espressioni regolari
La classe <xref:System.Text.RegularExpressions.Regex> è thread-safe e non modificabile (di sola lettura). Ciò significa che è possibile creare oggetti **Regex** in qualsiasi thread e condividerli fra i thread; i metodi corrispondenti possono essere chiamati da qualsiasi thread e non modificano in nessun caso uno stato globale.  
  
 Tuttavia, gli oggetti risultato (**Match** e **MatchCollection)** restituiti da **Regex** vanno usati in un unico thread. Sebbene molti di questi oggetti non siano modificabili a livello logico, le loro implementazioni potrebbero ritardare l'elaborazione di determinati risultati per migliorare le prestazioni; di conseguenza, i chiamanti dovranno serializzare l'accesso a tali oggetti.  
  
 Se risulta necessario condividere oggetti risultato **Regex** su più thread, tali oggetti possono essere convertiti in istanze thread-safe chiamando i relativi metodi sincronizzati. Fatta eccezione per gli enumeratori, tutte le classi di espressioni regolari sono thread-safe o possono essere convertite in oggetti thread-safe mediante un metodo sincronizzato.  
  
 L'unica eccezione è costituita dagli enumeratori. Un'applicazione deve serializzare le chiamate agli enumeratori di raccolta. La regola indica che se una raccolta può essere enumerata in più thread contemporaneamente, è necessario sincronizzare i metodi di enumeratore sull'oggetto radice della raccolta attraversata dall'enumeratore.  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni regolari .NET](../../../docs/standard/base-types/regular-expressions.md)

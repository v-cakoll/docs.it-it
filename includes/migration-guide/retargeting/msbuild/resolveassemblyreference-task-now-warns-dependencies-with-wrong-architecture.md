---
ms.openlocfilehash: 4d410811095786b33580d25f6c6eab3ac2f27148
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616105"
---
### <a name="resolveassemblyreference-task-now-warns-of-dependencies-with-the-wrong-architecture"></a>L'attiva ResolveAssemblyReference genera ora avvisi in caso di dipendenze con l'architettura non corretta

#### <a name="details"></a>Dettagli

L'attività genera un avviso, MSB3270, che indica la mancata corrispondenza di un riferimento o di una delle sue dipendenze all'architettura dell'app. Questa situazione si verifica ad esempio se un'app compilata con l'opzione `AnyCPU` include un riferimento x86. Uno scenario di questo tipo potrebbe provocare un errore dell'app in fase di esecuzione (nel caso descritto, se l'app viene distribuita come processo x64).

#### <a name="suggestion"></a>Suggerimento

Le possibili conseguenze riguardano le aree seguenti:

- La ricompilazione genera avvisi che non venivano visualizzati quando l'app veniva compilata con una versione precedente di MSBuild. Tuttavia, dal momento che l'avviso identifica una possibile fonte di errore di runtime, deve essere analizzato e affrontato.
- Se gli avvisi vengono considerati errori, la compilazione dell'app non verrà completata.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.5.1       |
| Type    | Ridestinazione |

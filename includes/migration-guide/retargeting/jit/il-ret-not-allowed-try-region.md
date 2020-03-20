---
ms.openlocfilehash: 1687b1b9a1a6861f9569a0e29426de7f32ffc32b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804411"
---
### <a name="il-ret-not-allowed-in-a-try-region"></a>Istruzione IL ret non consentita in un'area try

|   |   |
|---|---|
|Dettagli|A differenza del compilatore JIT JIT64, RyuJIT (usato in .NET Framework 4.6) non consente un'istruzione IL ret in un'area try. La restituzione da un'area try non è consentita dalla specifica ECMA-335 e nessun compilatore gestito noto genera tale IL. Tuttavia, il compilatore JIT64 eseguirà tale livello di integrità se viene generato tramite reflection emit.|
|Suggerimento|Se un'app genera IL che include un codice operativo ret in un'area try, è possibile destinare l'app a .NET Framework 4.5 per usare il compilatore JIT precedente ed evitare l'interruzione. In alternativa, l'IL generato può essere aggiornato per restituire il controllo dopo l'area try.|
|Scope|Microsoft Edge|
|Versione|4.6|
|Type|Ridestinazione|

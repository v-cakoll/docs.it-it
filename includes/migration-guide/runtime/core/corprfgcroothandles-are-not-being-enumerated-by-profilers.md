---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858570"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a>Gli COR_PRF_GC_ROOT_HANDLE non vengono enumerati dai profiler

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5.1, l'API di profilatura <code>RootReferences2()</code> non restituisce mai <code>COR_PRF_GC_ROOT_HANDLE</code> erroneamente (vengono invece restituiti come <code>COR_PRF_GC_ROOT_OTHER</code>). Questo problema è risolto a partire da .NET Framework 4.6.|
|Suggerimento|Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.|
|Scope|Minorenne|
|Versione|4.5.1|
|Type|Runtime|

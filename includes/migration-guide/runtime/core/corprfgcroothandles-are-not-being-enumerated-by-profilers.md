---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235455"
---
### <a name="corprfgcroothandles-are-not-being-enumerated-by-profilers"></a>Gli COR_PRF_GC_ROOT_HANDLE non vengono enumerati dai profiler

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5.1, l'API di profilatura <code>RootReferences2()</code> non restituisce mai <code>COR_PRF_GC_ROOT_HANDLE</code> erroneamente (vengono invece restituiti come <code>COR_PRF_GC_ROOT_OTHER</code>). Questo problema è risolto a partire da .NET Framework 4.6.|
|Suggerimento|Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.|
|Ambito|Secondario|
|Versione|4.5.1|
|Tipo|Runtime|

---
ms.openlocfilehash: 4f52535e54607cc824500f9c6a14964a1dec9d32
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620211"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a>Gli COR_PRF_GC_ROOT_HANDLE non vengono enumerati dai profiler

#### <a name="details"></a>Dettagli

In .NET Framework 4.5.1, l'API di profilatura <code>RootReferences2()</code> non restituisce mai <code>COR_PRF_GC_ROOT_HANDLE</code> erroneamente (vengono invece restituiti come <code>COR_PRF_GC_ROOT_OTHER</code>). Questo problema è risolto a partire da .NET Framework 4.6.

#### <a name="suggestion"></a>Suggerimento

Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5.1|
|Type|Runtime|

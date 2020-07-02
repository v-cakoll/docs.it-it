---
ms.openlocfilehash: 2e13268d4983af5d2fdd6d12b4d9e67d61d07f3d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622032"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a>La profilatura delle app ASP.Net MVC4 può causare un errore irreversibile del motore di esecuzione

#### <a name="details"></a>Dettagli

I profiler che usano gli assembly NGEN /Profile potrebbero causare arresti anomali delle applicazioni ASP.NET MVC4 profilate all'avvio con una 'eccezione irreversibile del motore di esecuzione'

#### <a name="suggestion"></a>Suggerimento

Questo problema è risolto in .NET Framework 4.5.2. In alternativa, il profiler può evitare questo problema specificando <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> nella maschera dell'evento.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime|

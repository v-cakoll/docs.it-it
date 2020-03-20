---
ms.openlocfilehash: 439a4976482639cd2e4e17315ec1a53ca54aa477
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803278"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a>La profilatura delle app ASP.Net MVC4 può causare un errore irreversibile del motore di esecuzione

|   |   |
|---|---|
|Dettagli|I profiler che usano gli assembly NGEN /Profile potrebbero causare arresti anomali delle applicazioni ASP.NET MVC4 profilate all'avvio con una 'eccezione irreversibile del motore di esecuzione'|
|Suggerimento|Questo problema è risolto in .NET Framework 4.5.2. In alternativa, il profiler può evitare questo problema specificando <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> nella maschera dell'evento.|
|Scope|Microsoft Edge|
|Versione|4.5|
|Type|Runtime|

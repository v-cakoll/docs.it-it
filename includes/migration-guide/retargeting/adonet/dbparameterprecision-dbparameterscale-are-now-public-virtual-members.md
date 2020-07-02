---
ms.openlocfilehash: 063e10b0310880af255793215a80a5529a5db0ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616106"
---
### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>DbParameter.Precision e DbParameter.Scale sono ora membri virtuali pubblici

#### <a name="details"></a>Dettagli

<xref:System.Data.Common.DbParameter.Precision> e <xref:System.Data.Common.DbParameter.Scale> sono implementati come proprietà virtuali pubbliche. Sostituiscono le corrispondenti implementazioni esplicite dell'interfaccia, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> e <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.

#### <a name="suggestion"></a>Suggerimento

Quando si ricompila un provider di database ADO.NET, queste differenze richiederanno l'applicazione della parola chiave 'override' alle proprietà Precision e Scale. Questo è necessario solo quando si ricompilano i componenti. I file binari esistenti continueranno a funzionare.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.5.1       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType>
- <xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType>

---
ms.openlocfilehash: 1721d32f8cdc9b6ea4b4732e38afa56a8a532600
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59234729"
---
### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>DbParameter.Precision e DbParameter.Scale sono ora membri virtuali pubblici

|   |   |
|---|---|
|Dettagli|<xref:System.Data.Common.DbParameter.Precision> e <xref:System.Data.Common.DbParameter.Scale> sono implementati come proprietà virtuali pubbliche. Sostituiscono le corrispondenti implementazioni esplicite dell'interfaccia, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> e <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.|
|Suggerimento|Quando si ricompila un provider di database ADO.NET, queste differenze richiederanno l'applicazione della parola chiave 'override' alle proprietà Precision e Scale. Questo è necessario solo quando si ricompilano i componenti. I file binari esistenti continueranno a funzionare.|
|Ambito|Secondario|
|Versione|4.5.1|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType></li></ul>|

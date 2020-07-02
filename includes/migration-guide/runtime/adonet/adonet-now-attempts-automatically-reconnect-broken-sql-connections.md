---
ms.openlocfilehash: 23ba6064a283b47312a66f3636c2834a7d58106e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620188"
---
### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a>ADO.NET ora tenta di riconnettere automaticamente le connessioni SQL interrotte

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.5.1, .NET Framework tenterà di riconnettere automaticamente le connessioni SQL interrotte. Anche se ciò in genere renderà più affidabili le app, in alcuni casi limite un'app deve sapere che la connessione è stata interrotta in modo da poter adottare determinate azioni alla riconnessione.

#### <a name="suggestion"></a>Suggerimento

Se questa funzionalità non è auspicabile per motivi di compatibilità, è possibile disabilitarla impostando la proprietà <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> di una stringa di connessione (o <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) su 0.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5.1|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Data.IDbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Configuration.ConnectionStringSettings.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor(System.String)></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor(System.Boolean)></li></ul>|

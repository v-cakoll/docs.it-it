---
ms.openlocfilehash: 241184d61d718fedfea396260e739d2dbc05c305
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620284"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a>SqlConnection non può più connettersi a SQL Server 1997 o a database che usano l'adapter VIA

#### <a name="details"></a>Dettagli

Le connessioni ai database SQL Server tramite il [protocollo Virtual Interface Adapter (via)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) non sono più supportate. Il protocollo usato per connettersi a un database di SQL Server è visibile nella stringa di connessione. Una connessione VIA conterrà via:&lt;nomeserver&gt;. Se l'app si connette a SQL tramite un protocollo diverso da VIA (TCP: o NP: ad esempio), non verrà rilevata alcuna modifica di rilievo. Inoltre, le connessioni a SQL Server 7 (1997) non sono più supportate.

#### <a name="suggestion"></a>Suggerimento

Il protocollo VIA è deprecato, pertanto deve essere usato un protocollo alternativo per connettersi ai database SQL. Il protocollo più comune usato è TCP/IP. Per altre informazioni sulle connessioni tramite TCP/IP, vedere [Abilitare il protocollo TCP/IP per un'istanza di database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)). Se il database è accessibile solo all'interno di una rete Intranet, il protocollo pipe condiviso può offrire prestazioni migliori se la rete è lenta.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)></li></ul>|

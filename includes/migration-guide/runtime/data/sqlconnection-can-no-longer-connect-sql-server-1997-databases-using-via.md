---
ms.openlocfilehash: fcaee245e98dfe71beb4042a2664a14b64cf2398
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235594"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a>SqlConnection non può più connettersi a SQL Server 1997 o a database che usano l'adapter VIA

|   |   |
|---|---|
|Dettagli|Le connessioni ai database SQL Server che usano il [protocollo Virtual Interface Adapter (VIA)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229%28v=sql.105%29) non sono più supportate. Il protocollo usato per connettersi a un database di SQL Server è visibile nella stringa di connessione. Una connessione VIA conterrà via:&lt;nomeserver&gt;. Se questa app si connette a SQL tramite un protocollo diverso da VIA (ad esempio tcp: o np:), non verrà rilevata nessuna modifica di rilievo. Le connessioni a SQL Server 7 (1997), inoltre, non sono più supportate.|
|Suggerimento|Il protocollo VIA è deprecato, pertanto deve essere usato un protocollo alternativo per connettersi ai database SQL. Il protocollo più comune usato è TCP/IP. Per altre informazioni sulle connessioni tramite TCP/IP, vedere [Abilitare il protocollo TCP/IP per un'istanza di database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)). Se il database è accessibile solo all'interno di una rete Intranet, il protocollo pipe condiviso può offrire prestazioni migliori se la rete è lenta.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)?displayProperty=nameWithType></li></ul>|

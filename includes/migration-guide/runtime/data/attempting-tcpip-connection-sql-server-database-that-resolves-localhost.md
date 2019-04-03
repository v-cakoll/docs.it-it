---
ms.openlocfilehash: a4b8a03661650a3ef1d96b656798c3c3d39a5705
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "58467074"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a>Il tentativo di connessione TCP/IP a un database di SQL Server corrispondente a `localhost` non riesce

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6 e 4.6.1, il tentativo di connessione TCP/IP a un database di SQL Server corrispondente a <code>localhost</code> ha esito negativo con l'errore &quot;Si è verificato un errore di rete o specifico dell'istanza mentre si cercava di stabilire una connessione con SQL Server. Il server non è stato trovato o non è accessibile. Verificare che il nome dell'istanza sia corretto e che SQL Server sia configurato in modo da consentire connessioni remote. (provider: Interfacce di rete SQL, errore: 26 - Errore nell'individuazione del server/dell'istanza specificati)&quot;|
|Suggerimento|Questo problema è stato risolto ed è stato ripristinato il comportamento precedente in .NET Framework 4.6.2. Per connettersi a un database di SQL Server corrispondente a <code>localhost</code>, eseguire l'aggiornamento a .NET Framework 4.6.2.|
|Ambito|Secondario|
|Versione|4.6|
|Tipo|Runtime|


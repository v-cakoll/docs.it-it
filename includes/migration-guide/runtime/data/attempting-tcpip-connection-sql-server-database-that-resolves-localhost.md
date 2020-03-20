---
ms.openlocfilehash: e36dac19beb6251debef100656670a6623344eea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "68237826"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a>Il tentativo di connessione TCP/IP a un database di SQL Server corrispondente a `localhost` non riesce

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6 e 4.6.1, il tentativo di connessione TCP/IP a un database di SQL Server corrispondente a <code>localhost</code> ha esito negativo con l'errore &quot;Si è verificato un errore di rete o specifico dell'istanza mentre si cercava di stabilire una connessione con SQL Server. Il server non è stato trovato o non è accessibile. Verificare che il nome dell'istanza sia corretto e che il server sia configurato in modo da consentire connessioni remote. (provider: interfacce di rete SQL, errore: 26 - Errore nell'individuazione del server/dell'istanza specificata)&quot;|
|Suggerimento|Questo problema è stato risolto ed è stato ripristinato il comportamento precedente in .NET Framework 4.6.2. Per connettersi a un database di SQL Server corrispondente a <code>localhost</code>, eseguire l'aggiornamento a .NET Framework 4.6.2.|
|Scope|Minorenne|
|Versione|4.6|
|Type|Runtime|

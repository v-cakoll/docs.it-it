---
ms.openlocfilehash: 87cb2570d3d47a2acb85b5557141c0fef885516a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621800"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a>Il tentativo di connessione TCP/IP a un database di SQL Server corrispondente a `localhost` non riesce

#### <a name="details"></a>Dettagli

In .NET Framework 4.6 e 4.6.1, il tentativo di connessione TCP/IP a un database di SQL Server corrispondente a <code>localhost</code> ha esito negativo con l'errore &quot;Si è verificato un errore di rete o specifico dell'istanza mentre si cercava di stabilire una connessione con SQL Server. Il server non è stato trovato o non è accessibile. Verificare che il nome dell'istanza sia corretto e che il server sia configurato in modo da consentire connessioni remote. (provider: interfacce di rete SQL, errore: 26 - Errore nell'individuazione del server/dell'istanza specificata)&quot;

#### <a name="suggestion"></a>Suggerimento

Questo problema è stato risolto ed è stato ripristinato il comportamento precedente in .NET Framework 4.6.2. Per connettersi a un database di SQL Server corrispondente a <code>localhost</code>, eseguire l'aggiornamento a .NET Framework 4.6.2.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.6|
|Type|Runtime|

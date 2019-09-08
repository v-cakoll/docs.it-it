---
title: Sicurezza in SQL Server Express
ms.date: 03/30/2017
ms.assetid: cf9cf6d9-4b05-43e9-ac7b-6cefbfcd6d4e
ms.openlocfilehash: 55f1d141e50ed7afd851d7330cfaf2e3b6380f18
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791696"
---
# <a name="sql-server-express-security"></a>Sicurezza in SQL Server Express
Microsoft SQL Server Express Edition (SQL Server Express) è basata su Microsoft SQL Server e supporta la maggior parte delle funzionalità del motore di database. È progettato in modo tale che le funzionalità non essenziali e la connettività di rete siano disattivate per impostazione predefinita, al fine di ridurre la superficie di attacco disponibile per utenti malintenzionati.  
  
 SQL Server Express viene in genere installato come un'istanza denominata. Il nome predefinito dell'istanza è `SQLExpress`. Un'istanza denominata è identificata dal nome di rete del computer e dal nome di istanza specificato durante l'installazione.  
  
## <a name="network-access"></a>Accesso alla rete  
 Per motivi di sicurezza, i protocolli di rete sono disabilitati per impostazione predefinita in SQL Server Express. In tal modo è possibile prevenire attacchi da utenti esterni che potrebbero compromettere la sicurezza del computer che ospita l'istanza di SQL Server Express. Per connettersi a un'istanza di SQL Server Express da un altro computer, è necessario abilitare in modo esplicito la connettività di rete e avviare il servizio SQL Server Browser.  
  
 Dopo aver abilitato la connettività di rete, un'istanza di SQL Server Express presenta gli stessi requisiti di sicurezza delle altre edizioni di SQL Server.  
  
## <a name="user-instances"></a>Istanze utente  
 Un'istanza utente è un'istanza distinta del motore di database di SQL Server Express generata da un'istanza padre di SQL Server Express. L'obiettivo primario di un'istanza utente è consentire a utenti che eseguono Windows con un account utente con privilegi minimi di disporre dei privilegi dell'amministratore di sistema (`sysadmin`) per l'istanza di SQL Server Express in esecuzione nel computer locale. Le istanze utente non devono essere usate per utenti che sono già amministratori di sistema del proprio computer.  
  
 Un'istanza utente viene generata da un'istanza primaria di SQL Server o SQL Server Express per conto di un utente. Viene eseguita come processo utente nel contesto di sicurezza Windows dell'utente e non come servizio. Gli account di accesso di SQL Server non sono consentiti. Sono infatti supportati solo quelli di Windows. In tal modo si impedisce a software in esecuzione in un'istanza utente di apportare modifiche a livello di sistema per le quali l'utente non dispone delle autorizzazioni. A un'istanza utente, nota anche come istanza figlio o client, viene talvolta fatto riferimento usando l'acronimo RAN (Run As Normal User).  
  
 Ogni istanza utente è isolata dalla relativa istanza padre e da altre istanze utente in esecuzione nello stesso computer. I database installati nelle istanze utente vengono aperti solo in modalità utente singolo e non sono accessibili a più utenti. La replica, le query distribuite e le connessioni remote sono disabilitate per le istanze utente. Durante la connessione a un'istanza utente, gli utenti non dispongono di privilegi speciali sull'istanza padre di SQL Server Express.  
  
## <a name="external-resources"></a>Risorse esterne  
 Per altre informazioni su SQL Server Express, vedere le risorse seguenti.  
  
|||  
|-|-|  
|[Documentazione online di Microsoft SQL Server 2005 Express Edition](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms165706(v=sql.90))|Documentazione completa relativa a SQL Server 2005 Express Edition.|  
|[Istanze utente per utenti non amministratori](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms143684(v=sql.100)) in documentazione online di SQL Server|Viene descritto come creare e distribuire istanze utente.|  
|[Connessione alle istanze utente di SQL Server Express](sql-server-express-user-instances.md)|Vengono descritte le funzionalità dell'istanza utente in un'applicazione ADO.NET. Vengono inoltre fornite informazioni su come abilitare un'istanza utente, effettuare la connessione a un'istanza utente usando un oggetto <xref:System.Data.SqlClient.SqlConnection>, la durata dell'istanza utente e gli scenari dell'istanza utente.|  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza di SQL Server](sql-server-security.md)
- [Connessione alle istanze utente di SQL Server Express](sql-server-express-user-instances.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)

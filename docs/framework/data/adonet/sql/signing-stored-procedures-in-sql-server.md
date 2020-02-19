---
title: Firma di stored procedure in SQL Server
ms.date: 01/05/2018
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
ms.openlocfilehash: 0131655d06a6ef543ea460d04739401538cac04b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452357"
---
# <a name="signing-stored-procedures-in-sql-server"></a>Firma di stored procedure in SQL Server

Un firma digitale è un digest di dati crittografato con la chiave privata del firmatario. Tramite la chiave privata, la firma digitale è univoca per il titolare o il proprietario. È possibile firmare stored procedure, funzioni (ad eccezione delle funzioni inline con valori di tabella), trigger e assembly.

È possibile firmare una stored procedure con un certificato o una chiave asimmetrica. Le firme sono progettate per scenari in cui le autorizzazioni non possono essere ereditate tramite il concatenamento della proprietà oppure in cui la catena di proprietà è interrotta, come nel caso delle istruzioni SQL dinamiche. È quindi possibile creare un utente mappato al certificato, concedendo le autorizzazioni utente per gli oggetti a cui deve accedere il stored procedure.

È inoltre possibile creare un account di accesso mappato allo stesso certificato, quindi concedere le autorizzazioni a livello di server necessarie per l'account di accesso o aggiungere l'account di accesso a uno o più ruoli predefiniti del server. Questo è progettato per evitare di abilitare l'impostazione del database `TRUSTWORTHY` per gli scenari in cui sono necessarie autorizzazioni di livello superiore.

Quando viene eseguita la stored procedure, SQL Server combina le autorizzazioni dell'utente del certificato e/o l'account di accesso con quelli del chiamante. A differenza della clausola `EXECUTE AS`, non modifica il contesto di esecuzione della stored procedure. Le funzioni predefinite che restituiscono i nomi di accesso e i nomi utente restituiscono il nome del chiamante e non il nome dell'utente del certificato.

## <a name="creating-certificates"></a>Creazione di certificati

Quando si firma una stored procedure con un certificato o una chiave asimmetrica, viene creato un digest di dati costituito dall'hash crittografato del codice stored procedure, insieme all'utente Execute-As, usando la chiave privata. In fase di esecuzione il digest di dati viene decrittografato usando la chiave pubblica e confrontato con il valore hash della stored procedure. Se si modifica l'utente Execute-As, il valore hash viene invalidato in modo che la firma digitale non corrisponda più. Se si modifica il stored procedure la firma viene eliminata completamente, che impedisce a un utente che non ha accesso alla chiave privata di modificare il codice di stored procedure. In entrambi i casi, è necessario firmare di nuovo la procedura ogni volta che si modifica il codice o l'utente Execute-As.

Per la firma di un modulo sono necessari due passaggi:

1. Creazione di un certificato tramite l'istruzione `CREATE CERTIFICATE [certificateName]` Transact-SQL. Questa istruzione prevede diverse opzioni per l'impostazione di una data di inizio e una data di fine, nonché di una password. La data di scadenza predefinita è di un anno.

1. Firma della stored procedure con il certificato tramite l'istruzione `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` Transact-SQL.

Una volta che il modulo è stato firmato, è necessario creare una o più entità per contenere le autorizzazioni aggiuntive che devono essere associate al certificato.

Se il modulo necessita di autorizzazioni aggiuntive a livello di database:

1. Creazione di un utente del database associato al certificato tramite l'istruzione `CREATE USER [userName] FROM CERTIFICATE [certificateName]` Transact-SQL. Questo utente esiste solo nel database e non è associato a un account di accesso a meno che non sia stato creato anche un account di accesso dallo stesso certificato.

1. Concedere all'utente del certificato le autorizzazioni necessarie a livello di database.

Se il modulo necessita di autorizzazioni aggiuntive a livello di server:

1. Copiare il certificato nel database di `master`.

1. Creare un account di accesso associato a tale certificato utilizzando l'istruzione Transact-SQL `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]`.

1. Concedere all'account di accesso del certificato le autorizzazioni a livello di server richieste.

> [!NOTE]
> Un certificato non può concedere autorizzazioni a un utente al quale sono state revocate autorizzazioni usando l'istruzione DENY. DENY ha sempre la precedenza su GRANT e impedisce al chiamante di ereditare autorizzazioni concesse all'utente del certificato.

## <a name="external-resources"></a>Risorse esterne

Per altre informazioni, vedere le seguenti risorse.

|Resource|Descrizione|
|--------------|-----------------|
|[Firma del modulo](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms345102(v=sql.100))|Viene descritta la firma del modulo, che fornisce uno scenario di esempio e i collegamenti agli articoli di Transact-SQL pertinenti.|
|[Firma di stored procedure con un certificato](/sql/relational-databases/tutorial-signing-stored-procedures-with-a-certificate)|Viene fornita un'esercitazione per firmare una stored procedure con un certificato.|

## <a name="see-also"></a>Vedere anche

- [Protezione delle applicazioni ADO.NET](../securing-ado-net-applications.md)
- [Cenni preliminari sulla sicurezza in SQL Server](overview-of-sql-server-security.md)
- [Scenari di sicurezza delle applicazioni in SQL Server](application-security-scenarios-in-sql-server.md)
- [Gestione delle autorizzazioni con stored procedure in SQL Server](managing-permissions-with-stored-procedures-in-sql-server.md)
- [Scrittura dinamica sicura in SQL Server](writing-secure-dynamic-sql-in-sql-server.md)
- [Personalizzazione delle autorizzazioni con rappresentazione in SQL Server](customizing-permissions-with-impersonation-in-sql-server.md)
- [Modifica di dati con stored procedure](../modifying-data-with-stored-procedures.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)

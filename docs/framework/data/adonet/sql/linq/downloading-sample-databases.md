---
title: Ottenere i database di SQL Server di esempio per gli esempi di codice ADO.NET
description: Scaricare i database di SQL Server di esempio usati negli esempi di codice nella documentazione di ADO.NET, nonché strumenti di gestione e di SQL Server
ms.date: 10/18/2018
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 8ab65f992c9cf2b65271a237fa06eb96e358ae6a
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153488"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Ottenere i database di esempio per gli esempi di codice ADO.NET

Un numero di esempi e procedure dettagliate di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentazione usare database SQL Server e SQL Server Express. È possibile scaricare questi prodotti gratuitamente da Microsoft.

## <a name="get-the-northwind-sample-database-for-sql-server"></a>Ottenere il database di esempio Northwind di SQL Server

Scaricare lo script `instnwnd.sql` dal repository di GitHub seguente per creare e caricare il database di esempio Northwind per SQL Server:

[Database di esempio Northwind e pubs per Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

Prima di utilizzare il database Northwind, è necessario eseguire scaricato `instnwnd.sql` file di script per ricreare il database in un'istanza di SQL Server tramite [SQL Server Management Studio](#get_ssms) o uno strumento simile. Seguire le istruzioni nel file Leggimi del repository.

> [!TIP]
> Se è interessati per il database Northwind per Microsoft Access, vedere [installare il database di esempio Northwind per Microsoft Access](#northwind_access).

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a>Ottenere il database di esempio AdventureWorks per SQL Server

Scaricare il database di esempio AdventureWorks per SQL Server dal repository di GitHub seguente:

[Database di esempio AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

Dopo aver scaricato uno dei backup del database (\*con estensione bak) i file, ripristinare il backup in un'istanza di SQL Server usando SQL Server Management Studio (SSMS). Visualizzare [ottenere SQL Server Management Studio](#get_ssms).

## <a name="get_sql"></a> Scarica SQL Server Express

SQL Server Express è un'edizione gratuita e base di SQL Server che è possibile ridistribuire con le applicazioni. Scaricare SQL Server Express dalla pagina seguente:
  
[SQL Server Express Edition](https://www.microsoft.com/sql-server/sql-server-editions-express)

Se si usa [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB è inclusa l'edizione Community gratuita di Visual Studio, nonché le edizioni Professional e versioni successive.  

## <a name="get_ssms"></a> Ottenere SQL Server Management Studio
Se si desidera visualizzare o modificare un database in cui è stato scaricato, è possibile usare SQL Server Management Studio (SSMS). Download di SSMS dalla pagina seguente:

[Scaricare SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms) 

È anche possibile visualizzare e gestire i database nell'ambiente di sviluppo integrato (IDE) di Visual Studio. Nelle [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connettersi al database da **Esplora oggetti di SQL Server**, o creare una connessione dati al database nella **Esplora Server**. Aprire questi riquadri explorer dal **vista** menu.

## <a name="northwind_access"></a> Installare il database di esempio Northwind per Microsoft Access

Il database di esempio Northwind per Microsoft Access non è disponibile nel Microsoft Download Center. Per installare Northwind direttamente dall'interno di Access, eseguire le operazioni seguenti:

1. Aprire l'accesso.

1. Invio **Northwind** nel **Cerca modelli Online** e quindi selezionare **invio**.

1. Nella schermata dei risultati, selezionare **Northwind**. Apre una nuova finestra con una descrizione del database Northwind.

1. Nella nuova finestra, nelle **nome del File** testo immettere un nome di file per la copia del database Northwind.

1. Scegliere **Crea**. Accesso Scarica il database Northwind e prepara il file.

1. Una volta completato questo processo, il database viene aperto con una schermata iniziale.

## <a name="see-also"></a>Vedere anche

- [Introduzione](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)

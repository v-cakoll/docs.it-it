---
title: Ottenere i database di esempio per gli esempi di codice ADO.NET
description: Scaricare i database di esempio usati negli esempi di codice nella documentazione di ADO.NET, nonché strumenti di gestione e di SQL Server
ms.date: 10/12/2018
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 75ae1895d683b669f51b33130fc2f47010e39814
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347513"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Ottenere i database di esempio per gli esempi di codice ADO.NET

Un numero di esempi e procedure dettagliate nel [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentazione usare database di esempio e SQL Server Express. È possibile scaricare questi prodotti gratuitamente da Microsoft.

## <a name="get-the-adventureworks-sample-database"></a>Ottenere il database di esempio AdventureWorks

Scaricare il database di esempio AdventureWorks dal repository di GitHub seguente:

[Database di esempio AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

Dopo aver scaricato uno dei backup del database (\*con estensione bak) i file, ripristinare il backup in un'istanza di SQL Server usando SQL Server Management Studio (SSMS). Visualizzare [ottenere SQL Server Management Studio](#get_ssms).

## <a name="get-the-northwind-sample-database"></a>Ottenere il database di esempio Northwind

Scaricare il database di esempio Northwind dalla pagina seguente nel Microsoft Download Center:

[Northwind and Pubs Sample Databases](https://go.microsoft.com/fwlink?linkid=64296)

Dopo che il file è stato scaricato, fare doppio clic sul file per estrarre il database e script. Per impostazione predefinita, i file vengono installati nella cartella `<drive>:\SQL Server 2000 Sample Databases`.

Prima di utilizzare il database Northwind, è necessario effettuare una delle operazioni seguenti:

- Ricreare il database in un'istanza di SQL Server eseguendo il `instnwnd.sql` file script nella cartella di installazione.

- Collegare il `northwnd.mdf` file con il corrispondente `*.ldf` file di log a un'istanza di SQL Server.

## <a name="get_sql"></a> Scarica SQL Server Express

SQL Server Express è un'edizione gratuita e base di SQL Server che è possibile ridistribuire con le applicazioni. Scaricare SQL Server Express dalla pagina seguente:
  
[Edizioni Express di SQL Server](https://www.microsoft.com/sql-server/sql-server-editions-express)

Se si usa [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB è inclusa l'edizione Community, nonché le edizioni Professional e versioni successive.  

## <a name="get_ssms"></a> Ottenere SQL Server Management Studio
Se si desidera visualizzare o modificare un database in cui è stato scaricato, è possibile usare SQL Server Management Studio (SSMS). Download di SSMS dalla pagina seguente:

[Scaricare SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms) 

È anche possibile visualizzare e gestire i database nell'ambiente di sviluppo integrato (IDE) di Visual Studio. Nelle [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connettersi al database da **Esplora oggetti di SQL Server**, o creare una connessione dati al database nella **Esplora Server**. Aprire questi riquadri explorer dal **vista** menu.
  
## <a name="see-also"></a>Vedere anche

- [Introduzione](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)

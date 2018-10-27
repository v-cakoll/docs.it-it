---
title: Ottenere i database di esempio per gli esempi di codice ADO.NET
description: Scaricare i database di esempio usati negli esempi di codice nella documentazione di ADO.NET, nonché strumenti di gestione e di SQL Server
ms.date: 10/18/2018
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 9779300288135cb9332a028d547ce55a07e89471
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188391"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Ottenere i database di esempio per gli esempi di codice ADO.NET

Un numero di esempi e procedure dettagliate nel [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentazione usare database di esempio e SQL Server Express. È possibile scaricare questi prodotti gratuitamente da Microsoft.

## <a name="get-the-northwind-sample-database"></a>Ottenere il database di esempio Northwind

Scaricare il database di esempio Northwind dalla pagina seguente nel Microsoft Download Center:

[Northwind and Pubs Sample Databases](https://go.microsoft.com/fwlink?linkid=64296)

Dopo che il file è stato scaricato, fare doppio clic sul file per estrarre il database e script. Per impostazione predefinita, i file vengono installati nella cartella `<drive>:\SQL Server 2000 Sample Databases`.

Prima è possibile usare il database Northwind, è necessario ricreare il database in un'istanza di SQL Server usando [SQL Server Management Studio](#get_ssms) o uno strumento simile per l'esecuzione di `instnwnd.sql` file script nella cartella di installazione.

## <a name="get-the-adventureworks-sample-database"></a>Ottenere il database di esempio AdventureWorks

Scaricare il database di esempio AdventureWorks dal repository di GitHub seguente:

[Database di esempio AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

Dopo aver scaricato uno dei backup del database (\*con estensione bak) i file, ripristinare il backup in un'istanza di SQL Server usando SQL Server Management Studio (SSMS). Visualizzare [ottenere SQL Server Management Studio](#get_ssms).

## <a name="get_sql"></a> Scarica SQL Server Express

SQL Server Express è un'edizione gratuita e base di SQL Server che è possibile ridistribuire con le applicazioni. Scaricare SQL Server Express dalla pagina seguente:
  
[Edizioni Express di SQL Server](https://www.microsoft.com/sql-server/sql-server-editions-express)

Se si usa [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB è inclusa l'edizione Community gratuita, nonché le edizioni Professional e versioni successive.  

## <a name="get_ssms"></a> Ottenere SQL Server Management Studio
Se si desidera visualizzare o modificare un database in cui è stato scaricato, è possibile usare SQL Server Management Studio (SSMS). Download di SSMS dalla pagina seguente:

[Scaricare SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms) 

È anche possibile visualizzare e gestire i database nell'ambiente di sviluppo integrato (IDE) di Visual Studio. Nelle [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connettersi al database da **Esplora oggetti di SQL Server**, o creare una connessione dati al database nella **Esplora Server**. Aprire questi riquadri explorer dal **vista** menu.
  
## <a name="see-also"></a>Vedere anche

- [Introduzione](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)

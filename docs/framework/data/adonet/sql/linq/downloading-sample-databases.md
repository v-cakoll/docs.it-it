---
title: Ottenere i database di SQL Server di esempio per ADO.NET esempi di codiceGet the sample SQL Server databases for ADO.NET code samples
description: Scaricare i database di SQL Server di esempio usati negli esempi di codice nella documentazione di ADO.NET, nonché SQL Server e gli strumenti di gestioneDownload the sample SQL Server databases used in the code samples in the ADO.NET documentation, as well as SQL Server and management tools
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 3449f502834f449f5023bd52457d45ffaf9b0fa1
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607984"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Ottenere i database di esempio per ADO.NET esempi di codiceGet the sample databases for ADO.NET code samples

Numerosi esempi e procedure dettagliate nella [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentazione usano database di SQL Server di esempio e SQL Server Express. È possibile scaricare questi prodotti gratuitamente da Microsoft.

## <a name="get-the-northwind-sample-database-for-sql-server"></a>Ottenere il database di esempio Northwind per SQL ServerGet the Northwind sample database for SQL Server

Scaricare lo `instnwnd.sql` script dal seguente repository GitHub per creare e caricare il database di esempio Northwind per SQL Server:

[Northwind e pub database di esempio per Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

Prima di poter utilizzare il database Northwind, `instnwnd.sql` è necessario eseguire il file di script scaricato per ricreare il database in un'istanza di SQL Server utilizzando [SQL Server Management Studio](#get_ssms) o uno strumento simile. Seguire le istruzioni nel file Leggimi nel repository.

> [!TIP]
> Se si sta cercando il database Northwind per Microsoft Access, vedere [Installare il database di esempio Northwind per Microsoft Access](#northwind_access).

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a>Ottenere il database di esempio Northwind per Microsoft Access

Il database di esempio Northwind per Microsoft Access non è disponibile nell'Area download Microsoft. Per installare Northwind direttamente da Access, eseguire le operazioni seguenti:

1. Aprire Access.

1. Immettere **Northwind** nella casella **Cerca modelli online** e quindi selezionare **INVIO**.

1. Nella schermata dei risultati selezionare **Northwind**. Verrà visualizzata una nuova finestra con una descrizione del database Northwind.

1. Nella nuova finestra, nella casella di testo **Nome file,** specificare un nome file per la copia del database Northwind.

1. Selezionare **Create** (Crea). Access scarica il database Northwind e prepara il file.

1. Al termine di questo processo, il database viene aperto con una schermata iniziale.

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a>Ottenere il database di esempio AdventureWorks per SQL ServerGet the AdventureWorks sample database for SQL Server

Scaricare il database di esempio AdventureWorks per SQL Server dal repository GitHub seguente:Download the AdventureWorks sample database for SQL Server from the following GitHub repository:

[Database di esempio AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

Dopo aver scaricato uno dei\*file di backup del database (con estensione bak), ripristinare il backup in un'istanza di SQL Server utilizzando SQL Server Management Studio (SSMS). Vedere [Ottenere SQL Server Management Studio](#get_ssms).

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a>Ottenere SQL Server Management StudioGet SQL Server Management Studio
Se si desidera visualizzare o modificare un database scaricato, è possibile utilizzare SQL Server Management Studio (SSMS). Scaricare SSMS dalla pagina seguente:Download SSMS from the following page:

[Scaricare SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms)

È inoltre possibile visualizzare e gestire i database nell'ambiente di sviluppo integrato (IDE) di Visual Studio. In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)connettersi al database da Esplora oggetti di SQL **Server**oppure creare una connessione dati al database in Esplora **server**. Aprire questi riquadri di esplorazione dal menu **Visualizza.**

## <a name="get-sql-server-express"></a><a name="get_sql"></a>Ottenere SQL Server ExpressGet SQL Server Express

SQL Server Express è un'edizione gratuita entry-level di SQL Server che è possibile ridistribuire con le applicazioni. Scaricare SQL Server Express dalla pagina seguente:
  
[SQL Server Express Edition](https://www.microsoft.com/sql-server/sql-server-editions-express)

Se si utilizza [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), SQL Server Express LocalDB è incluso nell'edizione community gratuita di Visual Studio, nonché le edizioni Professional e versioni successive.  

## <a name="see-also"></a>Vedere anche

- [Guida introduttiva](getting-started.md)

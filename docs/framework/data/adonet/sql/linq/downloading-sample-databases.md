---
title: Ottenere i database di esempio SQL Server per esempi di codice ADO.NET
description: Scaricare i database di esempio SQL Server utilizzati negli esempi di codice nella documentazione di ADO.NET, nonché SQL Server e gli strumenti di gestione
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 60566041ff4f99e96c9aee052dbcc17b5e5da9e5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794036"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Ottenere i database di esempio per gli esempi di codice ADO.NET

Alcuni esempi e procedure dettagliate nella documentazione utilizzano i [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] database di esempio SQL Server e SQL Server Express. È possibile scaricare questi prodotti gratuitamente da Microsoft.

## <a name="get-the-northwind-sample-database-for-sql-server"></a>Ottenere il database di esempio Northwind per SQL Server

Scaricare lo script `instnwnd.sql` dal repository GitHub seguente per creare e caricare il database di esempio Northwind per SQL Server:

[Database di esempio Northwind e pubs per Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

Prima di poter utilizzare il database Northwind, è necessario eseguire il file script `instnwnd.sql` scaricato per ricreare il database in un'istanza di SQL Server utilizzando [SQL Server Management Studio](#get_ssms) o uno strumento simile. Seguire le istruzioni nel file Leggimi del repository.

> [!TIP]
> Se si sta cercando il database Northwind per Microsoft Access, vedere [installare il database di esempio Northwind per Microsoft Access](#northwind_access).

## <a name="northwind_access"></a>Ottenere il database di esempio Northwind per Microsoft Access

Il database di esempio Northwind per Microsoft Access non è disponibile nell'area download Microsoft. Per installare Northwind direttamente dall'interno di Access, eseguire le operazioni seguenti:

1. Aprire accesso.

1. Immettere **Northwind** nella casella **Cerca modelli online** e quindi premere **invio**.

1. Nella schermata dei risultati selezionare **Northwind**. Verrà visualizzata una nuova finestra con una descrizione del database Northwind.

1. Nella casella di testo **nome file** della nuova finestra specificare un nome file per la copia del database Northwind.

1. Selezionare **Create**. Access Scarica il database Northwind e prepara il file.

1. Al termine di questo processo, il database verrà aperto con una schermata iniziale.

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a>Ottenere il database di esempio AdventureWorks per SQL Server

Scaricare il database di esempio AdventureWorks per SQL Server dal repository GitHub seguente:

[Database di esempio AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

Dopo aver scaricato uno dei file di backup del\*database (con estensione bak), ripristinare il backup in un'istanza di SQL Server tramite SQL Server Management Studio (SSMS). Vedere [Get SQL Server Management Studio](#get_ssms).

## <a name="get_ssms"></a>Ottenere SQL Server Management Studio
Se si vuole visualizzare o modificare un database scaricato, è possibile usare SQL Server Management Studio (SSMS). Scaricare SSMS dalla pagina seguente:

[Scaricare SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms) 

È anche possibile visualizzare e gestire i database in Visual Studio Integrated Development Environment (IDE). In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)connettersi al database da **Esplora oggetti di SQL Server**oppure creare una connessione dati al database **Esplora server**. Aprire i riquadri di Esplora risorse dal menu **Visualizza** .

## <a name="get_sql"></a>Ottenere SQL Server Express

SQL Server Express è un'edizione gratuita di SQL Server a livello di voce che è possibile ridistribuire con le applicazioni. Scaricare SQL Server Express dalla pagina seguente:
  
[Edizione SQL Server Express](https://www.microsoft.com/sql-server/sql-server-editions-express)

Se si usa [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express database locale è incluso nell'edizione Community gratuita di Visual Studio, nonché nelle edizioni Professional e versioni successive.  

## <a name="see-also"></a>Vedere anche

- [Introduzione](getting-started.md)

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
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="89517-103">Ottenere i database di esempio per gli esempi di codice ADO.NET</span><span class="sxs-lookup"><span data-stu-id="89517-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="89517-104">Un numero di esempi e procedure dettagliate nel [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentazione usare database di esempio e SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="89517-104">A number of samples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample databases and SQL Server Express.</span></span> <span data-ttu-id="89517-105">È possibile scaricare questi prodotti gratuitamente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="89517-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-adventureworks-sample-database"></a><span data-ttu-id="89517-106">Ottenere il database di esempio AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="89517-106">Get the AdventureWorks sample database</span></span>

<span data-ttu-id="89517-107">Scaricare il database di esempio AdventureWorks dal repository di GitHub seguente:</span><span class="sxs-lookup"><span data-stu-id="89517-107">Download the AdventureWorks sample database from the following GitHub repository:</span></span>

[<span data-ttu-id="89517-108">Database di esempio AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="89517-108">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="89517-109">Dopo aver scaricato uno dei backup del database (\*con estensione bak) i file, ripristinare il backup in un'istanza di SQL Server usando SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="89517-109">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="89517-110">Visualizzare [ottenere SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="89517-110">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-the-northwind-sample-database"></a><span data-ttu-id="89517-111">Ottenere il database di esempio Northwind</span><span class="sxs-lookup"><span data-stu-id="89517-111">Get the Northwind sample database</span></span>

<span data-ttu-id="89517-112">Scaricare il database di esempio Northwind dalla pagina seguente nel Microsoft Download Center:</span><span class="sxs-lookup"><span data-stu-id="89517-112">Download the Northwind sample database from the following page in the Microsoft Download Center:</span></span>

[<span data-ttu-id="89517-113">Northwind and Pubs Sample Databases</span><span class="sxs-lookup"><span data-stu-id="89517-113">Northwind and Pubs Sample Databases</span></span>](https://go.microsoft.com/fwlink?linkid=64296)

<span data-ttu-id="89517-114">Dopo che il file è stato scaricato, fare doppio clic sul file per estrarre il database e script.</span><span class="sxs-lookup"><span data-stu-id="89517-114">After the file has downloaded, double-click the file to extract the databases and scripts.</span></span> <span data-ttu-id="89517-115">Per impostazione predefinita, i file vengono installati nella cartella `<drive>:\SQL Server 2000 Sample Databases`.</span><span class="sxs-lookup"><span data-stu-id="89517-115">By default, the files are installed in the folder `<drive>:\SQL Server 2000 Sample Databases`.</span></span>

<span data-ttu-id="89517-116">Prima di utilizzare il database Northwind, è necessario effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89517-116">Before you can use the Northwind database, you have to do one of the following things:</span></span>

- <span data-ttu-id="89517-117">Ricreare il database in un'istanza di SQL Server eseguendo il `instnwnd.sql` file script nella cartella di installazione.</span><span class="sxs-lookup"><span data-stu-id="89517-117">Recreate the database on an instance of SQL Server by running the `instnwnd.sql` script file in the installation folder.</span></span>

- <span data-ttu-id="89517-118">Collegare il `northwnd.mdf` file con il corrispondente `*.ldf` file di log a un'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="89517-118">Attach the `northwnd.mdf` file with its corresponding `*.ldf` log file to an instance of SQL Server.</span></span>

## <a name="get_sql"></a> <span data-ttu-id="89517-119">Scarica SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="89517-119">Get SQL Server Express</span></span>

<span data-ttu-id="89517-120">SQL Server Express è un'edizione gratuita e base di SQL Server che è possibile ridistribuire con le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="89517-120">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="89517-121">Scaricare SQL Server Express dalla pagina seguente:</span><span class="sxs-lookup"><span data-stu-id="89517-121">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="89517-122">Edizioni Express di SQL Server</span><span class="sxs-lookup"><span data-stu-id="89517-122">SQL Server Express Editions</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="89517-123">Se si usa [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB è inclusa l'edizione Community, nonché le edizioni Professional e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="89517-123">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the Community edition as well as the Professional and higher editions.</span></span>  

## <a name="get_ssms"></a> <span data-ttu-id="89517-124">Ottenere SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="89517-124">Get SQL Server Management Studio</span></span>
<span data-ttu-id="89517-125">Se si desidera visualizzare o modificare un database in cui è stato scaricato, è possibile usare SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="89517-125">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="89517-126">Download di SSMS dalla pagina seguente:</span><span class="sxs-lookup"><span data-stu-id="89517-126">Download SSMS from the following page:</span></span>

[<span data-ttu-id="89517-127">Scaricare SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="89517-127">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="89517-128">È anche possibile visualizzare e gestire i database nell'ambiente di sviluppo integrato (IDE) di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="89517-128">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="89517-129">Nelle [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connettersi al database da **Esplora oggetti di SQL Server**, o creare una connessione dati al database nella **Esplora Server**.</span><span class="sxs-lookup"><span data-stu-id="89517-129">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="89517-130">Aprire questi riquadri explorer dal **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="89517-130">Open these explorer panes from the **View** menu.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="89517-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89517-131">See also</span></span>

- [<span data-ttu-id="89517-132">Introduzione</span><span class="sxs-lookup"><span data-stu-id="89517-132">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)

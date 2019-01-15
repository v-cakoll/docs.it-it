---
title: Ottenere i database di SQL Server di esempio per gli esempi di codice ADO.NET
description: Scaricare i database di SQL Server di esempio usati negli esempi di codice nella documentazione di ADO.NET, nonché strumenti di gestione e di SQL Server
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 5580f06f3d28ed6d70f75b619498ac8de7bc3326
ms.sourcegitcommit: 75567a3cb437009db55949c6092f4e77ed1a9da4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2019
ms.locfileid: "54307292"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="94970-103">Ottenere i database di esempio per gli esempi di codice ADO.NET</span><span class="sxs-lookup"><span data-stu-id="94970-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="94970-104">Un numero di esempi e procedure dettagliate di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentazione usare database SQL Server e SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="94970-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="94970-105">È possibile scaricare questi prodotti gratuitamente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="94970-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="94970-106">Ottenere il database di esempio Northwind di SQL Server</span><span class="sxs-lookup"><span data-stu-id="94970-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="94970-107">Scaricare lo script `instnwnd.sql` dal repository di GitHub seguente per creare e caricare il database di esempio Northwind per SQL Server:</span><span class="sxs-lookup"><span data-stu-id="94970-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="94970-108">Database di esempio Northwind e pubs per Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="94970-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="94970-109">Prima di utilizzare il database Northwind, è necessario eseguire scaricato `instnwnd.sql` file di script per ricreare il database in un'istanza di SQL Server tramite [SQL Server Management Studio](#get_ssms) o uno strumento simile.</span><span class="sxs-lookup"><span data-stu-id="94970-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="94970-110">Seguire le istruzioni nel file Leggimi del repository.</span><span class="sxs-lookup"><span data-stu-id="94970-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="94970-111">Se è interessati per il database Northwind per Microsoft Access, vedere [installare il database di esempio Northwind per Microsoft Access](#northwind_access).</span><span class="sxs-lookup"><span data-stu-id="94970-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="northwind_access"></a> <span data-ttu-id="94970-112">Ottenere il database di esempio Northwind per Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="94970-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="94970-113">Il database di esempio Northwind per Microsoft Access non è disponibile nel Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="94970-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="94970-114">Per installare Northwind direttamente dall'interno di Access, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="94970-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="94970-115">Aprire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="94970-115">Open Access.</span></span>

1. <span data-ttu-id="94970-116">Invio **Northwind** nel **Cerca modelli Online** e quindi selezionare **invio**.</span><span class="sxs-lookup"><span data-stu-id="94970-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="94970-117">Nella schermata dei risultati, selezionare **Northwind**.</span><span class="sxs-lookup"><span data-stu-id="94970-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="94970-118">Apre una nuova finestra con una descrizione del database Northwind.</span><span class="sxs-lookup"><span data-stu-id="94970-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="94970-119">Nella nuova finestra, nelle **nome del File** testo immettere un nome di file per la copia del database Northwind.</span><span class="sxs-lookup"><span data-stu-id="94970-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="94970-120">Scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="94970-120">Select **Create**.</span></span> <span data-ttu-id="94970-121">Accesso Scarica il database Northwind e prepara il file.</span><span class="sxs-lookup"><span data-stu-id="94970-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="94970-122">Una volta completato questo processo, il database viene aperto con una schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="94970-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="94970-123">Ottenere il database di esempio AdventureWorks per SQL Server</span><span class="sxs-lookup"><span data-stu-id="94970-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="94970-124">Scaricare il database di esempio AdventureWorks per SQL Server dal repository di GitHub seguente:</span><span class="sxs-lookup"><span data-stu-id="94970-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="94970-125">Database di esempio AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="94970-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="94970-126">Dopo aver scaricato uno dei backup del database (\*con estensione bak) i file, ripristinare il backup in un'istanza di SQL Server usando SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="94970-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="94970-127">Visualizzare [ottenere SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="94970-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get_ssms"></a> <span data-ttu-id="94970-128">Ottenere SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="94970-128">Get SQL Server Management Studio</span></span>
<span data-ttu-id="94970-129">Se si desidera visualizzare o modificare un database in cui è stato scaricato, è possibile usare SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="94970-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="94970-130">Download di SSMS dalla pagina seguente:</span><span class="sxs-lookup"><span data-stu-id="94970-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="94970-131">Scaricare SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="94970-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="94970-132">È anche possibile visualizzare e gestire i database nell'ambiente di sviluppo integrato (IDE) di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="94970-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="94970-133">Nelle [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connettersi al database da **Esplora oggetti di SQL Server**, o creare una connessione dati al database nella **Esplora Server**.</span><span class="sxs-lookup"><span data-stu-id="94970-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="94970-134">Aprire questi riquadri explorer dal **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="94970-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get_sql"></a> <span data-ttu-id="94970-135">Get SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="94970-135">Get SQL Server Express</span></span>

<span data-ttu-id="94970-136">SQL Server Express è un'edizione gratuita e base di SQL Server che è possibile ridistribuire con le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="94970-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="94970-137">Scaricare SQL Server Express dalla pagina seguente:</span><span class="sxs-lookup"><span data-stu-id="94970-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="94970-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="94970-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="94970-139">Se si usa [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB è inclusa l'edizione Community gratuita di Visual Studio, nonché le edizioni Professional e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="94970-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="94970-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94970-140">See also</span></span>

- [<span data-ttu-id="94970-141">Introduzione</span><span class="sxs-lookup"><span data-stu-id="94970-141">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)

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
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="a236a-103">Ottenere i database di esempio per gli esempi di codice ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a236a-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="a236a-104">Un numero di esempi e procedure dettagliate nel [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentazione usare database di esempio e SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="a236a-104">A number of samples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample databases and SQL Server Express.</span></span> <span data-ttu-id="a236a-105">È possibile scaricare questi prodotti gratuitamente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a236a-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database"></a><span data-ttu-id="a236a-106">Ottenere il database di esempio Northwind</span><span class="sxs-lookup"><span data-stu-id="a236a-106">Get the Northwind sample database</span></span>

<span data-ttu-id="a236a-107">Scaricare il database di esempio Northwind dalla pagina seguente nel Microsoft Download Center:</span><span class="sxs-lookup"><span data-stu-id="a236a-107">Download the Northwind sample database from the following page in the Microsoft Download Center:</span></span>

[<span data-ttu-id="a236a-108">Northwind and Pubs Sample Databases</span><span class="sxs-lookup"><span data-stu-id="a236a-108">Northwind and Pubs Sample Databases</span></span>](https://go.microsoft.com/fwlink?linkid=64296)

<span data-ttu-id="a236a-109">Dopo che il file è stato scaricato, fare doppio clic sul file per estrarre il database e script.</span><span class="sxs-lookup"><span data-stu-id="a236a-109">After the file has downloaded, double-click the file to extract the databases and scripts.</span></span> <span data-ttu-id="a236a-110">Per impostazione predefinita, i file vengono installati nella cartella `<drive>:\SQL Server 2000 Sample Databases`.</span><span class="sxs-lookup"><span data-stu-id="a236a-110">By default, the files are installed in the folder `<drive>:\SQL Server 2000 Sample Databases`.</span></span>

<span data-ttu-id="a236a-111">Prima è possibile usare il database Northwind, è necessario ricreare il database in un'istanza di SQL Server usando [SQL Server Management Studio](#get_ssms) o uno strumento simile per l'esecuzione di `instnwnd.sql` file script nella cartella di installazione.</span><span class="sxs-lookup"><span data-stu-id="a236a-111">Before you can use the Northwind database, you have to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool to run the `instnwnd.sql` script file in the installation folder.</span></span>

## <a name="get-the-adventureworks-sample-database"></a><span data-ttu-id="a236a-112">Ottenere il database di esempio AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="a236a-112">Get the AdventureWorks sample database</span></span>

<span data-ttu-id="a236a-113">Scaricare il database di esempio AdventureWorks dal repository di GitHub seguente:</span><span class="sxs-lookup"><span data-stu-id="a236a-113">Download the AdventureWorks sample database from the following GitHub repository:</span></span>

[<span data-ttu-id="a236a-114">Database di esempio AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="a236a-114">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="a236a-115">Dopo aver scaricato uno dei backup del database (\*con estensione bak) i file, ripristinare il backup in un'istanza di SQL Server usando SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="a236a-115">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="a236a-116">Visualizzare [ottenere SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="a236a-116">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get_sql"></a> <span data-ttu-id="a236a-117">Scarica SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="a236a-117">Get SQL Server Express</span></span>

<span data-ttu-id="a236a-118">SQL Server Express è un'edizione gratuita e base di SQL Server che è possibile ridistribuire con le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a236a-118">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="a236a-119">Scaricare SQL Server Express dalla pagina seguente:</span><span class="sxs-lookup"><span data-stu-id="a236a-119">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="a236a-120">Edizioni Express di SQL Server</span><span class="sxs-lookup"><span data-stu-id="a236a-120">SQL Server Express Editions</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="a236a-121">Se si usa [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB è inclusa l'edizione Community gratuita, nonché le edizioni Professional e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="a236a-121">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition as well as the Professional and higher editions.</span></span>  

## <a name="get_ssms"></a> <span data-ttu-id="a236a-122">Ottenere SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a236a-122">Get SQL Server Management Studio</span></span>
<span data-ttu-id="a236a-123">Se si desidera visualizzare o modificare un database in cui è stato scaricato, è possibile usare SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="a236a-123">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="a236a-124">Download di SSMS dalla pagina seguente:</span><span class="sxs-lookup"><span data-stu-id="a236a-124">Download SSMS from the following page:</span></span>

[<span data-ttu-id="a236a-125">Scaricare SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="a236a-125">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="a236a-126">È anche possibile visualizzare e gestire i database nell'ambiente di sviluppo integrato (IDE) di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a236a-126">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="a236a-127">Nelle [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connettersi al database da **Esplora oggetti di SQL Server**, o creare una connessione dati al database nella **Esplora Server**.</span><span class="sxs-lookup"><span data-stu-id="a236a-127">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="a236a-128">Aprire questi riquadri explorer dal **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="a236a-128">Open these explorer panes from the **View** menu.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a236a-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a236a-129">See also</span></span>

- [<span data-ttu-id="a236a-130">Introduzione</span><span class="sxs-lookup"><span data-stu-id="a236a-130">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)

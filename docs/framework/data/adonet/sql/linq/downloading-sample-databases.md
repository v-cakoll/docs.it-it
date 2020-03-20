---
title: Ottenere i database di SQL Server di esempio per ADO.NET esempi di codiceGet the sample SQL Server databases for ADO.NET code samples
description: Scaricare i database di SQL Server di esempio usati negli esempi di codice nella documentazione di ADO.NET, nonché SQL Server e gli strumenti di gestioneDownload the sample SQL Server databases used in the code samples in the ADO.NET documentation, as well as SQL Server and management tools
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 19d659cbe8f39d27b71dc59c738355f12fce92a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148387"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="deabe-103">Ottenere i database di esempio per ADO.NET esempi di codiceGet the sample databases for ADO.NET code samples</span><span class="sxs-lookup"><span data-stu-id="deabe-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="deabe-104">Numerosi esempi e procedure dettagliate nella [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentazione usano database di SQL Server di esempio e SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="deabe-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="deabe-105">È possibile scaricare questi prodotti gratuitamente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="deabe-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="deabe-106">Ottenere il database di esempio Northwind per SQL ServerGet the Northwind sample database for SQL Server</span><span class="sxs-lookup"><span data-stu-id="deabe-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="deabe-107">Scaricare lo `instnwnd.sql` script dal seguente repository GitHub per creare e caricare il database di esempio Northwind per SQL Server:</span><span class="sxs-lookup"><span data-stu-id="deabe-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="deabe-108">Northwind e pub database di esempio per Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="deabe-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="deabe-109">Prima di poter utilizzare il database Northwind, `instnwnd.sql` è necessario eseguire il file di script scaricato per ricreare il database in un'istanza di SQL Server utilizzando [SQL Server Management Studio](#get_ssms) o uno strumento simile.</span><span class="sxs-lookup"><span data-stu-id="deabe-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="deabe-110">Seguire le istruzioni nel file Leggimi nel repository.</span><span class="sxs-lookup"><span data-stu-id="deabe-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="deabe-111">Se si sta cercando il database Northwind per Microsoft Access, vedere [Installare il database di esempio Northwind per Microsoft Access](#northwind_access).</span><span class="sxs-lookup"><span data-stu-id="deabe-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a><span data-ttu-id="deabe-112">Ottenere il database di esempio Northwind per Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="deabe-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="deabe-113">Il database di esempio Northwind per Microsoft Access non è disponibile nell'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="deabe-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="deabe-114">Per installare Northwind direttamente da Access, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="deabe-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="deabe-115">Aprire Access.</span><span class="sxs-lookup"><span data-stu-id="deabe-115">Open Access.</span></span>

1. <span data-ttu-id="deabe-116">Immettere **Northwind** nella casella **Cerca modelli online** e quindi selezionare **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="deabe-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="deabe-117">Nella schermata dei risultati selezionare **Northwind**.</span><span class="sxs-lookup"><span data-stu-id="deabe-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="deabe-118">Verrà visualizzata una nuova finestra con una descrizione del database Northwind.</span><span class="sxs-lookup"><span data-stu-id="deabe-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="deabe-119">Nella nuova finestra, nella casella di testo **Nome file,** specificare un nome file per la copia del database Northwind.</span><span class="sxs-lookup"><span data-stu-id="deabe-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="deabe-120">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="deabe-120">Select **Create**.</span></span> <span data-ttu-id="deabe-121">Access scarica il database Northwind e prepara il file.</span><span class="sxs-lookup"><span data-stu-id="deabe-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="deabe-122">Al termine di questo processo, il database viene aperto con una schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="deabe-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="deabe-123">Ottenere il database di esempio AdventureWorks per SQL ServerGet the AdventureWorks sample database for SQL Server</span><span class="sxs-lookup"><span data-stu-id="deabe-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="deabe-124">Scaricare il database di esempio AdventureWorks per SQL Server dal repository GitHub seguente:Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span><span class="sxs-lookup"><span data-stu-id="deabe-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="deabe-125">Database di esempio AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="deabe-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="deabe-126">Dopo aver scaricato uno dei\*file di backup del database (con estensione bak), ripristinare il backup in un'istanza di SQL Server utilizzando SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="deabe-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="deabe-127">Vedere [Ottenere SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="deabe-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a><span data-ttu-id="deabe-128">Ottenere SQL Server Management StudioGet SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="deabe-128">Get SQL Server Management Studio</span></span>
<span data-ttu-id="deabe-129">Se si desidera visualizzare o modificare un database scaricato, è possibile utilizzare SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="deabe-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="deabe-130">Scaricare SSMS dalla pagina seguente:Download SSMS from the following page:</span><span class="sxs-lookup"><span data-stu-id="deabe-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="deabe-131">Scaricare SQL Server Management Studio (SSMS)Download SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="deabe-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms)

<span data-ttu-id="deabe-132">È inoltre possibile visualizzare e gestire i database nell'ambiente di sviluppo integrato (IDE) di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="deabe-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="deabe-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)connettersi al database da Esplora oggetti di SQL **Server**oppure creare una connessione dati al database in Esplora **server**.</span><span class="sxs-lookup"><span data-stu-id="deabe-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="deabe-134">Aprire questi riquadri di esplorazione dal menu **Visualizza.**</span><span class="sxs-lookup"><span data-stu-id="deabe-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get-sql-server-express"></a><a name="get_sql"></a><span data-ttu-id="deabe-135">Ottenere SQL Server ExpressGet SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="deabe-135">Get SQL Server Express</span></span>

<span data-ttu-id="deabe-136">SQL Server Express è un'edizione gratuita entry-level di SQL Server che è possibile ridistribuire con le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="deabe-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="deabe-137">Scaricare SQL Server Express dalla pagina seguente:</span><span class="sxs-lookup"><span data-stu-id="deabe-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="deabe-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="deabe-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="deabe-139">Se si utilizza [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB è incluso nell'edizione community gratuita di Visual Studio, nonché le edizioni Professional e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="deabe-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="deabe-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="deabe-140">See also</span></span>

- [<span data-ttu-id="deabe-141">Guida introduttiva</span><span class="sxs-lookup"><span data-stu-id="deabe-141">Getting Started</span></span>](getting-started.md)

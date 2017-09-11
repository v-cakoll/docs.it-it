---
title: SqlMetal.exe (strumento per la generazione del codice)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- SQLMetal [LINQ to SQL]
- code generation tool
- SQLMetal.exe
- LINQ to SQL, serialization
- LINQ to SQL, DBML files
- LINQ to SQL, SQLMetal
ms.assetid: 819e5a96-7646-4fdb-b14b-fe31221b0614
caps.latest.revision: 43
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6d0ac9c682c60db8eb9e5188a71916dc5d97de60
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="sqlmetalexe-code-generation-tool"></a><span data-ttu-id="bcfe2-102">SqlMetal.exe (strumento per la generazione del codice)</span><span class="sxs-lookup"><span data-stu-id="bcfe2-102">SqlMetal.exe (Code Generation Tool)</span></span>
<span data-ttu-id="bcfe2-103">Lo strumento da riga di comando SqlMetal genera codice e mapping per il componente [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcfe2-103">The SqlMetal command-line tool generates code and mapping for the [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] component of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="bcfe2-104">Mediante l'applicazione delle opzioni riportate più avanti in questo argomento è possibile usare SqlMetal per eseguire diverse operazioni, fra cui:</span><span class="sxs-lookup"><span data-stu-id="bcfe2-104">By applying options that appear later in this topic, you can instruct SqlMetal to perform several different actions that include the following:</span></span>  
  
-   <span data-ttu-id="bcfe2-105">A partire da un database, generare codice sorgente e attributi di mapping oppure un file di mapping.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-105">From a database, generate source code and mapping attributes or a mapping file.</span></span>  
  
-   <span data-ttu-id="bcfe2-106">A partire da un database, generare un file .dbml (Database Markup Language) intermedio da personalizzare.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-106">From a database, generate an intermediate database markup language (.dbml) file for customization.</span></span>  
  
-   <span data-ttu-id="bcfe2-107">A partire da un file .dbml, generare codice e attributi di mapping oppure un file di mapping.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-107">From a .dbml file, generate code and mapping attributes or a mapping file.</span></span>  
  
 <span data-ttu-id="bcfe2-108">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="bcfe2-109">Per impostazione predefinita, il file si trova in `drive`:\Programmi\Microsoft SDKs\Windows\v`n.nn`\bin.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-109">By default, the file is located at `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span></span> <span data-ttu-id="bcfe2-110">Se non si installa Visual Studio, è possibile ottenere il file SQLMetal anche scaricando [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=142225).</span><span class="sxs-lookup"><span data-stu-id="bcfe2-110">If you do not install Visual Studio, you can also get the SQLMetal file by downloading the [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=142225).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bcfe2-111">Gli sviluppatori che usano Visual Studio possono usare anche [!INCLUDE[vs_ordesigner_long](../../../includes/vs-ordesigner-long-md.md)] per generare classi di entità.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-111">Developers who use Visual Studio can also use the [!INCLUDE[vs_ordesigner_long](../../../includes/vs-ordesigner-long-md.md)] to generate entity classes.</span></span> <span data-ttu-id="bcfe2-112">Quando si usano database di grandi dimensioni, l'approccio basato sulla riga di comando rappresenta la scelta più adeguata.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-112">The command-line approach scales well for large databases.</span></span> <span data-ttu-id="bcfe2-113">In quanto strumento da riga di comando, SqlMetal può essere usato in un processo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-113">Because SqlMetal is a command-line tool, you can use it in a build process.</span></span>  
  
 <span data-ttu-id="bcfe2-114">Per eseguire lo strumento, usare il prompt dei comandi per sviluppatori o il prompt dei comandi di Visual Studio in Windows 7.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-114">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="bcfe2-115">Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md). Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bcfe2-115">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcfe2-116">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bcfe2-116">Syntax</span></span>  
  
```  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a><span data-ttu-id="bcfe2-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bcfe2-117">Options</span></span>  
 <span data-ttu-id="bcfe2-118">Per visualizzare l'elenco di opzioni più aggiornato, digitare `sqlmetal /?` al prompt dei comandi dal percorso di installazione.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-118">To view the most current option list, type `sqlmetal /?` at a command prompt from the installed location.</span></span>  
  
 <span data-ttu-id="bcfe2-119">**Opzioni di connessione**</span><span class="sxs-lookup"><span data-stu-id="bcfe2-119">**Connection Options**</span></span>  
  
|<span data-ttu-id="bcfe2-120">Opzione</span><span class="sxs-lookup"><span data-stu-id="bcfe2-120">Option</span></span>|<span data-ttu-id="bcfe2-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bcfe2-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="bcfe2-122">**/server:** *\<nome>*</span><span class="sxs-lookup"><span data-stu-id="bcfe2-122">**/server:** *\<name>*</span></span>|<span data-ttu-id="bcfe2-123">Specifica il nome del server di database.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-123">Specifies database server name.</span></span>|  
|<span data-ttu-id="bcfe2-124">**/database:** *\<nome>*</span><span class="sxs-lookup"><span data-stu-id="bcfe2-124">**/database:** *\<name>*</span></span>|<span data-ttu-id="bcfe2-125">Specifica il catalogo del database contenuto nel server.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-125">Specifies database catalog on server.</span></span>|  
|<span data-ttu-id="bcfe2-126">**/user:** *\<nome>*</span><span class="sxs-lookup"><span data-stu-id="bcfe2-126">**/user:** *\<name>*</span></span>|<span data-ttu-id="bcfe2-127">Specifica l'ID utente di accesso.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-127">Specifies logon user id.</span></span> <span data-ttu-id="bcfe2-128">Valore predefinito: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-128">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="bcfe2-129">**/password:** *\<password>*</span><span class="sxs-lookup"><span data-stu-id="bcfe2-129">**/password:** *\<password>*</span></span>|<span data-ttu-id="bcfe2-130">Specifica la password di accesso.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-130">Specifies logon password.</span></span> <span data-ttu-id="bcfe2-131">Valore predefinito: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-131">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="bcfe2-132">**/conn:** *\<stringa di connessione>*</span><span class="sxs-lookup"><span data-stu-id="bcfe2-132">**/conn:** *\<connection string>*</span></span>|<span data-ttu-id="bcfe2-133">Specifica la stringa di connessione al database.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-133">Specifies database connection string.</span></span> <span data-ttu-id="bcfe2-134">Non può essere usata con l'opzione **/server**, **/database**, **/user**o **/password** .</span><span class="sxs-lookup"><span data-stu-id="bcfe2-134">Cannot be used with **/server**, **/database**, **/user**, or **/password** options.</span></span><br /><br /> <span data-ttu-id="bcfe2-135">Non includere il nome file nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-135">Do not include the file name in the connection string.</span></span> <span data-ttu-id="bcfe2-136">Aggiungere invece il nome file alla riga di comando come file di input.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-136">Instead, add the file name to the command line as the input file.</span></span> <span data-ttu-id="bcfe2-137">La riga seguente, ad esempio, specifica "c:\northwnd.mdf" come file di input: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-137">For example, the following line specifies "c:\northwnd.mdf" as the input file: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span></span>|  
|<span data-ttu-id="bcfe2-138">**/timeout:** *\<secondi>*</span><span class="sxs-lookup"><span data-stu-id="bcfe2-138">**/timeout:** *\<seconds>*</span></span>|<span data-ttu-id="bcfe2-139">Specifica il valore di timeout quando SqlMetal accede al database.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-139">Specifies time-out value when SqlMetal accesses the database.</span></span> <span data-ttu-id="bcfe2-140">Valore predefinito: 0 (ovvero nessun limite di tempo).</span><span class="sxs-lookup"><span data-stu-id="bcfe2-140">Default value: 0 (that is, no time limit).</span></span>|  
  
 <span data-ttu-id="bcfe2-141">**Opzioni di estrazione**</span><span class="sxs-lookup"><span data-stu-id="bcfe2-141">**Extraction options**</span></span>  
  
|<span data-ttu-id="bcfe2-142">Opzione</span><span class="sxs-lookup"><span data-stu-id="bcfe2-142">Option</span></span>|<span data-ttu-id="bcfe2-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bcfe2-143">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="bcfe2-144">**/views**</span><span class="sxs-lookup"><span data-stu-id="bcfe2-144">**/views**</span></span>|<span data-ttu-id="bcfe2-145">Estrae viste di database.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-145">Extracts database views.</span></span>|  
|<span data-ttu-id="bcfe2-146">**/functions**</span><span class="sxs-lookup"><span data-stu-id="bcfe2-146">**/functions**</span></span>|<span data-ttu-id="bcfe2-147">Estrae funzioni di database.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-147">Extracts database functions.</span></span>|  
|<span data-ttu-id="bcfe2-148">**/sprocs**</span><span class="sxs-lookup"><span data-stu-id="bcfe2-148">**/sprocs**</span></span>|<span data-ttu-id="bcfe2-149">Estrae stored procedure.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-149">Extracts stored procedures.</span></span>|  
  
 <span data-ttu-id="bcfe2-150">**Opzioni di output**</span><span class="sxs-lookup"><span data-stu-id="bcfe2-150">**Output options**</span></span>  
  
|<span data-ttu-id="bcfe2-151">Opzione</span><span class="sxs-lookup"><span data-stu-id="bcfe2-151">Option</span></span>|<span data-ttu-id="bcfe2-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bcfe2-152">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="bcfe2-153">**/dbml** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="bcfe2-153">**/dbml** *[:file]*</span></span>|<span data-ttu-id="bcfe2-154">Invia l'output come file .dbml.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-154">Sends output as .dbml.</span></span> <span data-ttu-id="bcfe2-155">Non può essere usata con l'opzione **/map** .</span><span class="sxs-lookup"><span data-stu-id="bcfe2-155">Cannot be used with **/map** option.</span></span>|  
|<span data-ttu-id="bcfe2-156">**/code** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="bcfe2-156">**/code** *[:file]*</span></span>|<span data-ttu-id="bcfe2-157">Invia l'output come codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-157">Sends output as source code.</span></span> <span data-ttu-id="bcfe2-158">Non può essere usata con l'opzione **/dbml** .</span><span class="sxs-lookup"><span data-stu-id="bcfe2-158">Cannot be used with **/dbml** option.</span></span>|  
|<span data-ttu-id="bcfe2-159">**/map** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="bcfe2-159">**/map** *[:file]*</span></span>|<span data-ttu-id="bcfe2-160">Genera un file di mapping XML anziché gli attributi.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-160">Generates an XML mapping file instead of attributes.</span></span> <span data-ttu-id="bcfe2-161">Non può essere usata con l'opzione **/dbml** .</span><span class="sxs-lookup"><span data-stu-id="bcfe2-161">Cannot be used with **/dbml** option.</span></span>|  
  
 <span data-ttu-id="bcfe2-162">**Varie**</span><span class="sxs-lookup"><span data-stu-id="bcfe2-162">**Miscellaneous**</span></span>  
  
|<span data-ttu-id="bcfe2-163">Opzione</span><span class="sxs-lookup"><span data-stu-id="bcfe2-163">Option</span></span>|<span data-ttu-id="bcfe2-164">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bcfe2-164">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="bcfe2-165">**/language:** *\<linguaggio>*</span><span class="sxs-lookup"><span data-stu-id="bcfe2-165">**/language:** *\<language>*</span></span>|<span data-ttu-id="bcfe2-166">Specifica il linguaggio del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-166">Specifies source code language.</span></span><br /><br /> <span data-ttu-id="bcfe2-167">Valori validi per *\<linguaggio>*: vb, csharp.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-167">Valid *\<language>*: vb, csharp.</span></span><br /><br /> <span data-ttu-id="bcfe2-168">Valore predefinito: derivato dall'estensione nel nome file del codice.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-168">Default value: Derived from extension on code file name.</span></span>|  
|<span data-ttu-id="bcfe2-169">**/namespace:** *\<nome>*</span><span class="sxs-lookup"><span data-stu-id="bcfe2-169">**/namespace:** *\<name>*</span></span>|<span data-ttu-id="bcfe2-170">Specifica lo spazio dei nomi del codice generato.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-170">Specifies namespace of the generated code.</span></span> <span data-ttu-id="bcfe2-171">Valore predefinito: nessuno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-171">Default value: no namespace.</span></span>|  
|<span data-ttu-id="bcfe2-172">**/context:** *\<tipo>*</span><span class="sxs-lookup"><span data-stu-id="bcfe2-172">**/context:** *\<type>*</span></span>|<span data-ttu-id="bcfe2-173">Specifica il nome della classe del contesto dati.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-173">Specifies name of data context class.</span></span> <span data-ttu-id="bcfe2-174">Valore predefinito: derivato dal nome del database.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-174">Default value: Derived from database name.</span></span>|  
|<span data-ttu-id="bcfe2-175">**/entitybase:** *\<tipo>*</span><span class="sxs-lookup"><span data-stu-id="bcfe2-175">**/entitybase:** *\<type>*</span></span>|<span data-ttu-id="bcfe2-176">Specifica la classe base delle classi di entità nel codice generato.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-176">Specifies the base class of the entity classes in the generated code.</span></span> <span data-ttu-id="bcfe2-177">Valore predefinito: le entità non dispongono di classe base.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-177">Default value: Entities have no base class.</span></span>|  
|<span data-ttu-id="bcfe2-178">**/pluralize**</span><span class="sxs-lookup"><span data-stu-id="bcfe2-178">**/pluralize**</span></span>|<span data-ttu-id="bcfe2-179">Rende automaticamente plurali o singolari i nomi delle classi e dei membri.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-179">Automatically pluralizes or singularizes class and member names.</span></span><br /><br /> <span data-ttu-id="bcfe2-180">Opzione disponibile solo nella versione in lingua inglese degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-180">This option is available only in the U.S. English version.</span></span>|  
|<span data-ttu-id="bcfe2-181">**/serialization:** *\<opzione>*</span><span class="sxs-lookup"><span data-stu-id="bcfe2-181">**/serialization:** *\<option>*</span></span>|<span data-ttu-id="bcfe2-182">Genera classi serializzabili.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-182">Generates serializable classes.</span></span><br /><br /> <span data-ttu-id="bcfe2-183">Valori validi per *\<opzione>*: None, Unidirectional.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-183">Valid *\<option>*: None, Unidirectional.</span></span> <span data-ttu-id="bcfe2-184">Valore predefinito: None.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-184">Default value: None.</span></span><br /><br /> <span data-ttu-id="bcfe2-185">Per altre informazioni, vedere [Serializzazione](../../../docs/framework/data/adonet/sql/linq/serialization.md).</span><span class="sxs-lookup"><span data-stu-id="bcfe2-185">For more information, see [Serialization](../../../docs/framework/data/adonet/sql/linq/serialization.md).</span></span>|  
  
 <span data-ttu-id="bcfe2-186">**File di input**</span><span class="sxs-lookup"><span data-stu-id="bcfe2-186">**Input File**</span></span>  
  
|<span data-ttu-id="bcfe2-187">Opzione</span><span class="sxs-lookup"><span data-stu-id="bcfe2-187">Option</span></span>|<span data-ttu-id="bcfe2-188">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bcfe2-188">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="bcfe2-189">**\<file input>**</span><span class="sxs-lookup"><span data-stu-id="bcfe2-189">**\<input file>**</span></span>|<span data-ttu-id="bcfe2-190">Specifica un file .mdf di SQL Server Express, un file .sdf di [!INCLUDE[ssEW](../../../includes/ssew-md.md)] oppure un file .dbml intermedio.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-190">Specifies a SQL Server Express .mdf file, a [!INCLUDE[ssEW](../../../includes/ssew-md.md)] .sdf file, or a .dbml intermediate file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcfe2-191">Note</span><span class="sxs-lookup"><span data-stu-id="bcfe2-191">Remarks</span></span>  
 <span data-ttu-id="bcfe2-192">Il funzionamento di SqlMetal prevede di fatto due passaggi:</span><span class="sxs-lookup"><span data-stu-id="bcfe2-192">SqlMetal functionality actually involves two steps:</span></span>  
  
-   <span data-ttu-id="bcfe2-193">Estrazione dei metadati del database in un file .dbml.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-193">Extracting the metadata of the database into a .dbml file.</span></span>  
  
-   <span data-ttu-id="bcfe2-194">Generazione di un file di output di codice.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-194">Generating a code output file.</span></span>  
  
     <span data-ttu-id="bcfe2-195">Le opzioni della riga di comando, se usate correttamente, consentono di creare codice sorgente [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] o C# oppure un file di mapping XML.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-195">By using the appropriate command-line options, you can produce [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] or C# source code, or you can produce an XML mapping file.</span></span>  
  
 <span data-ttu-id="bcfe2-196">Per estrarre i metadati da un file .mdf è necessario aggiungere il nome di tale file in coda a tutte le altre opzioni specificate.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-196">To extract the metadata from an .mdf file, you must specify the name of the .mdf file after all other options.</span></span>  
  
 <span data-ttu-id="bcfe2-197">Se non è specificato alcun valore per **/server** , si presuppone che sia **localhost/sqlexpress** .</span><span class="sxs-lookup"><span data-stu-id="bcfe2-197">If no **/server** is specified, **localhost/sqlexpress** is assumed.</span></span>  
  
 [!INCLUDE[sqprsqext](../../../includes/sqprsqext-md.md)]<span data-ttu-id="bcfe2-198"> genera un'eccezione se almeno una delle condizioni seguenti è vera:</span><span class="sxs-lookup"><span data-stu-id="bcfe2-198"> throws an exception if one or more of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="bcfe2-199">SqlMetal tenta di estrarre una stored procedure che chiama se stessa.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-199">SqlMetal tries to extract a stored procedure that calls itself.</span></span>  
  
-   <span data-ttu-id="bcfe2-200">Il livello di annidamento di una stored procedure, di una funzione o di una vista è maggiore di 32.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-200">The nesting level of a stored procedure, function, or view exceeds 32.</span></span>  
  
     <span data-ttu-id="bcfe2-201">SqlMetal rileva questa eccezione e la segnala come avviso.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-201">SqlMetal catches this exception and reports it as a warning.</span></span>  
  
 <span data-ttu-id="bcfe2-202">Per specificare un nome file di input, aggiungere il nome nella riga di comando come file di input.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-202">To specify an input file name, add the name to the command line as the input file.</span></span> <span data-ttu-id="bcfe2-203">Non è possibile includere il nome file nella stringa di connessione mediante l'opzione **/conn** .</span><span class="sxs-lookup"><span data-stu-id="bcfe2-203">Including the file name in the connection string (using the **/conn** option) is not supported.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="bcfe2-204">Esempi</span><span class="sxs-lookup"><span data-stu-id="bcfe2-204">Examples</span></span>  
 <span data-ttu-id="bcfe2-205">Genera un file .dbml che contiene metadati SQL estratti:</span><span class="sxs-lookup"><span data-stu-id="bcfe2-205">Generate a .dbml file that includes extracted SQL metadata:</span></span>  
  
 <span data-ttu-id="bcfe2-206">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span><span class="sxs-lookup"><span data-stu-id="bcfe2-206">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span></span>  
  
 <span data-ttu-id="bcfe2-207">Genera un file .dbml che contiene metadati SQL estratti da un file .mdf tramite SQL Server Express:</span><span class="sxs-lookup"><span data-stu-id="bcfe2-207">Generate a .dbml file that includes extracted SQL metadata from an .mdf file by using SQL Server Express:</span></span>  
  
 <span data-ttu-id="bcfe2-208">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span><span class="sxs-lookup"><span data-stu-id="bcfe2-208">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span></span>  
  
 <span data-ttu-id="bcfe2-209">Genera un file .dbml che contiene metadati SQL estratti da SQL Server Express:</span><span class="sxs-lookup"><span data-stu-id="bcfe2-209">Generate a .dbml file that includes extracted SQL metadata from SQL Server Express:</span></span>  
  
 <span data-ttu-id="bcfe2-210">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span><span class="sxs-lookup"><span data-stu-id="bcfe2-210">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span></span>  
  
 <span data-ttu-id="bcfe2-211">Genera codice sorgente a partire da un file di metadati .dmbl:</span><span class="sxs-lookup"><span data-stu-id="bcfe2-211">Generate source code from a .dbml metadata file:</span></span>  
  
 <span data-ttu-id="bcfe2-212">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span><span class="sxs-lookup"><span data-stu-id="bcfe2-212">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span></span>  
  
 <span data-ttu-id="bcfe2-213">Genera codice sorgente direttamente da metadati SQL:</span><span class="sxs-lookup"><span data-stu-id="bcfe2-213">Generate source code from SQL metadata directly:</span></span>  
  
 <span data-ttu-id="bcfe2-214">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span><span class="sxs-lookup"><span data-stu-id="bcfe2-214">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bcfe2-215">Quando si usa l'opzione **/pluralize** con il database di esempio Northwind, si verifica il comportamento seguente.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-215">When you use the **/pluralize** option with the Northwind sample database, note the following behavior.</span></span> <span data-ttu-id="bcfe2-216">Quando SqlMetal crea nomi di tipo riga per le tabelle, i relativi nomi sono al singolare.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-216">When SqlMetal makes row-type names for tables, the table names are singular.</span></span> <span data-ttu-id="bcfe2-217">Quando crea proprietà <xref:System.Data.Linq.DataContext> per le tabelle, i relativi nomi sono invece al plurale.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-217">When it makes <xref:System.Data.Linq.DataContext> properties for tables, the table names are plural.</span></span> <span data-ttu-id="bcfe2-218">Per coincidenza, i nomi delle tabelle contenute nel database di esempio Northwind sono già al plurale.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-218">Coincidentally, the tables in the Northwind sample database are already plural.</span></span> <span data-ttu-id="bcfe2-219">Pertanto, l'opzione di pluralizzazione di fatto non viene usata.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-219">Therefore, you do not see that part working.</span></span> <span data-ttu-id="bcfe2-220">Di norma le tabelle di database vengono denominate al singolare, mentre le raccolte di .NET vengono denominate al plurale.</span><span class="sxs-lookup"><span data-stu-id="bcfe2-220">Although it is common practice to name database tables singular, it is also a common practice in .NET to name collections plural.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcfe2-221">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcfe2-221">See Also</span></span>  
 <span data-ttu-id="bcfe2-222">[How to: Generate the Object Model in Visual Basic or C#](../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  (Procedura: Generare il modello a oggetti in Visual Basic o C#)</span><span class="sxs-lookup"><span data-stu-id="bcfe2-222">[How to: Generate the Object Model in Visual Basic or C#](../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md) </span></span>  
 <span data-ttu-id="bcfe2-223">[Code Generation in LINQ to SQL](../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  (Generazione di codice in LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="bcfe2-223">[Code Generation in LINQ to SQL](../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md) </span></span>  
 <span data-ttu-id="bcfe2-224">[External Mapping](../../../docs/framework/data/adonet/sql/linq/external-mapping.md) (Mapping esterno)</span><span class="sxs-lookup"><span data-stu-id="bcfe2-224">[External Mapping](../../../docs/framework/data/adonet/sql/linq/external-mapping.md)</span></span>


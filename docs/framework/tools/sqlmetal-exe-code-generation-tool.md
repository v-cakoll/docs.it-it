---
title: SqlMetal.exe (strumento per la generazione del codice)
ms.date: 03/30/2017
helpviewer_keywords:
- SQLMetal [LINQ to SQL]
- code generation tool
- SQLMetal.exe
- LINQ to SQL, serialization
- LINQ to SQL, DBML files
- LINQ to SQL, SQLMetal
ms.assetid: 819e5a96-7646-4fdb-b14b-fe31221b0614
ms.openlocfilehash: d5b4c2b59b585b3d3a3584ef9055e70c9d998e85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71044086"
---
# <a name="sqlmetalexe-code-generation-tool"></a><span data-ttu-id="db90e-102">SqlMetal.exe (strumento per la generazione del codice)</span><span class="sxs-lookup"><span data-stu-id="db90e-102">SqlMetal.exe (Code Generation Tool)</span></span>
<span data-ttu-id="db90e-103">Lo strumento da riga di comando SqlMetal genera codice e mapping per il componente [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db90e-103">The SqlMetal command-line tool generates code and mapping for the [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] component of the .NET Framework.</span></span> <span data-ttu-id="db90e-104">Mediante l'applicazione delle opzioni riportate più avanti in questo argomento è possibile usare SqlMetal per eseguire diverse operazioni, fra cui:</span><span class="sxs-lookup"><span data-stu-id="db90e-104">By applying options that appear later in this topic, you can instruct SqlMetal to perform several different actions that include the following:</span></span>  
  
- <span data-ttu-id="db90e-105">A partire da un database, generare codice sorgente e attributi di mapping oppure un file di mapping.</span><span class="sxs-lookup"><span data-stu-id="db90e-105">From a database, generate source code and mapping attributes or a mapping file.</span></span>  
  
- <span data-ttu-id="db90e-106">A partire da un database, generare un file .dbml (Database Markup Language) intermedio da personalizzare.</span><span class="sxs-lookup"><span data-stu-id="db90e-106">From a database, generate an intermediate database markup language (.dbml) file for customization.</span></span>  
  
- <span data-ttu-id="db90e-107">A partire da un file .dbml, generare codice e attributi di mapping oppure un file di mapping.</span><span class="sxs-lookup"><span data-stu-id="db90e-107">From a .dbml file, generate code and mapping attributes or a mapping file.</span></span>  
  
 <span data-ttu-id="db90e-108">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="db90e-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="db90e-109">Per impostazione predefinita, il file si trova in `drive`:\Programmi\Microsoft SDKs\Windows\v`n.nn`\bin.</span><span class="sxs-lookup"><span data-stu-id="db90e-109">By default, the file is located at `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span></span> <span data-ttu-id="db90e-110">Se non si installa Visual Studio, è possibile ottenere il file SQLMetal anche scaricando [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225).</span><span class="sxs-lookup"><span data-stu-id="db90e-110">If you do not install Visual Studio, you can also get the SQLMetal file by downloading the [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db90e-111">Gli sviluppatori che usano Visual Studio possono usare anche Object Relational Designer per generare classi di entità.</span><span class="sxs-lookup"><span data-stu-id="db90e-111">Developers who use Visual Studio can also use the Object Relational Designer to generate entity classes.</span></span> <span data-ttu-id="db90e-112">Quando si usano database di grandi dimensioni, l'approccio basato sulla riga di comando rappresenta la scelta più adeguata.</span><span class="sxs-lookup"><span data-stu-id="db90e-112">The command-line approach scales well for large databases.</span></span> <span data-ttu-id="db90e-113">In quanto strumento da riga di comando, SqlMetal può essere usato in un processo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="db90e-113">Because SqlMetal is a command-line tool, you can use it in a build process.</span></span>  
  
 <span data-ttu-id="db90e-114">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="db90e-114">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="db90e-115">Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md). Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="db90e-115">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db90e-116">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db90e-116">Syntax</span></span>  
  
```console  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a><span data-ttu-id="db90e-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="db90e-117">Options</span></span>  
 <span data-ttu-id="db90e-118">Per visualizzare l'elenco di opzioni più aggiornato, digitare `sqlmetal /?` al prompt dei comandi dal percorso di installazione.</span><span class="sxs-lookup"><span data-stu-id="db90e-118">To view the most current option list, type `sqlmetal /?` at a command prompt from the installed location.</span></span>  
  
 <span data-ttu-id="db90e-119">**Opzioni di connessione**</span><span class="sxs-lookup"><span data-stu-id="db90e-119">**Connection Options**</span></span>  
  
|<span data-ttu-id="db90e-120">Opzione</span><span class="sxs-lookup"><span data-stu-id="db90e-120">Option</span></span>|<span data-ttu-id="db90e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db90e-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="db90e-122">**/server:** \* \<>del nome\*</span><span class="sxs-lookup"><span data-stu-id="db90e-122">**/server:** *\<name>*</span></span>|<span data-ttu-id="db90e-123">Specifica il nome del server di database.</span><span class="sxs-lookup"><span data-stu-id="db90e-123">Specifies database server name.</span></span>|  
|<span data-ttu-id="db90e-124">**/database:** \* \<>del nome\*</span><span class="sxs-lookup"><span data-stu-id="db90e-124">**/database:** *\<name>*</span></span>|<span data-ttu-id="db90e-125">Specifica il catalogo del database contenuto nel server.</span><span class="sxs-lookup"><span data-stu-id="db90e-125">Specifies database catalog on server.</span></span>|  
|<span data-ttu-id="db90e-126">**/user:** \* \<>del nome\*</span><span class="sxs-lookup"><span data-stu-id="db90e-126">**/user:** *\<name>*</span></span>|<span data-ttu-id="db90e-127">Specifica l'ID utente di accesso. Valore predefinito: usare l'autenticazione di Windows.Default value: Use Windows authentication.</span><span class="sxs-lookup"><span data-stu-id="db90e-127">Specifies logon user id. Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="db90e-128">**/password:** \* \<>password\*</span><span class="sxs-lookup"><span data-stu-id="db90e-128">**/password:** *\<password>*</span></span>|<span data-ttu-id="db90e-129">Specifica la password di accesso.</span><span class="sxs-lookup"><span data-stu-id="db90e-129">Specifies logon password.</span></span> <span data-ttu-id="db90e-130">Valore predefinito: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="db90e-130">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="db90e-131">**/conn:** stringa di \* \<connessione>\*</span><span class="sxs-lookup"><span data-stu-id="db90e-131">**/conn:** *\<connection string>*</span></span>|<span data-ttu-id="db90e-132">Specifica la stringa di connessione al database.</span><span class="sxs-lookup"><span data-stu-id="db90e-132">Specifies database connection string.</span></span> <span data-ttu-id="db90e-133">Non può essere usata con l'opzione **/server**, **/database**, **/user**o **/password** .</span><span class="sxs-lookup"><span data-stu-id="db90e-133">Cannot be used with **/server**, **/database**, **/user**, or **/password** options.</span></span><br /><br /> <span data-ttu-id="db90e-134">Non includere il nome file nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="db90e-134">Do not include the file name in the connection string.</span></span> <span data-ttu-id="db90e-135">Aggiungere invece il nome file alla riga di comando come file di input.</span><span class="sxs-lookup"><span data-stu-id="db90e-135">Instead, add the file name to the command line as the input file.</span></span> <span data-ttu-id="db90e-136">La riga seguente, ad esempio, specifica "c:\northwnd.mdf" come file di input: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span><span class="sxs-lookup"><span data-stu-id="db90e-136">For example, the following line specifies "c:\northwnd.mdf" as the input file: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span></span>|  
|<span data-ttu-id="db90e-137">**/timeout:** \* \<secondi>\*</span><span class="sxs-lookup"><span data-stu-id="db90e-137">**/timeout:** *\<seconds>*</span></span>|<span data-ttu-id="db90e-138">Specifica il valore di timeout quando SqlMetal accede al database.</span><span class="sxs-lookup"><span data-stu-id="db90e-138">Specifies time-out value when SqlMetal accesses the database.</span></span> <span data-ttu-id="db90e-139">Valore predefinito: 0 (ovvero nessun limite di tempo).</span><span class="sxs-lookup"><span data-stu-id="db90e-139">Default value: 0 (that is, no time limit).</span></span>|  
  
 <span data-ttu-id="db90e-140">**Opzioni di estrazione**</span><span class="sxs-lookup"><span data-stu-id="db90e-140">**Extraction options**</span></span>  
  
|<span data-ttu-id="db90e-141">Opzione</span><span class="sxs-lookup"><span data-stu-id="db90e-141">Option</span></span>|<span data-ttu-id="db90e-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db90e-142">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="db90e-143">**/views**</span><span class="sxs-lookup"><span data-stu-id="db90e-143">**/views**</span></span>|<span data-ttu-id="db90e-144">Estrae viste di database.</span><span class="sxs-lookup"><span data-stu-id="db90e-144">Extracts database views.</span></span>|  
|<span data-ttu-id="db90e-145">**/functions (funzioni)**</span><span class="sxs-lookup"><span data-stu-id="db90e-145">**/functions**</span></span>|<span data-ttu-id="db90e-146">Estrae funzioni di database.</span><span class="sxs-lookup"><span data-stu-id="db90e-146">Extracts database functions.</span></span>|  
|<span data-ttu-id="db90e-147">**/sprocs**</span><span class="sxs-lookup"><span data-stu-id="db90e-147">**/sprocs**</span></span>|<span data-ttu-id="db90e-148">Estrae stored procedure.</span><span class="sxs-lookup"><span data-stu-id="db90e-148">Extracts stored procedures.</span></span>|  
  
 <span data-ttu-id="db90e-149">**Opzioni di output**</span><span class="sxs-lookup"><span data-stu-id="db90e-149">**Output options**</span></span>  
  
|<span data-ttu-id="db90e-150">Opzione</span><span class="sxs-lookup"><span data-stu-id="db90e-150">Option</span></span>|<span data-ttu-id="db90e-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db90e-151">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="db90e-152">**/dbml** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="db90e-152">**/dbml** *[:file]*</span></span>|<span data-ttu-id="db90e-153">Invia l'output come file .dbml.</span><span class="sxs-lookup"><span data-stu-id="db90e-153">Sends output as .dbml.</span></span> <span data-ttu-id="db90e-154">Non può essere usata con l'opzione **/map** .</span><span class="sxs-lookup"><span data-stu-id="db90e-154">Cannot be used with **/map** option.</span></span>|  
|<span data-ttu-id="db90e-155">**/code** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="db90e-155">**/code** *[:file]*</span></span>|<span data-ttu-id="db90e-156">Invia l'output come codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="db90e-156">Sends output as source code.</span></span> <span data-ttu-id="db90e-157">Non può essere usata con l'opzione **/dbml** .</span><span class="sxs-lookup"><span data-stu-id="db90e-157">Cannot be used with **/dbml** option.</span></span>|  
|<span data-ttu-id="db90e-158">**/map** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="db90e-158">**/map** *[:file]*</span></span>|<span data-ttu-id="db90e-159">Genera un file di mapping XML anziché gli attributi.</span><span class="sxs-lookup"><span data-stu-id="db90e-159">Generates an XML mapping file instead of attributes.</span></span> <span data-ttu-id="db90e-160">Non può essere usata con l'opzione **/dbml** .</span><span class="sxs-lookup"><span data-stu-id="db90e-160">Cannot be used with **/dbml** option.</span></span>|  
  
 <span data-ttu-id="db90e-161">**Varie**</span><span class="sxs-lookup"><span data-stu-id="db90e-161">**Miscellaneous**</span></span>  
  
|<span data-ttu-id="db90e-162">Opzione</span><span class="sxs-lookup"><span data-stu-id="db90e-162">Option</span></span>|<span data-ttu-id="db90e-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db90e-163">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="db90e-164">**/language:** \* \<>della lingua\*</span><span class="sxs-lookup"><span data-stu-id="db90e-164">**/language:** *\<language>*</span></span>|<span data-ttu-id="db90e-165">Specifica il linguaggio del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="db90e-165">Specifies source code language.</span></span><br /><br /> <span data-ttu-id="db90e-166">\* \<Linguaggio \*valido>: vb, csharp.</span><span class="sxs-lookup"><span data-stu-id="db90e-166">Valid *\<language>*: vb, csharp.</span></span><br /><br /> <span data-ttu-id="db90e-167">Valore predefinito: derivato dall'estensione nel nome file del codice.</span><span class="sxs-lookup"><span data-stu-id="db90e-167">Default value: Derived from extension on code file name.</span></span>|  
|<span data-ttu-id="db90e-168">**/namespace:** \* \<nome>\*</span><span class="sxs-lookup"><span data-stu-id="db90e-168">**/namespace:** *\<name>*</span></span>|<span data-ttu-id="db90e-169">Specifica lo spazio dei nomi del codice generato.</span><span class="sxs-lookup"><span data-stu-id="db90e-169">Specifies namespace of the generated code.</span></span> <span data-ttu-id="db90e-170">Valore predefinito: nessuno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="db90e-170">Default value: no namespace.</span></span>|  
|<span data-ttu-id="db90e-171">**/context:** \* \<tipo>\*</span><span class="sxs-lookup"><span data-stu-id="db90e-171">**/context:** *\<type>*</span></span>|<span data-ttu-id="db90e-172">Specifica il nome della classe del contesto dati.</span><span class="sxs-lookup"><span data-stu-id="db90e-172">Specifies name of data context class.</span></span> <span data-ttu-id="db90e-173">Valore predefinito: derivato dal nome del database.</span><span class="sxs-lookup"><span data-stu-id="db90e-173">Default value: Derived from database name.</span></span>|  
|<span data-ttu-id="db90e-174">**/entitybase:** \* \<>del tipo\*</span><span class="sxs-lookup"><span data-stu-id="db90e-174">**/entitybase:** *\<type>*</span></span>|<span data-ttu-id="db90e-175">Specifica la classe base delle classi di entità nel codice generato.</span><span class="sxs-lookup"><span data-stu-id="db90e-175">Specifies the base class of the entity classes in the generated code.</span></span> <span data-ttu-id="db90e-176">Valore predefinito: le entità non dispongono di classe base.</span><span class="sxs-lookup"><span data-stu-id="db90e-176">Default value: Entities have no base class.</span></span>|  
|<span data-ttu-id="db90e-177">**/pluralize**</span><span class="sxs-lookup"><span data-stu-id="db90e-177">**/pluralize**</span></span>|<span data-ttu-id="db90e-178">Rende automaticamente plurali o singolari i nomi delle classi e dei membri.</span><span class="sxs-lookup"><span data-stu-id="db90e-178">Automatically pluralizes or singularizes class and member names.</span></span><br /><br /> <span data-ttu-id="db90e-179">Opzione disponibile solo nella versione in lingua inglese degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="db90e-179">This option is available only in the U.S. English version.</span></span>|  
|<span data-ttu-id="db90e-180">**/serialization:** \* \<>delle opzioni\*</span><span class="sxs-lookup"><span data-stu-id="db90e-180">**/serialization:** *\<option>*</span></span>|<span data-ttu-id="db90e-181">Genera classi serializzabili.</span><span class="sxs-lookup"><span data-stu-id="db90e-181">Generates serializable classes.</span></span><br /><br /> <span data-ttu-id="db90e-182">Opzione \* \<valida>\*: Nessuno, Unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="db90e-182">Valid *\<option>*: None, Unidirectional.</span></span> <span data-ttu-id="db90e-183">Valore predefinito: None.</span><span class="sxs-lookup"><span data-stu-id="db90e-183">Default value: None.</span></span><br /><br /> <span data-ttu-id="db90e-184">Per altre informazioni, vedere [Serializzazione](../data/adonet/sql/linq/serialization.md).</span><span class="sxs-lookup"><span data-stu-id="db90e-184">For more information, see [Serialization](../data/adonet/sql/linq/serialization.md).</span></span>|  
  
 <span data-ttu-id="db90e-185">**Input File**</span><span class="sxs-lookup"><span data-stu-id="db90e-185">**Input File**</span></span>  
  
|<span data-ttu-id="db90e-186">Opzione</span><span class="sxs-lookup"><span data-stu-id="db90e-186">Option</span></span>|<span data-ttu-id="db90e-187">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db90e-187">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="db90e-188">**\<>del file di input**</span><span class="sxs-lookup"><span data-stu-id="db90e-188">**\<input file>**</span></span>|<span data-ttu-id="db90e-189">Specifica un file con estensione mdf di SQL Server Express, un file con estensione sdf di SQL Server Compact 3.5 oppure un file con estensione dbml intermedio.</span><span class="sxs-lookup"><span data-stu-id="db90e-189">Specifies a SQL Server Express .mdf file, a SQL Server Compact 3.5 .sdf file, or a .dbml intermediate file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db90e-190">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="db90e-190">Remarks</span></span>  
 <span data-ttu-id="db90e-191">Il funzionamento di SqlMetal prevede di fatto due passaggi:</span><span class="sxs-lookup"><span data-stu-id="db90e-191">SqlMetal functionality actually involves two steps:</span></span>  
  
- <span data-ttu-id="db90e-192">Estrazione dei metadati del database in un file .dbml.</span><span class="sxs-lookup"><span data-stu-id="db90e-192">Extracting the metadata of the database into a .dbml file.</span></span>  
  
- <span data-ttu-id="db90e-193">Generazione di un file di output di codice.</span><span class="sxs-lookup"><span data-stu-id="db90e-193">Generating a code output file.</span></span>  
  
     <span data-ttu-id="db90e-194">Le opzioni della riga di comando, se usate correttamente, consentono di creare codice sorgente Visual Basic o C# oppure un file di mapping XML.</span><span class="sxs-lookup"><span data-stu-id="db90e-194">By using the appropriate command-line options, you can produce Visual Basic or C# source code, or you can produce an XML mapping file.</span></span>  
  
 <span data-ttu-id="db90e-195">Per estrarre i metadati da un file .mdf è necessario aggiungere il nome di tale file in coda a tutte le altre opzioni specificate.</span><span class="sxs-lookup"><span data-stu-id="db90e-195">To extract the metadata from an .mdf file, you must specify the name of the .mdf file after all other options.</span></span>  
  
 <span data-ttu-id="db90e-196">Se non è specificato alcun valore per **/server** , si presuppone che sia **localhost/sqlexpress** .</span><span class="sxs-lookup"><span data-stu-id="db90e-196">If no **/server** is specified, **localhost/sqlexpress** is assumed.</span></span>  
  
 <span data-ttu-id="db90e-197">Microsoft SQL Server 2005 genera un'eccezione se almeno una delle condizioni seguenti è vera:</span><span class="sxs-lookup"><span data-stu-id="db90e-197">Microsoft SQL Server 2005 throws an exception if one or more of the following conditions are true:</span></span>  
  
- <span data-ttu-id="db90e-198">SqlMetal tenta di estrarre una stored procedure che chiama se stessa.</span><span class="sxs-lookup"><span data-stu-id="db90e-198">SqlMetal tries to extract a stored procedure that calls itself.</span></span>  
  
- <span data-ttu-id="db90e-199">Il livello di annidamento di una stored procedure, di una funzione o di una vista è maggiore di 32.</span><span class="sxs-lookup"><span data-stu-id="db90e-199">The nesting level of a stored procedure, function, or view exceeds 32.</span></span>  
  
     <span data-ttu-id="db90e-200">SqlMetal rileva questa eccezione e la segnala come avviso.</span><span class="sxs-lookup"><span data-stu-id="db90e-200">SqlMetal catches this exception and reports it as a warning.</span></span>  
  
 <span data-ttu-id="db90e-201">Per specificare un nome file di input, aggiungere il nome nella riga di comando come file di input.</span><span class="sxs-lookup"><span data-stu-id="db90e-201">To specify an input file name, add the name to the command line as the input file.</span></span> <span data-ttu-id="db90e-202">Non è possibile includere il nome file nella stringa di connessione mediante l'opzione **/conn** .</span><span class="sxs-lookup"><span data-stu-id="db90e-202">Including the file name in the connection string (using the **/conn** option) is not supported.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="db90e-203">Esempi</span><span class="sxs-lookup"><span data-stu-id="db90e-203">Examples</span></span>  
 <span data-ttu-id="db90e-204">Genera un file .dbml che contiene metadati SQL estratti:</span><span class="sxs-lookup"><span data-stu-id="db90e-204">Generate a .dbml file that includes extracted SQL metadata:</span></span>  
  
 <span data-ttu-id="db90e-205">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span><span class="sxs-lookup"><span data-stu-id="db90e-205">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span></span>  
  
 <span data-ttu-id="db90e-206">Genera un file .dbml che contiene metadati SQL estratti da un file .mdf tramite SQL Server Express:</span><span class="sxs-lookup"><span data-stu-id="db90e-206">Generate a .dbml file that includes extracted SQL metadata from an .mdf file by using SQL Server Express:</span></span>  
  
 <span data-ttu-id="db90e-207">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span><span class="sxs-lookup"><span data-stu-id="db90e-207">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span></span>  
  
 <span data-ttu-id="db90e-208">Genera un file .dbml che contiene metadati SQL estratti da SQL Server Express:</span><span class="sxs-lookup"><span data-stu-id="db90e-208">Generate a .dbml file that includes extracted SQL metadata from SQL Server Express:</span></span>  
  
 <span data-ttu-id="db90e-209">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span><span class="sxs-lookup"><span data-stu-id="db90e-209">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span></span>  
  
 <span data-ttu-id="db90e-210">Genera codice sorgente a partire da un file di metadati .dmbl:</span><span class="sxs-lookup"><span data-stu-id="db90e-210">Generate source code from a .dbml metadata file:</span></span>  
  
 <span data-ttu-id="db90e-211">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span><span class="sxs-lookup"><span data-stu-id="db90e-211">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span></span>  
  
 <span data-ttu-id="db90e-212">Genera codice sorgente direttamente da metadati SQL:</span><span class="sxs-lookup"><span data-stu-id="db90e-212">Generate source code from SQL metadata directly:</span></span>  
  
 <span data-ttu-id="db90e-213">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span><span class="sxs-lookup"><span data-stu-id="db90e-213">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db90e-214">Quando si usa l'opzione **/pluralize** con il database di esempio Northwind, si verifica il comportamento seguente.</span><span class="sxs-lookup"><span data-stu-id="db90e-214">When you use the **/pluralize** option with the Northwind sample database, note the following behavior.</span></span> <span data-ttu-id="db90e-215">Quando SqlMetal crea nomi di tipo riga per le tabelle, i relativi nomi sono al singolare.</span><span class="sxs-lookup"><span data-stu-id="db90e-215">When SqlMetal makes row-type names for tables, the table names are singular.</span></span> <span data-ttu-id="db90e-216">Quando crea proprietà <xref:System.Data.Linq.DataContext> per le tabelle, i relativi nomi sono invece al plurale.</span><span class="sxs-lookup"><span data-stu-id="db90e-216">When it makes <xref:System.Data.Linq.DataContext> properties for tables, the table names are plural.</span></span> <span data-ttu-id="db90e-217">Per coincidenza, i nomi delle tabelle contenute nel database di esempio Northwind sono già al plurale.</span><span class="sxs-lookup"><span data-stu-id="db90e-217">Coincidentally, the tables in the Northwind sample database are already plural.</span></span> <span data-ttu-id="db90e-218">Pertanto, l'opzione di pluralizzazione di fatto non viene usata.</span><span class="sxs-lookup"><span data-stu-id="db90e-218">Therefore, you do not see that part working.</span></span> <span data-ttu-id="db90e-219">Di norma le tabelle di database vengono denominate al singolare, mentre le raccolte di .NET vengono denominate al plurale.</span><span class="sxs-lookup"><span data-stu-id="db90e-219">Although it is common practice to name database tables singular, it is also a common practice in .NET to name collections plural.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db90e-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db90e-220">See also</span></span>

- [<span data-ttu-id="db90e-221">Procedura: Generare il modello a oggetti in Visual Basic o C#</span><span class="sxs-lookup"><span data-stu-id="db90e-221">How to: Generate the Object Model in Visual Basic or C#</span></span>](../data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
- [<span data-ttu-id="db90e-222">Generazione di codice in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="db90e-222">Code Generation in LINQ to SQL</span></span>](../data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="db90e-223">Mapping esterno</span><span class="sxs-lookup"><span data-stu-id="db90e-223">External Mapping</span></span>](../data/adonet/sql/linq/external-mapping.md)

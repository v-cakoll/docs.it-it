---
title: Stringhe di connessione
ms.date: 12/13/2019
description: Parole chiave e valori supportati delle stringhe di connessione.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447013"
---
# <a name="connection-strings"></a><span data-ttu-id="ac1a9-103">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="ac1a9-103">Connection strings</span></span>

<span data-ttu-id="ac1a9-104">Una stringa di connessione viene utilizzata per specificare la modalità di connessione al database.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="ac1a9-105">Le stringhe di connessione in Microsoft. Data. sqlite seguono la [sintassi ADO.NET](../../../framework/data/adonet/connection-strings.md) standard come un elenco di parole chiave e valori delimitati da punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="ac1a9-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ac1a9-106">Keywords</span></span>

<span data-ttu-id="ac1a9-107">Con Microsoft. Data. SQLite è possibile usare le parole chiave della stringa di connessione seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac1a9-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="ac1a9-108">Origine dati</span><span class="sxs-lookup"><span data-stu-id="ac1a9-108">Data source</span></span>

<span data-ttu-id="ac1a9-109">Percorso del file di database.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-109">The path to the database file.</span></span> <span data-ttu-id="ac1a9-110">*DataSource* (senza spazio) e *filename* sono alias di questa parola chiave.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="ac1a9-111">SQLite considera i percorsi relativi alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="ac1a9-112">È anche possibile specificare percorsi assoluti.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="ac1a9-113">Se **vuoto**, SQLite crea un database su disco temporaneo che viene eliminato alla chiusura della connessione.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="ac1a9-114">Se `:memory:`, viene utilizzato un database in memoria.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="ac1a9-115">Per ulteriori informazioni, vedere [database in memoria](in-memory-databases.md).</span><span class="sxs-lookup"><span data-stu-id="ac1a9-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="ac1a9-116">I percorsi che iniziano con la stringa di sostituzione `|DataDirectory|` vengono considerati uguali ai percorsi relativi.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="ac1a9-117">Se impostata, i percorsi vengono eseguiti in relazione al valore della proprietà del dominio dell'applicazione DataDirectory.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="ac1a9-118">Questa parola chiave supporta anche i [nomi file URI](https://www.sqlite.org/uri.html).</span><span class="sxs-lookup"><span data-stu-id="ac1a9-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="ac1a9-119">Modalità</span><span class="sxs-lookup"><span data-stu-id="ac1a9-119">Mode</span></span>

<span data-ttu-id="ac1a9-120">Modalità di connessione.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-120">The connection mode.</span></span>

| <span data-ttu-id="ac1a9-121">Valore</span><span class="sxs-lookup"><span data-stu-id="ac1a9-121">Value</span></span>           | <span data-ttu-id="ac1a9-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac1a9-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ac1a9-123">ReadWriteCreate</span><span class="sxs-lookup"><span data-stu-id="ac1a9-123">ReadWriteCreate</span></span> | <span data-ttu-id="ac1a9-124">Apre il database per la lettura e la scrittura e lo crea se non esiste.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="ac1a9-125">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-125">This is the default.</span></span> |
| <span data-ttu-id="ac1a9-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ac1a9-126">ReadWrite</span></span>       | <span data-ttu-id="ac1a9-127">Apre il database per la lettura e la scrittura.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="ac1a9-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="ac1a9-128">ReadOnly</span></span>        | <span data-ttu-id="ac1a9-129">Apre il database in modalità di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="ac1a9-130">Memoria</span><span class="sxs-lookup"><span data-stu-id="ac1a9-130">Memory</span></span>          | <span data-ttu-id="ac1a9-131">Apre un database in memoria.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="ac1a9-132">Cache</span><span class="sxs-lookup"><span data-stu-id="ac1a9-132">Cache</span></span>

<span data-ttu-id="ac1a9-133">Modalità di memorizzazione nella cache utilizzata dalla connessione.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="ac1a9-134">Valore</span><span class="sxs-lookup"><span data-stu-id="ac1a9-134">Value</span></span>   | <span data-ttu-id="ac1a9-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac1a9-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ac1a9-136">Default</span><span class="sxs-lookup"><span data-stu-id="ac1a9-136">Default</span></span> | <span data-ttu-id="ac1a9-137">Usa la modalità predefinita della libreria SQLite sottostante.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="ac1a9-138">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-138">This is the default.</span></span>                   |
| <span data-ttu-id="ac1a9-139">Private</span><span class="sxs-lookup"><span data-stu-id="ac1a9-139">Private</span></span> | <span data-ttu-id="ac1a9-140">Ogni connessione utilizza una cache privata.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="ac1a9-141">Condivisa</span><span class="sxs-lookup"><span data-stu-id="ac1a9-141">Shared</span></span>  | <span data-ttu-id="ac1a9-142">Le connessioni condividono una cache.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-142">Connections share a cache.</span></span> <span data-ttu-id="ac1a9-143">Questa modalità può modificare il comportamento di blocco delle transazioni e della tabella.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="ac1a9-144">Password</span><span class="sxs-lookup"><span data-stu-id="ac1a9-144">Password</span></span>

<span data-ttu-id="ac1a9-145">Chiave di crittografia.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-145">The encryption key.</span></span> <span data-ttu-id="ac1a9-146">Se specificato, `PRAGMA key` viene inviato immediatamente dopo l'apertura della connessione.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="ac1a9-147">La password non ha alcun effetto se la crittografia non è supportata dalla libreria SQLite nativa.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="ac1a9-148">Chiavi esterne</span><span class="sxs-lookup"><span data-stu-id="ac1a9-148">Foreign Keys</span></span>

<span data-ttu-id="ac1a9-149">Valore che indica se abilitare i vincoli di chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="ac1a9-150">Valore</span><span class="sxs-lookup"><span data-stu-id="ac1a9-150">Value</span></span>   | <span data-ttu-id="ac1a9-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac1a9-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="ac1a9-152">True</span><span class="sxs-lookup"><span data-stu-id="ac1a9-152">True</span></span>    | <span data-ttu-id="ac1a9-153">Invia `PRAGMA foreign_keys = 1` immediatamente dopo l'apertura della connessione.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="ac1a9-154">Falso</span><span class="sxs-lookup"><span data-stu-id="ac1a9-154">False</span></span>   | <span data-ttu-id="ac1a9-155">Invia `PRAGMA foreign_keys = 0` immediatamente dopo l'apertura della connessione.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="ac1a9-156">(vuoto)</span><span class="sxs-lookup"><span data-stu-id="ac1a9-156">(empty)</span></span> | <span data-ttu-id="ac1a9-157">Non invia `PRAGMA foreign_keys`.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="ac1a9-158">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-158">This is the default.</span></span> |

<span data-ttu-id="ac1a9-159">Non è necessario abilitare le chiavi esterne se, come in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS è stato usato per compilare la libreria SQLite nativa.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="ac1a9-160">Trigger ricorsivi</span><span class="sxs-lookup"><span data-stu-id="ac1a9-160">Recursive triggers</span></span>

<span data-ttu-id="ac1a9-161">Valore che indica se abilitare i trigger ricorsivi.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="ac1a9-162">Valore</span><span class="sxs-lookup"><span data-stu-id="ac1a9-162">Value</span></span> | <span data-ttu-id="ac1a9-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac1a9-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="ac1a9-164">True</span><span class="sxs-lookup"><span data-stu-id="ac1a9-164">True</span></span>  | <span data-ttu-id="ac1a9-165">Invia `PRAGMA recursive_triggers` immediatamente dopo l'apertura della connessione.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="ac1a9-166">Falso</span><span class="sxs-lookup"><span data-stu-id="ac1a9-166">False</span></span> | <span data-ttu-id="ac1a9-167">Non invia `PRAGMA recursive_triggers`.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="ac1a9-168">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="ac1a9-169">Generatore di stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="ac1a9-169">Connection string builder</span></span>

<span data-ttu-id="ac1a9-170">È possibile utilizzare <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> come modo fortemente tipizzato per la creazione di stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="ac1a9-171">Può anche essere usato per impedire attacchi injection alla stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="ac1a9-172">Esempi</span><span class="sxs-lookup"><span data-stu-id="ac1a9-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="ac1a9-173">Basic</span><span class="sxs-lookup"><span data-stu-id="ac1a9-173">Basic</span></span>

<span data-ttu-id="ac1a9-174">Stringa di connessione di base con una cache condivisa per una maggiore concorrenza.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="ac1a9-175">Crittografato</span><span class="sxs-lookup"><span data-stu-id="ac1a9-175">Encrypted</span></span>

<span data-ttu-id="ac1a9-176">Un database crittografato.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="ac1a9-177">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ac1a9-177">Read-only</span></span>

<span data-ttu-id="ac1a9-178">Un database di sola lettura che non può essere modificato dall'app.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="ac1a9-179">In memoria</span><span class="sxs-lookup"><span data-stu-id="ac1a9-179">In-memory</span></span>

<span data-ttu-id="ac1a9-180">Un database privato in memoria.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="ac1a9-181">Condivisibile in memoria</span><span class="sxs-lookup"><span data-stu-id="ac1a9-181">Sharable in-memory</span></span>

<span data-ttu-id="ac1a9-182">Un database condivisibile in memoria identificato dal nome *condivisibile*.</span><span class="sxs-lookup"><span data-stu-id="ac1a9-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="ac1a9-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac1a9-183">See also</span></span>

* [<span data-ttu-id="ac1a9-184">Stringhe di connessione in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ac1a9-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="ac1a9-185">Database in memoria</span><span class="sxs-lookup"><span data-stu-id="ac1a9-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="ac1a9-186">Transazioni</span><span class="sxs-lookup"><span data-stu-id="ac1a9-186">Transactions</span></span>](transactions.md)

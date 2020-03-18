---
title: Stringhe di connessione
ms.date: 12/13/2019
description: Parole chiave supportate e valori delle stringhe di connessione.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400449"
---
# <a name="connection-strings"></a><span data-ttu-id="441c6-103">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="441c6-103">Connection strings</span></span>

<span data-ttu-id="441c6-104">Una stringa di connessione viene utilizzata per specificare come connettersi al database.</span><span class="sxs-lookup"><span data-stu-id="441c6-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="441c6-105">Le stringhe di connessione in Microsoft.Data.Sqlite seguono la [sintassi standard ADO.NET](../../../framework/data/adonet/connection-strings.md) come elenco separato da punti e virgola di parole chiave e valori.</span><span class="sxs-lookup"><span data-stu-id="441c6-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="441c6-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="441c6-106">Keywords</span></span>

<span data-ttu-id="441c6-107">Le parole chiave della stringa di connessione seguenti possono essere utilizzate con Microsoft.Data.Sqlite:The following connection string keywords can be used with Microsoft.Data.Sqlite:</span><span class="sxs-lookup"><span data-stu-id="441c6-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="441c6-108">Origine dati</span><span class="sxs-lookup"><span data-stu-id="441c6-108">Data source</span></span>

<span data-ttu-id="441c6-109">Percorso del file di database.</span><span class="sxs-lookup"><span data-stu-id="441c6-109">The path to the database file.</span></span> <span data-ttu-id="441c6-110">*DataSource* (senza spazi) e *Filename* sono alias di questa parola chiave.</span><span class="sxs-lookup"><span data-stu-id="441c6-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="441c6-111">SQLite considera i percorsi relativi alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="441c6-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="441c6-112">È inoltre possibile specificare percorsi assoluti.</span><span class="sxs-lookup"><span data-stu-id="441c6-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="441c6-113">Se **vuoto**, SQLite crea un database temporaneo su disco che viene eliminato quando la connessione viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="441c6-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="441c6-114">Se `:memory:`è , viene utilizzato un database in memoria.</span><span class="sxs-lookup"><span data-stu-id="441c6-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="441c6-115">Per ulteriori informazioni, vedere [Database in memoria](in-memory-databases.md).</span><span class="sxs-lookup"><span data-stu-id="441c6-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="441c6-116">I percorsi `|DataDirectory|` che iniziano con la stringa di sostituzione vengono considerati allo stesso modo dei percorsi relativi.</span><span class="sxs-lookup"><span data-stu-id="441c6-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="441c6-117">Se impostato, i percorsi vengono resi relativi al valore della proprietà del dominio applicazione DataDirectory.</span><span class="sxs-lookup"><span data-stu-id="441c6-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="441c6-118">Questa parola chiave supporta anche [URI Filenames](https://www.sqlite.org/uri.html).</span><span class="sxs-lookup"><span data-stu-id="441c6-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="441c6-119">Mode</span><span class="sxs-lookup"><span data-stu-id="441c6-119">Mode</span></span>

<span data-ttu-id="441c6-120">Modalità di connessione.</span><span class="sxs-lookup"><span data-stu-id="441c6-120">The connection mode.</span></span>

| <span data-ttu-id="441c6-121">valore</span><span class="sxs-lookup"><span data-stu-id="441c6-121">Value</span></span>           | <span data-ttu-id="441c6-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="441c6-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="441c6-123">ReadWriteCreate</span><span class="sxs-lookup"><span data-stu-id="441c6-123">ReadWriteCreate</span></span> | <span data-ttu-id="441c6-124">Apre il database per la lettura e la scrittura e lo crea se non esiste.</span><span class="sxs-lookup"><span data-stu-id="441c6-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="441c6-125">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="441c6-125">This is the default.</span></span> |
| <span data-ttu-id="441c6-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="441c6-126">ReadWrite</span></span>       | <span data-ttu-id="441c6-127">Apre il database per la lettura e la scrittura.</span><span class="sxs-lookup"><span data-stu-id="441c6-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="441c6-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="441c6-128">ReadOnly</span></span>        | <span data-ttu-id="441c6-129">Apre il database in modalità di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="441c6-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="441c6-130">Memoria</span><span class="sxs-lookup"><span data-stu-id="441c6-130">Memory</span></span>          | <span data-ttu-id="441c6-131">Apre un database in memoria.</span><span class="sxs-lookup"><span data-stu-id="441c6-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="441c6-132">Cache</span><span class="sxs-lookup"><span data-stu-id="441c6-132">Cache</span></span>

<span data-ttu-id="441c6-133">Modalità di memorizzazione nella cache utilizzata dalla connessione.</span><span class="sxs-lookup"><span data-stu-id="441c6-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="441c6-134">valore</span><span class="sxs-lookup"><span data-stu-id="441c6-134">Value</span></span>   | <span data-ttu-id="441c6-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="441c6-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="441c6-136">Predefinito</span><span class="sxs-lookup"><span data-stu-id="441c6-136">Default</span></span> | <span data-ttu-id="441c6-137">Utilizza la modalità predefinita della libreria SQLite sottostante.</span><span class="sxs-lookup"><span data-stu-id="441c6-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="441c6-138">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="441c6-138">This is the default.</span></span>                   |
| <span data-ttu-id="441c6-139">Privato</span><span class="sxs-lookup"><span data-stu-id="441c6-139">Private</span></span> | <span data-ttu-id="441c6-140">Ogni connessione utilizza una cache privata.</span><span class="sxs-lookup"><span data-stu-id="441c6-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="441c6-141">Condiviso</span><span class="sxs-lookup"><span data-stu-id="441c6-141">Shared</span></span>  | <span data-ttu-id="441c6-142">Le connessioni condividono una cache.</span><span class="sxs-lookup"><span data-stu-id="441c6-142">Connections share a cache.</span></span> <span data-ttu-id="441c6-143">Questa modalità può modificare il comportamento delle transazioni e del blocco delle tabelle.</span><span class="sxs-lookup"><span data-stu-id="441c6-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="441c6-144">Password</span><span class="sxs-lookup"><span data-stu-id="441c6-144">Password</span></span>

<span data-ttu-id="441c6-145">Chiave di crittografia.</span><span class="sxs-lookup"><span data-stu-id="441c6-145">The encryption key.</span></span> <span data-ttu-id="441c6-146">Se specificato, `PRAGMA key` viene inviato immediatamente dopo l'apertura della connessione.</span><span class="sxs-lookup"><span data-stu-id="441c6-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="441c6-147">La password non ha effetto quando la crittografia non è supportata dalla libreria SQLite nativa.</span><span class="sxs-lookup"><span data-stu-id="441c6-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="441c6-148">Chiavi esterne</span><span class="sxs-lookup"><span data-stu-id="441c6-148">Foreign Keys</span></span>

<span data-ttu-id="441c6-149">Valore che indica se abilitare i vincoli di chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="441c6-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="441c6-150">valore</span><span class="sxs-lookup"><span data-stu-id="441c6-150">Value</span></span>   | <span data-ttu-id="441c6-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="441c6-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="441c6-152">True </span><span class="sxs-lookup"><span data-stu-id="441c6-152">True</span></span>    | <span data-ttu-id="441c6-153">Invia `PRAGMA foreign_keys = 1` subito dopo l'apertura della connessione.</span><span class="sxs-lookup"><span data-stu-id="441c6-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="441c6-154">False</span><span class="sxs-lookup"><span data-stu-id="441c6-154">False</span></span>   | <span data-ttu-id="441c6-155">Invia `PRAGMA foreign_keys = 0` subito dopo l'apertura della connessione.</span><span class="sxs-lookup"><span data-stu-id="441c6-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="441c6-156">(vuoto)</span><span class="sxs-lookup"><span data-stu-id="441c6-156">(empty)</span></span> | <span data-ttu-id="441c6-157">Non invia `PRAGMA foreign_keys`.</span><span class="sxs-lookup"><span data-stu-id="441c6-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="441c6-158">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="441c6-158">This is the default.</span></span> |

<span data-ttu-id="441c6-159">Non è necessario abilitare le chiavi esterne se, come in e_sqlite3, è stato usato SQLITE_DEFAULT_FOREIGN_KEYS per compilare la libreria SQLite nativa.</span><span class="sxs-lookup"><span data-stu-id="441c6-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="441c6-160">Trigger ricorsivi</span><span class="sxs-lookup"><span data-stu-id="441c6-160">Recursive triggers</span></span>

<span data-ttu-id="441c6-161">Valore che indica se abilitare i trigger ricorsivi.</span><span class="sxs-lookup"><span data-stu-id="441c6-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="441c6-162">valore</span><span class="sxs-lookup"><span data-stu-id="441c6-162">Value</span></span> | <span data-ttu-id="441c6-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="441c6-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="441c6-164">True </span><span class="sxs-lookup"><span data-stu-id="441c6-164">True</span></span>  | <span data-ttu-id="441c6-165">Invia `PRAGMA recursive_triggers` subito dopo l'apertura della connessione.</span><span class="sxs-lookup"><span data-stu-id="441c6-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="441c6-166">False</span><span class="sxs-lookup"><span data-stu-id="441c6-166">False</span></span> | <span data-ttu-id="441c6-167">Non invia `PRAGMA recursive_triggers`.</span><span class="sxs-lookup"><span data-stu-id="441c6-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="441c6-168">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="441c6-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="441c6-169">Generatore di stringhe di connessioneConnection string builder</span><span class="sxs-lookup"><span data-stu-id="441c6-169">Connection string builder</span></span>

<span data-ttu-id="441c6-170">È possibile <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> utilizzare un modo fortemente tipizzato di creare stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="441c6-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="441c6-171">Può anche essere utilizzato per prevenire attacchi di iniezione stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="441c6-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="441c6-172">Esempi</span><span class="sxs-lookup"><span data-stu-id="441c6-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="441c6-173">Basic</span><span class="sxs-lookup"><span data-stu-id="441c6-173">Basic</span></span>

<span data-ttu-id="441c6-174">Stringa di connessione di base con una cache condivisa per una migliore concorrenza.</span><span class="sxs-lookup"><span data-stu-id="441c6-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="441c6-175">Crittografato</span><span class="sxs-lookup"><span data-stu-id="441c6-175">Encrypted</span></span>

<span data-ttu-id="441c6-176">Un database crittografato.</span><span class="sxs-lookup"><span data-stu-id="441c6-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="441c6-177">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="441c6-177">Read-only</span></span>

<span data-ttu-id="441c6-178">Database di sola lettura che non può essere modificato dall'app.</span><span class="sxs-lookup"><span data-stu-id="441c6-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="441c6-179">In memoria</span><span class="sxs-lookup"><span data-stu-id="441c6-179">In-memory</span></span>

<span data-ttu-id="441c6-180">Un database privato in memoria.</span><span class="sxs-lookup"><span data-stu-id="441c6-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="441c6-181">Sharable in-memory</span><span class="sxs-lookup"><span data-stu-id="441c6-181">Sharable in-memory</span></span>

<span data-ttu-id="441c6-182">Database condivisibili e in memoria identificato con il nome *Sharable*.</span><span class="sxs-lookup"><span data-stu-id="441c6-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="441c6-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="441c6-183">See also</span></span>

* [<span data-ttu-id="441c6-184">Stringhe di connessione in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="441c6-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="441c6-185">Database in memoria</span><span class="sxs-lookup"><span data-stu-id="441c6-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="441c6-186">Transazioni</span><span class="sxs-lookup"><span data-stu-id="441c6-186">Transactions</span></span>](transactions.md)

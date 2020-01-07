---
title: Errori di database
ms.date: 12/13/2019
description: Viene descritto il modo in cui gli errori e i ritiri del database vengono gestiti dalla libreria.
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447272"
---
# <a name="database-errors"></a><span data-ttu-id="80403-103">Errori di database</span><span class="sxs-lookup"><span data-stu-id="80403-103">Database errors</span></span>

<span data-ttu-id="80403-104"><xref:Microsoft.Data.Sqlite.SqliteException> viene generata quando viene rilevato un errore SQLite.</span><span class="sxs-lookup"><span data-stu-id="80403-104"><xref:Microsoft.Data.Sqlite.SqliteException> is thrown when a SQLite error is encountered.</span></span> <span data-ttu-id="80403-105">Il messaggio viene fornito da SQLite.</span><span class="sxs-lookup"><span data-stu-id="80403-105">The message is provided by SQLite.</span></span> <span data-ttu-id="80403-106">Le proprietà `SqliteErrorCode` e `SqliteExtendedErrorCode` contengono il [codice di risultato](https://www.sqlite.org/rescode.html) SQLite dell'errore.</span><span class="sxs-lookup"><span data-stu-id="80403-106">The `SqliteErrorCode` and `SqliteExtendedErrorCode` properties contain the SQLite [result code](https://www.sqlite.org/rescode.html) of the error.</span></span>

<span data-ttu-id="80403-107">Gli errori possono essere rilevati ogni volta che Microsoft. Data. sqlite interagisce con la libreria SQLite nativa.</span><span class="sxs-lookup"><span data-stu-id="80403-107">Errors may be encountered any time the Microsoft.Data.Sqlite interacts with the native SQLite library.</span></span> <span data-ttu-id="80403-108">Nell'elenco seguente vengono illustrati gli scenari comuni in cui possono verificarsi errori:</span><span class="sxs-lookup"><span data-stu-id="80403-108">The following list shows the common scenarios where errors can occur:</span></span>

* <span data-ttu-id="80403-109">Apertura di una connessione.</span><span class="sxs-lookup"><span data-stu-id="80403-109">Opening a connection.</span></span>
* <span data-ttu-id="80403-110">Inizio di una transazione.</span><span class="sxs-lookup"><span data-stu-id="80403-110">Beginning a transaction.</span></span>
* <span data-ttu-id="80403-111">Esecuzione di un comando.</span><span class="sxs-lookup"><span data-stu-id="80403-111">Executing a command.</span></span>
* <span data-ttu-id="80403-112">Chiamata del metodo <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.</span><span class="sxs-lookup"><span data-stu-id="80403-112">Calling <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.</span></span>

<span data-ttu-id="80403-113">Valutare attentamente il modo in cui l'app gestirà questi errori.</span><span class="sxs-lookup"><span data-stu-id="80403-113">Consider carefully how your app will handle these errors.</span></span>

## <a name="locking-retries-and-timeouts"></a><span data-ttu-id="80403-114">Blocco, tentativi e timeout</span><span class="sxs-lookup"><span data-stu-id="80403-114">Locking, retries, and timeouts</span></span>

<span data-ttu-id="80403-115">SQLite è molto aggressivo quando si tratta di tabelle di blocco e di file di database.</span><span class="sxs-lookup"><span data-stu-id="80403-115">SQLite is aggressive when it comes to locking tables and database files.</span></span> <span data-ttu-id="80403-116">Se l'app consente l'accesso a un database simultaneo, è probabile che si verifichino errori di occupato e bloccato.</span><span class="sxs-lookup"><span data-stu-id="80403-116">If your app enables any concurrent database access, you'll likely encounter busy and locked errors.</span></span> <span data-ttu-id="80403-117">È possibile attenuare molti errori usando una [cache condivisa](connection-strings.md#cache) e una [registrazione write-ahead](async.md).</span><span class="sxs-lookup"><span data-stu-id="80403-117">You can mitigate many errors by using a [shared cache](connection-strings.md#cache) and [write-ahead logging](async.md).</span></span>

<span data-ttu-id="80403-118">Ogni volta che Microsoft. Data. sqlite rileva un errore occupato o bloccato, verrà ritentato automaticamente finché non avrà esito positivo o verrà raggiunto il timeout del comando.</span><span class="sxs-lookup"><span data-stu-id="80403-118">Whenever Microsoft.Data.Sqlite encounters a busy or locked error, it will automatically retry until it succeeds or the command timeout is reached.</span></span>

<span data-ttu-id="80403-119">È possibile aumentare il timeout del comando impostando <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>.</span><span class="sxs-lookup"><span data-stu-id="80403-119">You can increase the timeout of command by setting <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>.</span></span> <span data-ttu-id="80403-120">Il timeout predefinito è 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="80403-120">The default timeout is 30 seconds.</span></span> <span data-ttu-id="80403-121">Il valore `0` indica nessun timeout.</span><span class="sxs-lookup"><span data-stu-id="80403-121">A value of `0` means no timeout.</span></span>

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

<span data-ttu-id="80403-122">Microsoft. Data. sqlite a volte deve creare un oggetto comando implicito.</span><span class="sxs-lookup"><span data-stu-id="80403-122">Microsoft.Data.Sqlite sometimes needs to create an implicit command object.</span></span> <span data-ttu-id="80403-123">Ad esempio, durante BeginTransaction.</span><span class="sxs-lookup"><span data-stu-id="80403-123">For example, during BeginTransaction.</span></span> <span data-ttu-id="80403-124">Per impostare il timeout per questi comandi, utilizzare <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.</span><span class="sxs-lookup"><span data-stu-id="80403-124">To set the timeout for these commands, use <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.</span></span>

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a><span data-ttu-id="80403-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80403-125">See also</span></span>

* [<span data-ttu-id="80403-126">Codici di errore SQLite</span><span class="sxs-lookup"><span data-stu-id="80403-126">SQLite Error Codes</span></span>](https://www.sqlite.org/rescode.html)
* [<span data-ttu-id="80403-127">Blocco di file in SQLite</span><span class="sxs-lookup"><span data-stu-id="80403-127">File Locking In SQLite</span></span>](https://www.sqlite.org/lockingv3.html)
* [<span data-ttu-id="80403-128">Modalità cache condivisa</span><span class="sxs-lookup"><span data-stu-id="80403-128">Shared-Cache Mode</span></span>](https://www.sqlite.org/sharedcache.html)
* [<span data-ttu-id="80403-129">Registrazione write-ahead</span><span class="sxs-lookup"><span data-stu-id="80403-129">Write-Ahead Logging</span></span>](https://www.sqlite.org/wal.html)

---
title: Statistiche di provider per SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 429c9d09-92ac-46ec-829a-fbff0a9575a2
ms.openlocfilehash: 5e37a04ff731a99664d636e0d4175f99214c2646
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174511"
---
# <a name="provider-statistics-for-sql-server"></a><span data-ttu-id="d3d52-102">Statistiche di provider per SQL Server</span><span class="sxs-lookup"><span data-stu-id="d3d52-102">Provider Statistics for SQL Server</span></span>
<span data-ttu-id="d3d52-103">A partire da .NET Framework versione 2.0, il provider di dati .NET Framework per SQL Server supporta le statistiche in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d3d52-103">Starting with the .NET Framework version 2.0, the .NET Framework Data Provider for SQL Server supports run-time statistics.</span></span> <span data-ttu-id="d3d52-104">Le statistiche devono essere abilitate impostando la proprietà <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> dell'oggetto <xref:System.Data.SqlClient.SqlConnection> su `True` dopo aver creato un oggetto connessione valido.</span><span class="sxs-lookup"><span data-stu-id="d3d52-104">You must enable statistics by setting the <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> property of the <xref:System.Data.SqlClient.SqlConnection> object to `True` after you have a valid connection object created.</span></span> <span data-ttu-id="d3d52-105">Una volta abilitate le statistiche, è possibile esaminarle come "snapshot in un dato momento" recuperando un riferimento <xref:System.Collections.IDictionary> tramite il metodo <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> dell'oggetto <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="d3d52-105">After statistics are enabled, you can review them as a "snapshot in time" by retrieving an <xref:System.Collections.IDictionary> reference via the <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="d3d52-106">È possibile enumerare l'elenco come un set di voci del dizionario delle coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="d3d52-106">You enumerate through the list as a set of name/value pair dictionary entries.</span></span> <span data-ttu-id="d3d52-107">Queste coppie nome/valore non sono ordinate.</span><span class="sxs-lookup"><span data-stu-id="d3d52-107">These name/value pairs are unordered.</span></span> <span data-ttu-id="d3d52-108">In qualsiasi momento è possibile chiamare il metodo <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> dell'oggetto <xref:System.Data.SqlClient.SqlConnection> per reimpostare i contatori.</span><span class="sxs-lookup"><span data-stu-id="d3d52-108">At any time, you can call the <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object to reset the counters.</span></span> <span data-ttu-id="d3d52-109">Se la raccolta delle statistiche non è stata abilitata, non viene generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="d3d52-109">If statistic gathering has not been enabled, an exception is not generated.</span></span> <span data-ttu-id="d3d52-110">Inoltre, se <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> viene chiamato senza che prima sia stato chiamato <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A>, i valori recuperati sono i valori iniziali per ogni voce.</span><span class="sxs-lookup"><span data-stu-id="d3d52-110">In addition, if <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> is called without <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> having been called first, the values retrieved are the initial values for each entry.</span></span> <span data-ttu-id="d3d52-111">Se si abilitano le statistiche, si esegue l'applicazione per un periodo di tempo e si disabilitano le statistiche, i valori recuperati rifletteranno i valori raccolti fino al punto in cui le statistiche sono state disabilitate.</span><span class="sxs-lookup"><span data-stu-id="d3d52-111">If you enable statistics, run your application for a while, and then disable statistics, the values retrieved will reflect the values collected up to the point where statistics were disabled.</span></span> <span data-ttu-id="d3d52-112">Tutti i valori statistici raccolti sono in base alla connessione.</span><span class="sxs-lookup"><span data-stu-id="d3d52-112">All statistical values gathered are on a per-connection basis.</span></span>  
  
## <a name="statistical-values-available"></a><span data-ttu-id="d3d52-113">Valori statistici disponibili</span><span class="sxs-lookup"><span data-stu-id="d3d52-113">Statistical Values Available</span></span>  
 <span data-ttu-id="d3d52-114">Attualmente il provider Microsoft SQL Server mette a disposizione 18 elementi diversi.</span><span class="sxs-lookup"><span data-stu-id="d3d52-114">Currently there are 18 different items available from the Microsoft SQL Server provider.</span></span> <span data-ttu-id="d3d52-115">È possibile accedere alle voci disponibili tramite la proprietà **Count** del riferimento dell'interfaccia <xref:System.Collections.IDictionary> restituito da <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3d52-115">The number of items available can be accessed via the **Count** property of the <xref:System.Collections.IDictionary> interface reference returned by <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>.</span></span> <span data-ttu-id="d3d52-116">Tutti i contatori delle statistiche del provider usano il tipo <xref:System.Int64> di Common Language Runtime (**long** in C# e Visual Basic), da 64 bit.</span><span class="sxs-lookup"><span data-stu-id="d3d52-116">All of the counters for provider statistics use the common language runtime <xref:System.Int64> type (**long** in C# and Visual Basic), which is 64 bits wide.</span></span> <span data-ttu-id="d3d52-117">Il valore massimo del tipo di dati **int64**, definito dal campo **int64.MaxValue**, è ((2^63)-1)).</span><span class="sxs-lookup"><span data-stu-id="d3d52-117">The maximum value of the **int64** data type, as defined by the **int64.MaxValue** field, is ((2^63)-1)).</span></span> <span data-ttu-id="d3d52-118">Quando i valori per i contatori raggiungono questo valore massimo, non vengono più considerati accurati.</span><span class="sxs-lookup"><span data-stu-id="d3d52-118">When the values for the counters reach this maximum value, they should no longer be considered accurate.</span></span> <span data-ttu-id="d3d52-119">Ciò significa che **int64.MaxValue**-1((2^63)-2) è realmente il valore massimo valido per le statistiche.</span><span class="sxs-lookup"><span data-stu-id="d3d52-119">This means that **int64.MaxValue**-1((2^63)-2) is effectively the greatest valid value for any statistic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3d52-120">Viene usato un dizionario per restituire le statistiche del provider poiché il numero, i nomi e l'ordine delle statistiche restituite in futuro possono cambiare.</span><span class="sxs-lookup"><span data-stu-id="d3d52-120">A dictionary is used for returning provider statistics because the number, names and order of the returned statistics may change in the future.</span></span> <span data-ttu-id="d3d52-121">Le applicazioni non devono basarsi su un valore specifico trovato nel dizionario, ma devono invece verificare se il valore è presente e di conseguenza creare un ramo.</span><span class="sxs-lookup"><span data-stu-id="d3d52-121">Applications should not rely on a specific value being found in the dictionary, but should instead check whether the value is there and branch accordingly.</span></span>  
  
 <span data-ttu-id="d3d52-122">Nella tabella seguente vengono descritti i valori statistici correnti disponibili.</span><span class="sxs-lookup"><span data-stu-id="d3d52-122">The following table describes the current statistical values available.</span></span> <span data-ttu-id="d3d52-123">Si noti che i nomi delle chiavi per i singoli valori non sono localizzati nelle versioni internazionali di Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d3d52-123">Note that the key names for the individual values are not localized across regional versions of the Microsoft .NET Framework.</span></span>  
  
|<span data-ttu-id="d3d52-124">Nome chiave</span><span class="sxs-lookup"><span data-stu-id="d3d52-124">Key Name</span></span>|<span data-ttu-id="d3d52-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3d52-125">Description</span></span>|  
|--------------|-----------------|  
|`BuffersReceived`|<span data-ttu-id="d3d52-126">Restituisce il numero di pacchetti di flusso TDS (Tabular Data Stream) ricevuti dal provider da SQL Server dopo che l'applicazione è stata avviata usando il provider e con le statistiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="d3d52-126">Returns the number of tabular data stream (TDS) packets received by the provider from SQL Server after the application has started using the provider and has enabled statistics.</span></span>|  
|`BuffersSent`|<span data-ttu-id="d3d52-127">Restituisce il numero di pacchetti di flusso TDS inviati a SQL Server dal provider dopo che sono state abilitate le statistiche.</span><span class="sxs-lookup"><span data-stu-id="d3d52-127">Returns the number of TDS packets sent to SQL Server by the provider after statistics have been enabled.</span></span> <span data-ttu-id="d3d52-128">I comandi di grandi dimensioni possono richiedere più buffer.</span><span class="sxs-lookup"><span data-stu-id="d3d52-128">Large commands can require multiple buffers.</span></span> <span data-ttu-id="d3d52-129">Se, ad esempio, un comando di grandi dimensioni viene inviato al server e richiede sei pacchetti, `ServerRoundtrips` viene incrementato di uno e `BuffersSent` viene incrementato di sei.</span><span class="sxs-lookup"><span data-stu-id="d3d52-129">For example, if a large command is sent to the server and it requires six packets, `ServerRoundtrips` is incremented by one and `BuffersSent` is incremented by six.</span></span>|  
|`BytesReceived`|<span data-ttu-id="d3d52-130">Restituisce il numero di byte di dati nei pacchetti di flusso TDS ricevuti dal provider da SQL Server dopo che l'applicazione è stata avviata usando il provider e con le statistiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="d3d52-130">Returns the number of bytes of data in the TDS packets received by the provider from SQL Server once the application has started using the provider and has enabled statistics.</span></span>|  
|`BytesSent`|<span data-ttu-id="d3d52-131">Restituisce il numero di byte di dati inviati a SQL Server nei pacchetti di flusso TDS dopo che l'applicazione è stata avviata usando il provider e con le statistiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="d3d52-131">Returns the number of bytes of data sent to SQL Server in TDS packets after the application has started using the provider and has enabled statistics.</span></span>|  
|`ConnectionTime`|<span data-ttu-id="d3d52-132">Il periodo di tempo (in millisecondi) durante il quale la connessione è stata aperta dopo l'abilitazione delle statistiche (tempo di connessione totale se le statistiche sono state abilitate prima di aprire la connessione).</span><span class="sxs-lookup"><span data-stu-id="d3d52-132">The amount of time (in milliseconds) that the connection has been opened after statistics have been enabled (total connection time if statistics were enabled before opening the connection).</span></span>|  
|`CursorOpens`|<span data-ttu-id="d3d52-133">Restituisce il numero di volte in cui un cursore è stato aperto, per la durata della connessione, dopo che l'applicazione è stata avviata usando il provider e con le statistiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="d3d52-133">Returns the number of times a cursor was open through the connection once the application has started using the provider and has enabled statistics.</span></span><br /><br /> <span data-ttu-id="d3d52-134">Si noti che i risultati di sola lettura o di solo invio restituiti dalle istruzioni SELECT non sono considerati cursori e pertanto non influiscono su questo contatore.</span><span class="sxs-lookup"><span data-stu-id="d3d52-134">Note that read-only/forward-only results returned by SELECT statements are not considered cursors and thus do not affect this counter.</span></span>|  
|`ExecutionTime`|<span data-ttu-id="d3d52-135">Restituisce l'intervallo di tempo cumulativo (in millisecondi) usato dal provider per l'elaborazione dopo l'abilitazione delle statistiche, incluso il tempo di attesa per le risposte del server nonché il tempo di esecuzione del codice nel provider stesso.</span><span class="sxs-lookup"><span data-stu-id="d3d52-135">Returns the cumulative amount of time (in milliseconds) that the provider has spent processing once statistics have been enabled, including the time spent waiting for replies from the server as well as the time spent executing code in the provider itself.</span></span><br /><br /> <span data-ttu-id="d3d52-136">Le classi che includono il codice temporale sono:</span><span class="sxs-lookup"><span data-stu-id="d3d52-136">The classes that include timing code are:</span></span><br /><br /> <span data-ttu-id="d3d52-137">SqlConnection</span><span class="sxs-lookup"><span data-stu-id="d3d52-137">SqlConnection</span></span><br /><br /> <span data-ttu-id="d3d52-138">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="d3d52-138">SqlCommand</span></span><br /><br /> <span data-ttu-id="d3d52-139">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="d3d52-139">SqlDataReader</span></span><br /><br /> <span data-ttu-id="d3d52-140">SqlDataAdapter</span><span class="sxs-lookup"><span data-stu-id="d3d52-140">SqlDataAdapter</span></span><br /><br /> <span data-ttu-id="d3d52-141">SqlTransaction</span><span class="sxs-lookup"><span data-stu-id="d3d52-141">SqlTransaction</span></span><br /><br /> <span data-ttu-id="d3d52-142">SqlCommandBuilder</span><span class="sxs-lookup"><span data-stu-id="d3d52-142">SqlCommandBuilder</span></span><br /><br /> <span data-ttu-id="d3d52-143">Per ridurre il più possibile i membri critici per le prestazioni, i membri seguenti non sono temporizzati:</span><span class="sxs-lookup"><span data-stu-id="d3d52-143">To keep performance-critical members as small as possible, the following members are not timed:</span></span><br /><br /> <span data-ttu-id="d3d52-144">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="d3d52-144">SqlDataReader</span></span><br /><br /> <span data-ttu-id="d3d52-145">this[] operator (all overloads)</span><span class="sxs-lookup"><span data-stu-id="d3d52-145">this[] operator (all overloads)</span></span><br /><br /> <span data-ttu-id="d3d52-146">GetBoolean</span><span class="sxs-lookup"><span data-stu-id="d3d52-146">GetBoolean</span></span><br /><br /> <span data-ttu-id="d3d52-147">GetChar</span><span class="sxs-lookup"><span data-stu-id="d3d52-147">GetChar</span></span><br /><br /> <span data-ttu-id="d3d52-148">GetDateTime</span><span class="sxs-lookup"><span data-stu-id="d3d52-148">GetDateTime</span></span><br /><br /> <span data-ttu-id="d3d52-149">GetDecimal</span><span class="sxs-lookup"><span data-stu-id="d3d52-149">GetDecimal</span></span><br /><br /> <span data-ttu-id="d3d52-150">GetDouble</span><span class="sxs-lookup"><span data-stu-id="d3d52-150">GetDouble</span></span><br /><br /> <span data-ttu-id="d3d52-151">GetFloat</span><span class="sxs-lookup"><span data-stu-id="d3d52-151">GetFloat</span></span><br /><br /> <span data-ttu-id="d3d52-152">GetGuid</span><span class="sxs-lookup"><span data-stu-id="d3d52-152">GetGuid</span></span><br /><br /> <span data-ttu-id="d3d52-153">GetInt16</span><span class="sxs-lookup"><span data-stu-id="d3d52-153">GetInt16</span></span><br /><br /> <span data-ttu-id="d3d52-154">GetInt32</span><span class="sxs-lookup"><span data-stu-id="d3d52-154">GetInt32</span></span><br /><br /> <span data-ttu-id="d3d52-155">GetInt64</span><span class="sxs-lookup"><span data-stu-id="d3d52-155">GetInt64</span></span><br /><br /> <span data-ttu-id="d3d52-156">GetName</span><span class="sxs-lookup"><span data-stu-id="d3d52-156">GetName</span></span><br /><br /> <span data-ttu-id="d3d52-157">GetOrdinal</span><span class="sxs-lookup"><span data-stu-id="d3d52-157">GetOrdinal</span></span><br /><br /> <span data-ttu-id="d3d52-158">GetSqlBinary</span><span class="sxs-lookup"><span data-stu-id="d3d52-158">GetSqlBinary</span></span><br /><br /> <span data-ttu-id="d3d52-159">GetSqlBoolean</span><span class="sxs-lookup"><span data-stu-id="d3d52-159">GetSqlBoolean</span></span><br /><br /> <span data-ttu-id="d3d52-160">GetSqlByte</span><span class="sxs-lookup"><span data-stu-id="d3d52-160">GetSqlByte</span></span><br /><br /> <span data-ttu-id="d3d52-161">GetSqlDateTime</span><span class="sxs-lookup"><span data-stu-id="d3d52-161">GetSqlDateTime</span></span><br /><br /> <span data-ttu-id="d3d52-162">GetSqlDecimal</span><span class="sxs-lookup"><span data-stu-id="d3d52-162">GetSqlDecimal</span></span><br /><br /> <span data-ttu-id="d3d52-163">GetSqlDouble</span><span class="sxs-lookup"><span data-stu-id="d3d52-163">GetSqlDouble</span></span><br /><br /> <span data-ttu-id="d3d52-164">GetSqlGuid</span><span class="sxs-lookup"><span data-stu-id="d3d52-164">GetSqlGuid</span></span><br /><br /> <span data-ttu-id="d3d52-165">GetSqlInt16</span><span class="sxs-lookup"><span data-stu-id="d3d52-165">GetSqlInt16</span></span><br /><br /> <span data-ttu-id="d3d52-166">GetSqlInt32</span><span class="sxs-lookup"><span data-stu-id="d3d52-166">GetSqlInt32</span></span><br /><br /> <span data-ttu-id="d3d52-167">GetSqlInt64</span><span class="sxs-lookup"><span data-stu-id="d3d52-167">GetSqlInt64</span></span><br /><br /> <span data-ttu-id="d3d52-168">GetSqlMoney</span><span class="sxs-lookup"><span data-stu-id="d3d52-168">GetSqlMoney</span></span><br /><br /> <span data-ttu-id="d3d52-169">GetSqlSingle</span><span class="sxs-lookup"><span data-stu-id="d3d52-169">GetSqlSingle</span></span><br /><br /> <span data-ttu-id="d3d52-170">GetSqlString</span><span class="sxs-lookup"><span data-stu-id="d3d52-170">GetSqlString</span></span><br /><br /> <span data-ttu-id="d3d52-171">GetString</span><span class="sxs-lookup"><span data-stu-id="d3d52-171">GetString</span></span><br /><br /> <span data-ttu-id="d3d52-172">IsDBNull</span><span class="sxs-lookup"><span data-stu-id="d3d52-172">IsDBNull</span></span>|  
|`IduCount`|<span data-ttu-id="d3d52-173">Restituisce il numero totale di istruzioni INSERT, DELETE e UPDATE eseguite per la durata della connessione, dopo che l'applicazione è stata avviata usando il provider e con le statistiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="d3d52-173">Returns the total number of INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`IduRows`|<span data-ttu-id="d3d52-174">Restituisce il numero totale di righe interessate dalle istruzioni INSERT, DELETE e UPDATE eseguite per la durata della connessione, dopo che l'applicazione è stata avviata usando il provider e con le statistiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="d3d52-174">Returns the total number of rows affected by INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`NetworkServerTime`|<span data-ttu-id="d3d52-175">Restituisce il tempo cumulativo (in millisecondi) di attesa del provider per le risposte dal server dopo che l'avvio dell'applicazione e l'abilitazione delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="d3d52-175">Returns the cumulative amount of time (in milliseconds) that the provider spent waiting for replies from the server once the application has started using the provider and has enabled statistics.</span></span>|  
|`PreparedExecs`|<span data-ttu-id="d3d52-176">Restituisce il numero di comandi preparati eseguiti per la durata della connessione, dopo che l'applicazione è stata avviata usando il provider e con le statistiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="d3d52-176">Returns the number of prepared commands executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`Prepares`|<span data-ttu-id="d3d52-177">Restituisce il numero di istruzioni preparate per la durata della connessione, dopo che l'applicazione è stata avviata usando il provider e con le statistiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="d3d52-177">Returns the number of statements prepared through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`SelectCount`|<span data-ttu-id="d3d52-178">Restituisce il numero di istruzioni SELECT eseguite per la durata della connessione, dopo che l'applicazione è stata avviata usando il provider e con le statistiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="d3d52-178">Returns the number of SELECT statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="d3d52-179">Sono incluse le istruzioni FETCH per recuperare le righe dai cursori e il conteggio delle istruzioni SELECT viene aggiornato quando viene raggiunta la fine di una classe <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="d3d52-179">This includes FETCH statements to retrieve rows from cursors, and the count for SELECT statements is updated when the end of a <xref:System.Data.SqlClient.SqlDataReader> is reached.</span></span>|  
|`SelectRows`|<span data-ttu-id="d3d52-180">Restituisce il numero di righe selezionate dopo che l'applicazione è stata avviata usando il provider e con le statistiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="d3d52-180">Returns the number of rows selected once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="d3d52-181">Questo numero riflette tutte le righe generate da istruzioni SQL, anche da quelle non effettivamente usate dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="d3d52-181">This counter reflects all the rows generated by SQL statements, even those that were not actually consumed by the caller.</span></span> <span data-ttu-id="d3d52-182">La chiusura di un lettore di dati prima della lettura dell'intero set di risultati, ad esempio, non influisce sul conteggio.</span><span class="sxs-lookup"><span data-stu-id="d3d52-182">For example, closing a data reader before reading the entire result set would not affect the count.</span></span> <span data-ttu-id="d3d52-183">Sono incluse le righe recuperate dai cursori tramite istruzioni FETCH.</span><span class="sxs-lookup"><span data-stu-id="d3d52-183">This includes the rows retrieved from cursors through FETCH statements.</span></span>|  
|`ServerRoundtrips`|<span data-ttu-id="d3d52-184">Restituisce il numero di volte in cui la connessione ha inviato comandi al server e ha ricevuto una risposta, dopo che l'applicazione è stata avviata usando il provider e con le statistiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="d3d52-184">Returns the number of times the connection sent commands to the server and got a reply back once the application has started using the provider and has enabled statistics.</span></span>|  
|`SumResultSets`|<span data-ttu-id="d3d52-185">Restituisce il numero di set di risultati usati dopo che l'applicazione è stata avviata usando il provider e con le statistiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="d3d52-185">Returns the number of result sets that have been used once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="d3d52-186">Sarebbero inclusi, ad esempio, i set di risultati restituiti al client.</span><span class="sxs-lookup"><span data-stu-id="d3d52-186">For example this would include any result set returned to the client.</span></span> <span data-ttu-id="d3d52-187">Per i cursori, ogni operazione di recupero o blocco di recupero viene considerata un set di risultati indipendente.</span><span class="sxs-lookup"><span data-stu-id="d3d52-187">For cursors, each fetch or block-fetch operation is considered an independent result set.</span></span>|  
|`Transactions`|<span data-ttu-id="d3d52-188">Restituisce il numero di transazioni utente avviate dopo che l'applicazione è stata avviata usando il provider e con le statistiche abilitate, inclusi i rollback.</span><span class="sxs-lookup"><span data-stu-id="d3d52-188">Returns the number of user transactions started once the application has started using the provider and has enabled statistics, including rollbacks.</span></span> <span data-ttu-id="d3d52-189">Se la connessione è in esecuzione con il commit automatico abilitato, ogni comando viene considerato una transazione.</span><span class="sxs-lookup"><span data-stu-id="d3d52-189">If a connection is running with auto commit on, each command is considered a transaction.</span></span><br /><br /> <span data-ttu-id="d3d52-190">Questo contatore incrementa il conteggio delle transazioni non appena viene eseguita un'istruzione BEGIN TRAN, indipendentemente dal fatto che in un secondo momento venga eseguito il commit o il rollback della transazione.</span><span class="sxs-lookup"><span data-stu-id="d3d52-190">This counter increments the transaction count as soon as a BEGIN TRAN statement is executed, regardless of whether the transaction is committed or rolled back later.</span></span>|  
|`UnpreparedExecs`|<span data-ttu-id="d3d52-191">Restituisce il numero di istruzioni non preparate eseguite per la durata della connessione, dopo che l'applicazione è stata avviata usando il provider e con le statistiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="d3d52-191">Returns the number of unprepared statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
  
### <a name="retrieving-a-value"></a><span data-ttu-id="d3d52-192">Recupero di valori</span><span class="sxs-lookup"><span data-stu-id="d3d52-192">Retrieving a Value</span></span>  
 <span data-ttu-id="d3d52-193">Nell'applicazione console seguente viene illustrato come abilitare le statistiche in una connessione, recuperare quattro singoli valori statistici e scriverli nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="d3d52-193">The following console application shows how to enable statistics on a connection, retrieve four individual statistic values, and write them out to the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3d52-194">Nell'esempio seguente viene usato il database di esempio **AdventureWorks** incluso in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d3d52-194">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="d3d52-195">Per la stringa di connessione specificata nel codice di esempio si presuppone che il database sia installato e disponibile nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="d3d52-195">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="d3d52-196">Modificare la stringa di connessione in base alle esigenze dell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="d3d52-196">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      ' Retrieve a few individual values  
      ' related to the previous command.  
      Dim bytesReceived As Long = _  
          CLng(currentStatistics.Item("BytesReceived"))  
      Dim bytesSent As Long = _  
          CLng(currentStatistics.Item("BytesSent"))  
      Dim selectCount As Long = _  
          CLng(currentStatistics.Item("SelectCount"))  
      Dim selectRows As Long = _  
          CLng(currentStatistics.Item("SelectRows"))  
  
      Console.WriteLine("BytesReceived: " & bytesReceived.ToString())  
      Console.WriteLine("BytesSent: " & bytesSent.ToString())  
      Console.WriteLine("SelectCount: " & selectCount.ToString())  
      Console.WriteLine("SelectRows: " & selectRows.ToString())  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrieve it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetValue  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =
          new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
          awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
          currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        // Retrieve a few individual values  
        // related to the previous command.  
        long bytesReceived =  
            (long) currentStatistics["BytesReceived"];  
        long bytesSent =  
            (long) currentStatistics["BytesSent"];  
        long selectCount =  
            (long) currentStatistics["SelectCount"];  
        long selectRows =  
            (long) currentStatistics["SelectRows"];  
  
        Console.WriteLine("BytesReceived: " +  
            bytesReceived.ToString());  
        Console.WriteLine("BytesSent: " +  
            bytesSent.ToString());  
        Console.WriteLine("SelectCount: " +  
            selectCount.ToString());  
        Console.WriteLine("SelectRows: " +  
            selectRows.ToString());  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrieve it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
### <a name="retrieving-all-values"></a><span data-ttu-id="d3d52-197">Recupero di tutti i valori</span><span class="sxs-lookup"><span data-stu-id="d3d52-197">Retrieving All Values</span></span>  
 <span data-ttu-id="d3d52-198">Nell'applicazione console seguente viene illustrato come abilitare le statistiche in una connessione, recuperare tutti i valori statistici disponibili usando l'enumeratore e scriverli nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="d3d52-198">The following console application shows how to enable statistics on a connection, retrieve all available statistic values using the enumerator, and write them to the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3d52-199">Nell'esempio seguente viene usato il database di esempio **AdventureWorks** incluso in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d3d52-199">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="d3d52-200">Per la stringa di connessione specificata nel codice di esempio si presuppone che il database sia installato e disponibile nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="d3d52-200">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="d3d52-201">Modificare la stringa di connessione in base alle esigenze dell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="d3d52-201">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      Console.WriteLine("Key Name and Value")  
  
      ' Note the entries are unsorted.  
      For Each entry As DictionaryEntry In currentStatistics  
        Console.WriteLine(entry.Key.ToString() & _  
            ": " & entry.Value.ToString())  
      Next  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrieve it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Text;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetAll  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =  
            new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
            awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
            currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        Console.WriteLine("Key Name and Value");  
  
        // Note the entries are unsorted.  
        foreach (DictionaryEntry entry in currentStatistics)  
        {  
          Console.WriteLine(entry.Key.ToString() +  
              ": " + entry.Value.ToString());  
        }  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrieve it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3d52-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3d52-202">See also</span></span>

- [<span data-ttu-id="d3d52-203">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d3d52-203">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="d3d52-204">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d3d52-204">ADO.NET Overview</span></span>](../ado-net-overview.md)

---
title: Generazione di comandi tramite CommandBuilders
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6e3fb8b5-373b-4f9e-ab03-a22693df8e91
ms.openlocfilehash: 76c2a6cb0661a0e39fc3a0dd599fcbb3c046f382
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149612"
---
# <a name="generating-commands-with-commandbuilders"></a>Generazione di comandi tramite CommandBuilders
Se la proprietà `SelectCommand` viene specificata in modo dinamico in fase di esecuzione, ad esempio mediante uno strumento per query che accetta un comando testuale dell'utente, potrebbe non essere possibile specificare l'appropriato `InsertCommand`, `UpdateCommand` o `DeleteCommand` in fase di progettazione. Se <xref:System.Data.DataTable> esegue il mapping o viene generato da una singola tabella di database, è possibile usare l'oggetto <xref:System.Data.Common.DbCommandBuilder> per generare automaticamente gli oggetti `DeleteCommand`, `InsertCommand` e `UpdateCommand` di <xref:System.Data.Common.DbDataAdapter>.  
  
 Come requisito minimo, è necessario impostare la proprietà `SelectCommand` affinché la generazione automatica del comando venga eseguita correttamente. Lo schema della tabella recuperato dalla proprietà `SelectCommand` determina la sintassi delle istruzioni INSERT, UPDATE e DELETE generate automaticamente.  
  
 <xref:System.Data.Common.DbCommandBuilder> deve eseguire `SelectCommand` in modo da restituire i metadati necessari per creare i comandi SQL INSERT, UPDATE e DELETE. Di conseguenza, è necessario un ulteriore percorso all'origine dati che può ridurre le prestazioni. Per ottenere prestazioni ottimali, specificare i comandi in modo esplicito anziché usare <xref:System.Data.Common.DbCommandBuilder>.  
  
 È inoltre necessario che `SelectCommand` restituisca almeno una chiave primaria o una colonna univoca. In caso contrario, viene generata un'eccezione `InvalidOperation` e i comandi non vengono generati.  
  
 Quando è associato a un `DataAdapter`, <xref:System.Data.Common.DbCommandBuilder> genera automaticamente le proprietà `InsertCommand`, `UpdateCommand` e `DeleteCommand` del `DataAdapter`, se queste sono riferimenti Null. Se esiste già un oggetto `Command` per una proprietà, viene usato l'oggetto `Command` esistente.  
  
 Le visualizzazioni di database create dall'unione di due o più tabelle non vengono considerate un'unica tabella di database. In questo caso non è possibile usare <xref:System.Data.Common.DbCommandBuilder> per generare automaticamente i comandi ed è necessario specificarli in modo esplicito. Per informazioni sull'impostazione esplicita `DataSet` dei comandi per risolvere gli aggiornamenti in una nuova origine dati, vedere [Aggiornamento delle origini dati con DataAdapter](updating-data-sources-with-dataadapters.md).  
  
 È possibile eseguire il mapping dei parametri di output alla riga aggiornata di un `DataSet`. Un'attività comune sarebbe il recupero del valore di un campo identità generato automaticamente o del timestamp da un'origine dati. Per impostazione predefinita, <xref:System.Data.Common.DbCommandBuilder> non esegue il mapping dei parametri di output sulle colonne in una riga aggiornata. In questo caso è necessario specificare il comando in modo esplicito. Per un esempio di mapping di un campo Identity generato automaticamente a una colonna di una riga inserita, vedere Recupero di [valori Identity o Autonumber](retrieving-identity-or-autonumber-values.md).  
  
## <a name="rules-for-automatically-generated-commands"></a>Regole per i comandi generati automaticamente  
 Nella tabella seguente vengono illustrate le regole per generare automaticamente i comandi.  
  
|Comando|Regola|  
|-------------|----------|  
|`InsertCommand`|Consente di inserire una riga nell'origine dati per ogni riga della tabella con una proprietà <xref:System.Data.DataRow.RowState%2A> uguale a <xref:System.Data.DataRowState.Added>. I valori vengono inseriti in tutte le colonne aggiornabili, quindi non nelle colonne di identità, espressioni o timestamp.|  
|`UpdateCommand`|Aggiorna le righe nell'origine dati per tutte le righe della tabella con `RowState` uguale a <xref:System.Data.DataRowState.Modified>. I valori vengono aggiornati in tutte le colonne aggiornabili, quindi non nelle colonne di identità o di espressioni. Vengono aggiornate tutte le righe in cui i valori delle colonne nell'origine dati corrispondono ai valori delle colonne della chiave primaria della riga e in cui le restanti colonne dell'origine dati corrispondono ai valori originali della riga. Per altre informazioni, vedere la sezione "Modello di concorrenza ottimistica per aggiornamenti ed eliminazioni" contenuta in questo argomento.|  
|`DeleteCommand`|Elimina le righe nell'origine dati per tutte le righe della tabella con `RowState` uguale a <xref:System.Data.DataRowState.Deleted>. Vengono eliminate tutte le righe in cui i valori delle colonne corrispondono ai valori delle colonne della chiave primaria della riga e in cui le restanti colonne dell'origine dati corrispondono ai valori originali della riga. Per altre informazioni, vedere la sezione "Modello di concorrenza ottimistica per aggiornamenti ed eliminazioni" contenuta in questo argomento.|  
  
## <a name="optimistic-concurrency-model-for-updates-and-deletes"></a>Modello di concorrenza ottimistica per aggiornamenti ed eliminazioni  
 La logica per la generazione automatica dei comandi per le istruzioni UPDATE e DELETE si basa sulla *concorrenza ottimistica,* ovvero i record non sono bloccati per la modifica e possono essere modificati da altri utenti o processi in qualsiasi momento. Poiché un record può essere modificato dopo che è stato restituito dall'istruzione SELECT, ma prima che sia eseguita l'istruzione UPDATE o DELETE, nell'istruzione UPDATE o DELETE generata automaticamente è contenuta una clausola WHERE, tale che una riga viene aggiornata solo se contiene tutti i valori originali e non è stata eliminata dall'origine dati. In questo modo si evita di sovrascrivere i nuovi dati. Nei casi in cui un comando Update generato automaticamente tenta di aggiornare una riga che è stata eliminata o che non contiene i valori originali rilevati in <xref:System.Data.DataSet>, il comando non ha alcun effetto sui record e viene generata un'eccezione <xref:System.Data.DBConcurrencyException>.  
  
 Se si desidera che le istruzioni UPDATE o DELETE vengano completate a prescindere dai valori originali, è necessario impostare in modo esplicito `UpdateCommand` per il `DataAdapter` e non usare la generazione automatica dei comandi.  
  
## <a name="limitations-of-automatic-command-generation-logic"></a>Limiti della logica per la generazione automatica dei comandi  
 I limiti che seguono si riferiscono alla generazione automatica dei comandi.  
  
### <a name="unrelated-tables-only"></a>Solo tabelle non correlate  
 La logica per la generazione automatica dei comandi genera un'istruzione INSERT, UPDATE o DELETE per le tabelle autonome senza tenere conto delle relazioni con altre tabelle nell'origine dati. Di conseguenza, è possibile che venga rilevato un errore quando si chiama `Update` per inviare le modifiche a una colonna che fa parte di un vincolo di chiave esterna nel database. Per evitare questa eccezione, non usare <xref:System.Data.Common.DbCommandBuilder> per aggiornare le colonne incluse in un vincolo di chiave esterna e specificare in modo esplicito le istruzioni usate per eseguire l'operazione.  
  
### <a name="table-and-column-names"></a>Nomi di tabelle e colonne  
 La logica per la generazione automatica dei comandi potrebbe non essere eseguita correttamente se i nomi delle colonne o delle tabelle contengono caratteri speciali quali spazi, punti, virgolette o altri caratteri non alfanumerici, anche se racchiusi tra parentesi. A seconda del provider, l'impostazione dei parametri QuoteSuffix e QuotePrefix può consentire alla logica di generazione di elaborare gli spazi, ma non i caratteri speciali di escape. Sono supportati nomi di tabella completi sotto forma di *catalog.schema.table.*  
  
## <a name="using-the-commandbuilder-to-automatically-generate-an-sql-statement"></a>Uso di CommandBuilder per generare automaticamente un'istruzione SQL  
 Per generare automaticamente le istruzioni SQL per un oggetto `DataAdapter`, impostare innanzitutto la proprietà `SelectCommand` di `DataAdapter`. Creare quindi un oggetto `CommandBuilder` e specificare come argomento l'oggetto `DataAdapter` per il quale l'oggetto `CommandBuilder` genererà automaticamente le istruzioni SQL.  
  
```vb  
' Assumes that connection is a valid SqlConnection object
' inside of a Using block.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers", connection)  
Dim builder As SqlCommandBuilder = New SqlCommandBuilder(adapter)  
builder.QuotePrefix = "["  
builder.QuoteSuffix = "]"  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object  
// inside of a using block.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers", connection);  
SqlCommandBuilder builder = new SqlCommandBuilder(adapter);  
builder.QuotePrefix = "[";  
builder.QuoteSuffix = "]";  
```  
  
## <a name="modifying-the-selectcommand"></a>Modifica di SelectCommand  
 Se si modifica `CommandText` di `SelectCommand` dopo la generazione automatica di un comando INSERT, UPDATE o DELETE, è possibile che venga generata un'eccezione. Se l'oggetto `SelectCommand.CommandText` modificato contiene informazioni sullo schema che non sono coerenti con l'oggetto `SelectCommand.CommandText` usato durante la generazione automatica del comando di inserimento, aggiornamento o eliminazione, nelle future chiamate al metodo `DataAdapter.Update` potrebbe essere eseguito un tentativo di accesso a colonne che non esistono più nella tabella corrente a cui `SelectCommand` fa riferimento e verrà generata un'eccezione.  
  
 È possibile aggiornare le informazioni sullo schema usate da `CommandBuilder` per generare automaticamente i comandi chiamando il metodo `RefreshSchema` di `CommandBuilder`.  
  
 Se si desidera conoscere il comando che è stato generato automaticamente, è possibile ottenere un riferimento ai comandi generati automaticamente tramite i metodi `GetInsertCommand`, `GetUpdateCommand` e `GetDeleteCommand` dell'oggetto `CommandBuilder` e selezionare la proprietà `CommandText`del comando associato.  
  
 Nell'esempio di codice seguente viene scritto sulla console il comando di aggiornamento che è stato generato automaticamente.  
  
```vb
Console.WriteLine(builder.GetUpdateCommand().CommandText)  
```

```csharp
Console.WriteLine(builder.GetUpdateCommand().CommandText);
```
  
 Nell'esempio seguente viene ricreata la tabella `Customers` nel set di dati `custDS`. Il **RefreshSchema** metodo viene chiamato per aggiornare i comandi generati automaticamente con queste nuove informazioni di colonna.  
  
```vb  
' Assumes an open SqlConnection and SqlDataAdapter inside of a Using block.  
adapter.SelectCommand.CommandText = _  
  "SELECT CustomerID, ContactName FROM dbo.Customers"  
builder.RefreshSchema()  
  
custDS.Tables.Remove(custDS.Tables("Customers"))  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
// Assumes an open SqlConnection and SqlDataAdapter inside of a using block.  
adapter.SelectCommand.CommandText =
  "SELECT CustomerID, ContactName FROM dbo.Customers";  
builder.RefreshSchema();  
  
custDS.Tables.Remove(custDS.Tables["Customers"]);  
adapter.Fill(custDS, "Customers");  
```  
  
## <a name="see-also"></a>Vedere anche

- [Comandi e parametri](commands-and-parameters.md)
- [Esecuzione di un comandoExecuting a Command](executing-a-command.md)
- [DbConnection, DbCommand e DbException](dbconnection-dbcommand-and-dbexception.md)
- [Panoramica di ADO.NET](ado-net-overview.md)

---
title: Modifica di dati con valori di grandi dimensioni (max)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8aca5f00-d80e-4320-81b3-016d0466f7ee
ms.openlocfilehash: cb37fdb85d323d4f0816a3667a4624da8ec75e65
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979846"
---
# <a name="modifying-large-value-max-data-in-adonet"></a>Modifica di dati con valori elevati (massimi) in ADO.NET
I tipi di dati LOB (oggetti di grandi dimensioni) sono quelli che superano la dimensione massima di 8 kilobyte (KB) per le righe. In SQL Server viene fornito un identificatore `max` per i tipi di dati `varchar`, `nvarchar` e `varbinary` per consentire l'archiviazione di valori di dimensioni pari a 2^32 byte. Nelle colonne di tabelle e nelle variabili Transact-SQL possono essere specificati tipi di dati `varchar(max)`, `nvarchar(max)` o `varbinary(max)`. In ADO.NET i tipi di dati `max` possono essere recuperati da un `DataReader` e possono inoltre essere specificati come parametri di input e di output senza richiedere una gestione speciale. Per tipi di dati `varchar` di grandi dimensioni, è possibile recuperare e aggiornare i dati in modo incrementale.  
  
 I tipi di dati `max` possono essere usati per eseguire confronti, come le variabili Transact-SQL, e per eseguire concatenazioni. È inoltre usarli nelle clausole DISTINCT, ORDER BY e GROUP BY di un'istruzione SELECT, nonché nelle aggregazioni, nelle unioni e nelle sottoquery.  
  
 La tabella seguente fornisce i collegamenti alla documentazione online di SQL Server.  
  
 **Documentazione online di SQL Server**  
  
1. [Utilizzo di tipi di dati con valori di grandi dimensioni](https://go.microsoft.com/fwlink/?LinkId=120498)  
  
## <a name="large-value-type-restrictions"></a>Restrizioni per i tipi di valori di grandi dimensioni  
 Le seguenti restrizioni si applicano ai tipi di dati `max` e non ai tipi di dati di dimensioni minori:  
  
- Un tipo `sql_variant` non può contenere un tipo di dati `varchar` di grandi dimensioni.  
  
- Le colonne `varchar` di grandi dimensioni non possono essere specificate come colonne di chiave primaria in un indice. Sono consentite in una colonna inclusa in un indice non cluster.  
  
- Le colonne `varchar` di grandi dimensioni non possono essere usate come colonne chiave di partizionamento.  
  
## <a name="working-with-large-value-types-in-transact-sql"></a>Uso di tipi di valori di grandi dimensioni in Transact-SQL  
 La funzione `OPENROWSET` di Transact-SQL è un metodo unico per eseguire la connessione e l'accesso ai dati remoti. Include tutte le informazioni di connessione necessarie per l'accesso remoto ai dati da un'origine dati OLE DB. È possibile fare riferimento a `OPENROWSET` nella clausola FROM di una query come se fosse un nome di tabella. È inoltre possibile farvi riferimento come tabella di destinazione di un'istruzione INSERT, UPDATE o DELETE, soggetta alle funzionalità del provider OLE DB.  
  
 La funzione `OPENROWSET` include il provider di set di righe `BULK`, che consente di leggere i dati direttamente da un file senza caricare i dati in una tabella di destinazione. Questo consente l'uso di `OPENROWSET` in una semplice istruzione INSERT SELECT.  
  
 Gli argomenti dell'opzione `OPENROWSET BULK` forniscono un controllo significativo sulla posizione in cui iniziare e terminare la lettura dei dati, su come gestire gli errori e su come vengono interpretati i dati. È ad esempio possibile specificare che il file di dati venga letto come una singola riga o come un set di righe di una singola colonna di tipo `varbinary`, `varchar` o `nvarchar`. Per la sintassi e le opzioni complete, vedere la documentazione online di SQL Server.  
  
 Nell'esempio seguente viene inserita una foto nella tabella ProductPhoto del database di esempio AdventureWorks. Quando si usa il provider di `BULK OPENROWSET`, è necessario fornire l'elenco di colonne denominato anche se non si inseriscono valori in ogni colonna. In questo caso, la chiave primaria è definita come colonna Identity e può essere omessa dall'elenco di colonne. Notare che è necessario fornire anche un nome di correlazione alla fine dell'istruzione `OPENROWSET`, che in questo caso è ThumbnailPhoto. Tale nome è correlato alla colonna della tabella `ProductPhoto` in cui viene caricato il file.  
  
```sql  
INSERT Production.ProductPhoto (  
    ThumbnailPhoto,   
    ThumbnailPhotoFilePath,   
    LargePhoto,   
    LargePhotoFilePath)  
SELECT ThumbnailPhoto.*, null, null, N'tricycle_pink.gif'  
FROM OPENROWSET   
    (BULK 'c:\images\tricycle.jpg', SINGLE_BLOB) ThumbnailPhoto  
```  
  
## <a name="updating-data-using-update-write"></a>Aggiornamento di dati tramite UPDATE .WRITE  
 L'istruzione Transact-SQL UPDATE include una nuova sintassi WRITE per modificare il contenuto delle colonne `varchar(max)`, `nvarchar(max)` o `varbinary(max)`. In tal modo è possibile eseguire aggiornamenti parziali dei dati. La sintassi UPDATE .WRITE viene illustrata di seguito in formato abbreviato:  
  
 AGGIORNAMENTO  
  
 { *\<object>* }  
  
 SET  
  
 { *column_name* = {. WRITE ( *espressione* , @Offset, @Length)}  
  
 Il metodo WRITE specifica che una sezione del valore del *column_name* verrà modificata. L'espressione è il valore che verrà copiato nel *column_name*, il `@Offset` è il punto iniziale in cui verrà scritta l'espressione e l'argomento `@Length` è la lunghezza della sezione nella colonna.  
  
|\* Se|Quindi|  
|--------|----------|  
|L'espressione è impostata su NULL.|`@Length` viene ignorato e il valore in *column_name* viene troncato in corrispondenza del `@Offset`specificato.|  
|Il valore di `@Offset` è NULL.|L'operazione di aggiornamento aggiunge l'espressione alla fine del valore di *column_name* esistente e `@Length` viene ignorato.|  
|Il valore di `@Offset` è maggiore della lunghezza del valore di column_name.|SQL Server restituisce un errore.|  
|Il valore di `@Length` è NULL.|L'operazione di aggiornamento rimuove tutti i dati a partire da `@Offset` alla fine del valore di `column_name`.|  
  
> [!NOTE]
> Il valore di `@Offset` o di `@Length` non può essere un numero negativo.  
  
## <a name="example"></a>Esempio  
 In questo esempio di Transact-SQL viene aggiornato un valore parziale di DocumentSummary, una colonna `nvarchar(max)` della tabella Document nel database AdventureWorks. La parola "components" viene sostituita con la parola "features" specificando la parola di sostituzione, la posizione iniziale (offset) della parola da sostituire nei dati esistenti e il numero di caratteri da sostituire (lunghezza). Per confrontare i risultati, nell'esempio sono incluse le istruzioni SELECT precedenti e successive all'istruzione UPDATE.  
  
```sql
USE AdventureWorks;  
GO  
--View the existing value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety components of your bicycle.  
  
--Modify a single word in the DocumentSummary column  
UPDATE Production.Document  
SET DocumentSummary .WRITE (N'features',28,10)  
WHERE DocumentID = 3 ;  
GO   
--View the modified value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety features of your bicycle.  
```  
  
## <a name="working-with-large-value-types-in-adonet"></a>Uso di tipi di valori di grandi dimensioni in ADO.NET  
 È possibile utilizzare tipi di valore di grandi dimensioni in ADO.NET specificando tipi di valore di grandi dimensioni come <xref:System.Data.SqlClient.SqlParameter> oggetti in una <xref:System.Data.SqlClient.SqlDataReader> per restituire un set di risultati o utilizzando un <xref:System.Data.SqlClient.SqlDataAdapter> per riempire un /`DataSet``DataTable`. Non vi è differenza tra il modo di usare un tipo di valore di grandi dimensioni e il relativo tipo di dati del valore di dimensioni minori.  
  
### <a name="using-getsqlbytes-to-retrieve-data"></a>Uso di GetSqlBytes per il recupero di dati  
 È possibile usare il metodo `GetSqlBytes` del tipo <xref:System.Data.SqlClient.SqlDataReader> per recuperare il contenuto di una colonna `varbinary(max)`. Il seguente frammento di codice presuppone un oggetto <xref:System.Data.SqlClient.SqlCommand> denominato `cmd` che consente di selezionare dati `varbinary(max)` da una tabella e un oggetto <xref:System.Data.SqlClient.SqlDataReader> denominato `reader` che consente di recuperare i dati come tipo <xref:System.Data.SqlTypes.SqlBytes>.  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim bytes As SqlBytes = reader.GetSqlBytes(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBytes bytes = reader.GetSqlBytes(0);  
    }  
```  
  
### <a name="using-getsqlchars-to-retrieve-data"></a>Uso di GetSqlChars per il recupero di dati  
 È possibile usare il metodo `GetSqlChars` del tipo <xref:System.Data.SqlClient.SqlDataReader> per recuperare il contenuto di una colonna `varchar(max)` o `nvarchar(max)`. Il seguente frammento di codice presuppone un oggetto <xref:System.Data.SqlClient.SqlCommand> denominato `cmd` che consente di selezionare dati `nvarchar(max)` da una tabella e un oggetto <xref:System.Data.SqlClient.SqlDataReader> denominato `reader` che consente di recuperare i dati.  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim buffer As SqlChars = reader.GetSqlChars(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
{  
    SqlChars buffer = reader.GetSqlChars(0);  
}  
```  
  
### <a name="using-getsqlbinary-to-retrieve-data"></a>Uso di GetSqlBinary per il recupero di dati  
 È possibile usare il metodo `GetSqlBinary` di un tipo <xref:System.Data.SqlClient.SqlDataReader> per recuperare il contenuto di una colonna `varbinary(max)`. Il seguente frammento di codice presuppone un oggetto <xref:System.Data.SqlClient.SqlCommand> denominato `cmd` che consente di selezionare dati `varbinary(max)` da una tabella e un oggetto <xref:System.Data.SqlClient.SqlDataReader> denominato `reader` che consente di recuperare i dati come flusso <xref:System.Data.SqlTypes.SqlBinary>.  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim binaryStream As SqlBinary = reader.GetSqlBinary(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBinary binaryStream = reader.GetSqlBinary(0);  
    }  
```  
  
### <a name="using-getbytes-to-retrieve-data"></a>Uso di GetBytes per il recupero di dati  
 Il metodo `GetBytes` di un tipo <xref:System.Data.SqlClient.SqlDataReader> consente di leggere un flusso di byte dall'offset della colonna specificata nella matrice di byte a partire dall'offset della matrice specificata. Il seguente frammento di codice presuppone un oggetto <xref:System.Data.SqlClient.SqlDataReader> denominato `reader` che consente di recuperare byte in una matrice di byte. Notare che, a differenza di `GetSqlBytes`, con `GetBytes` è necessario specificare una dimensione per il buffer della matrice.  
  
```vb  
While reader.Read()  
    Dim buffer(4000) As Byte  
    Dim byteCount As Integer = _  
    CInt(reader.GetBytes(1, 0, buffer, 0, 4000))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    byte[] buffer = new byte[4000];  
    long byteCount = reader.GetBytes(1, 0, buffer, 0, 4000);  
}  
```  
  
### <a name="using-getvalue-to-retrieve-data"></a>Uso di GetValue per il recupero di dati  
 Il metodo `GetValue` di un tipo <xref:System.Data.SqlClient.SqlDataReader> consente di leggere il valore dall'offset della colonna specificata in una matrice. Il seguente frammento di codice presuppone un oggetto <xref:System.Data.SqlClient.SqlDataReader> denominato `reader` che consente di recuperare dati binari dall'offset della prima colonna e dati di tipo stringa dall'offset della seconda colonna.  
  
```vb  
While reader.Read()  
    ' Read the data from varbinary(max) column  
    Dim binaryData() As Byte = CByte(reader.GetValue(0))  
  
    ' Read the data from varchar(max) or nvarchar(max) column  
    Dim stringData() As String = Cstr((reader.GetValue(1))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    // Read the data from varbinary(max) column  
    byte[] binaryData = (byte[])reader.GetValue(0);  
  
    // Read the data from varchar(max) or nvarchar(max) column  
    String stringData = (String)reader.GetValue(1);  
}  
```  
  
## <a name="converting-from-large-value-types-to-clr-types"></a>Conversione da tipi di valore di grandi dimensioni a tipi CLR  
 È possibile convertire il contenuto di una colonna `varchar(max)` o `nvarchar(max)` usando uno dei metodi disponibili per la conversione di stringhe, ad esempio `ToString`. Il seguente frammento di codice presuppone un oggetto <xref:System.Data.SqlClient.SqlDataReader> denominato `reader` che consente di recuperare i dati.  
  
```vb  
While reader.Read()  
    Dim str as String = reader(0).ToString()  
    Console.WriteLine(str)  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
     string str = reader[0].ToString();  
     Console.WriteLine(str);  
}  
```  
  
### <a name="example"></a>Esempio  
 Il codice seguente consente di recuperare il nome e l'oggetto `LargePhoto` dalla tabella `ProductPhoto` del database `AdventureWorks` e di salvarlo in un file. È necessario compilare l'assembly con un riferimento allo spazio dei nomi <xref:System.Drawing>.  Il metodo <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> del tipo <xref:System.Data.SqlClient.SqlDataReader> restituisce un oggetto <xref:System.Data.SqlTypes.SqlBytes> che espone una proprietà `Stream`. Il codice lo usa per creare un nuovo oggetto `Bitmap`, quindi lo salva nel `ImageFormat`gif.  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## <a name="using-large-value-type-parameters"></a>Utilizzo dei parametri di tipi di valore di grandi dimensioni  
 I tipi di valore di grandi dimensioni possono essere usati negli oggetti <xref:System.Data.SqlClient.SqlParameter> nello stesso modo in cui si usano tipi di valore di dimensioni minori in oggetti <xref:System.Data.SqlClient.SqlParameter>. È possibile recuperare i tipi di valore di grandi dimensioni come <xref:System.Data.SqlClient.SqlParameter> valori, come illustrato nell'esempio seguente. Il codice presuppone l'esistenza della seguente stored procedure GetDocumentSummary nel database di esempio AdventureWorks. Il stored procedure accetta un parametro di input denominato @DocumentID e restituisce il contenuto della colonna DocumentSummary nel parametro @DocumentSummary output.  
  
```sql
CREATE PROCEDURE GetDocumentSummary   
(  
    @DocumentID int,  
    @DocumentSummary nvarchar(MAX) OUTPUT  
)  
AS  
SET NOCOUNT ON  
SELECT  @DocumentSummary=Convert(nvarchar(MAX), DocumentSummary)  
FROM    Production.Document  
WHERE   DocumentID=@DocumentID  
```  
  
### <a name="example"></a>Esempio  
 Il codice di ADO.NET crea oggetti <xref:System.Data.SqlClient.SqlConnection> e <xref:System.Data.SqlClient.SqlCommand> per eseguire la stored procedure GetDocumentSummary e recuperare le informazioni di riepilogo del documento archiviate come tipo di valore di grandi dimensioni. Il codice passa un valore per il parametro di input @DocumentID e Visualizza i risultati restituiti nel parametro di output @DocumentSummary nella finestra della console.  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Dati binari e con valori elevati SQL Server](sql-server-binary-and-large-value-data.md)
- [Mapping dei tipi di dati SQL Server](../sql-server-data-type-mappings.md)
- [Operazioni sui dati SQL Server in ADO.NET](sql-server-data-operations.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)

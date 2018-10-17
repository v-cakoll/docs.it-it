---
title: Dati FILESTREAM
ms.date: 03/30/2017
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
ms.openlocfilehash: 843aa890ba80ab2816af0726170eacb77f419d50
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374196"
---
# <a name="filestream-data"></a>Dati FILESTREAM
L'attributo di archiviazione FILESTREAM è per i dati (BLOB) binari archiviati in una colonna varbinary(max). Prima di FILESTREAM, l'archiviazione dei dati binari richiedeva una gestione speciale. I dati non strutturati, come documenti di testo, immagini e video, sono spesso archiviati fuori dal database e questo ne rende complessa la gestione.  
  
> [!NOTE]
>  Per usare i dati FILESTREAM con SqlClient, è necessario installare .NET Framework 3.5 SP1 (o versione successiva).  
  
 Se si specifica l'attributo FILESTREAM in una colonna varbinary(max), in SQL Server i dati vengono archiviati nel file system NTFS locale anziché nel file di database. Sebbene vengano archiviati separatamente, è possibile usare le stesse istruzioni [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] supportate per l'uso di dati varbinary(max) archiviati nel database.  
  
## <a name="sqlclient-support-for-filestream"></a>Supporto di SqlClient per FILESTREAM  
 Il [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Provider di dati per SQL Server, <xref:System.Data.SqlClient>, supporta la lettura e scrittura di dati FILESTREAM utilizzando il <xref:System.Data.SqlTypes.SqlFileStream> definito nella classe di <xref:System.Data.SqlTypes> dello spazio dei nomi. `SqlFileStream` eredita dalla classe <xref:System.IO.Stream> che fornisce metodi per la lettura e la scrittura nei flussi di dati. La lettura da un flusso comporta il trasferimento dei dati dal flusso in una struttura di dati, ad esempio una matrice di byte. La scrittura comporta il trasferimento dei dati dalla struttura di dati in un flusso.  
  
### <a name="creating-the-sql-server-table"></a>Creazione di una tabella SQL Server  
 Le istruzioni [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] seguenti consentono di creare una tabella denominata employees e di inserire una riga di dati. Dopo avere abilitato l'archiviazione FILESTREAM, è possibile usare questa tabella insieme agli esempi di codice seguenti. I collegamenti alle risorse nella documentazione Online di SQL Server si trovano alla fine di questo argomento.  
  
```  
CREATE TABLE employees  
(  
  EmployeeId INT  NOT NULL  PRIMARY KEY,  
  Photo VARBINARY(MAX) FILESTREAM  NULL,  
  RowGuid UNIQUEIDENTIFIER  NOT NULL  ROWGUIDCOL  
  UNIQUE DEFAULT NEWID()  
)  
GO  
Insert into employees  
Values(1, 0x00, default)  
GO  
```  
  
### <a name="example-reading-overwriting-and-inserting-filestream-data"></a>Esempio: lettura, sovrascrittura e inserimento di dati FILESTREAM  
 Nell'esempio seguente viene illustrato come leggere i dati da FILESTREAM. Il codice consente di ottenere il percorso logico del file, impostando `FileAccess` su `Read` e `FileOptions` su `SequentialScan`. Tramite il codice vengono quindi letti i byte da SqlFileStream nel buffer. I byte vengono infine scritti nella finestra della console.  
  
 Nell'esempio seguente viene illustrato come scrivere dati in un oggetto FILESTREAM nel quale vengono sovrascritti tutti i dati esistenti. Il codice consente di ottenere il percorso logico del file e di creare `SqlFileStream`, impostando `FileAccess` su `Write` e `FileOptions` su `SequentialScan`. Un singolo byte viene scritto in `SqlFileStream`, sostituendo tutti i dati nel file.  
  
 Nell'esempio viene illustrato anche come scrivere i dati in un oggetto FILESTREAM usando il metodo Seek per aggiungere i dati alla fine del file. Il codice consente di ottenere il percorso logico del file e di creare `SqlFileStream`, impostando `FileAccess` su `ReadWrite` e `FileOptions` su `SequentialScan`. Nel codice viene usato il metodo Seek per cercare la fine del file e viene aggiunto un singolo byte al file esistente.  
  
```csharp  
using System;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Data;  
using System.IO;  
  
namespace FileStreamTest  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder("server=(local);integrated security=true;database=myDB");  
            ReadFilestream(builder);  
            OverwriteFilestream(builder);  
            InsertFilestream(builder);  
  
            Console.WriteLine("Done");  
        }  
  
        private static void ReadFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for the file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Read, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Read the contents as bytes and write them to the console  
                            for (long index = 0; index < fileStream.Length; index++)  
                            {  
                                Console.WriteLine(fileStream.ReadByte());  
                            }  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void OverwriteFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file   
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Write a single byte to the file. This will  
                            // replace any data in the file.  
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void InsertFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.ReadWrite, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Seek to the end of the file  
                            fileStream.Seek(0, SeekOrigin.End);  
  
                            // Append a single byte   
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
  
        }  
    }  
}
```  
  
 Per un altro esempio, vedere [come archiviare e recuperare dati binari in una colonna di flusso di file](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).  
  
## <a name="resources-in-sql-server-books-online"></a>Risorse nella documentazione online di SQL Server  
 La documentazione completa per FILESTREAM è disponibile nelle sezioni seguenti nella documentazione Online di SQL Server.  
  
|Argomento|Descrizione|  
|-----------|-----------------|  
|[FILESTREAM (SQL Server)](/sql/relational-databases/blob/filestream-sql-server)|Viene descritto quando usare l'archiviazione FILESTREAM e come questa consente l'integrazione del Motore di database di SQL Server con un file system NTFS.|  
|[Creazione di applicazioni Client per i dati FILESTREAM](/sql/relational-databases/blob/create-client-applications-for-filestream-data)|Vengono descritte le funzioni dell'API Win32 per l'uso dei dati FILESTREAM.|  
|[FILESTREAM e altre funzionalità di SQL Server](/sql/relational-databases/blob/filestream-compatibility-with-other-sql-server-features)|Vengono illustrate considerazioni, linee guida e limitazioni per l'uso di dati FILESTREAM con le altre funzionalità di SQL Server.|  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati SQL Server e ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [Recupero e modifica di dati in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Sicurezza dell'accesso di codice e ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md)  
 [Dati binari e con valori elevati SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [Panoramica di ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)

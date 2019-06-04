---
title: Dati FILESTREAM
ms.date: 03/30/2017
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
ms.openlocfilehash: 4edd03a38f8f5df6cb4fb9c2446f966dfe601564
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490071"
---
# <a name="filestream-data"></a><span data-ttu-id="74908-102">Dati FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="74908-102">FILESTREAM Data</span></span>

<span data-ttu-id="74908-103">L'attributo di archiviazione FILESTREAM è per i dati (BLOB) binari archiviati in una colonna varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="74908-103">The FILESTREAM storage attribute is for binary (BLOB) data stored in a varbinary(max) column.</span></span> <span data-ttu-id="74908-104">Prima di FILESTREAM, l'archiviazione dei dati binari richiedeva una gestione speciale.</span><span class="sxs-lookup"><span data-stu-id="74908-104">Before FILESTREAM, storing binary data required special handling.</span></span> <span data-ttu-id="74908-105">I dati non strutturati, come documenti di testo, immagini e video, sono spesso archiviati fuori dal database e questo ne rende complessa la gestione.</span><span class="sxs-lookup"><span data-stu-id="74908-105">Unstructured data, such as text documents, images and video, is often stored outside of the database, making it difficult to manage.</span></span>

> [!NOTE]
> <span data-ttu-id="74908-106">Per usare i dati FILESTREAM con SqlClient, è necessario installare .NET Framework 3.5 SP1 (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="74908-106">You must install the .NET Framework 3.5 SP1 (or later) to work with FILESTREAM data using SqlClient.</span></span>

<span data-ttu-id="74908-107">Se si specifica l'attributo FILESTREAM in una colonna varbinary(max), in SQL Server i dati vengono archiviati nel file system NTFS locale anziché nel file di database.</span><span class="sxs-lookup"><span data-stu-id="74908-107">Specifying the FILESTREAM attribute on a varbinary(max) column causes SQL Server to store the data on the local NTFS file system instead of in the database file.</span></span> <span data-ttu-id="74908-108">Sebbene vengano archiviati separatamente, è possibile utilizzare le stesse istruzioni Transact-SQL supportate per l'utilizzo di dati varbinary(max) archiviati nel database.</span><span class="sxs-lookup"><span data-stu-id="74908-108">Although it is stored separately, you can use the same Transact-SQL statements that are supported for working with varbinary(max) data that is stored in the database.</span></span>

## <a name="sqlclient-support-for-filestream"></a><span data-ttu-id="74908-109">Supporto di SqlClient per FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="74908-109">SqlClient Support for FILESTREAM</span></span>

<span data-ttu-id="74908-110">Il Provider di dati .NET Framework per SQL Server, <xref:System.Data.SqlClient>, supporta la lettura e scrittura di dati FILESTREAM utilizzando la <xref:System.Data.SqlTypes.SqlFileStream> definito nella classe di <xref:System.Data.SqlTypes> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="74908-110">The .NET Framework Data Provider for SQL Server, <xref:System.Data.SqlClient>, supports reading and writing to FILESTREAM data using the <xref:System.Data.SqlTypes.SqlFileStream> class defined in the <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="74908-111">`SqlFileStream` eredita dalla classe <xref:System.IO.Stream> che fornisce metodi per la lettura e la scrittura nei flussi di dati.</span><span class="sxs-lookup"><span data-stu-id="74908-111">`SqlFileStream` inherits from the <xref:System.IO.Stream> class, which provides methods for reading and writing to streams of data.</span></span> <span data-ttu-id="74908-112">La lettura da un flusso comporta il trasferimento dei dati dal flusso in una struttura di dati, ad esempio una matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="74908-112">Reading from a stream transfers data from the stream into a data structure, such as an array of bytes.</span></span> <span data-ttu-id="74908-113">La scrittura comporta il trasferimento dei dati dalla struttura di dati in un flusso.</span><span class="sxs-lookup"><span data-stu-id="74908-113">Writing transfers the data from the data structure into a stream.</span></span>

### <a name="creating-the-sql-server-table"></a><span data-ttu-id="74908-114">Creazione di una tabella SQL Server</span><span class="sxs-lookup"><span data-stu-id="74908-114">Creating the SQL Server Table</span></span>

<span data-ttu-id="74908-115">Le istruzioni Transact-SQL seguenti consentono di creare una tabella denominata employees e di inserire una riga di dati.</span><span class="sxs-lookup"><span data-stu-id="74908-115">The following Transact-SQL statements creates a table named employees and inserts a row of data.</span></span> <span data-ttu-id="74908-116">Dopo avere abilitato l'archiviazione FILESTREAM, è possibile usare questa tabella insieme agli esempi di codice seguenti.</span><span class="sxs-lookup"><span data-stu-id="74908-116">Once you have enabled FILESTREAM storage, you can use this table in conjunction with the code examples that follow.</span></span> <span data-ttu-id="74908-117">I collegamenti alle risorse nella documentazione Online di SQL Server si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="74908-117">The links to resources in SQL Server Books Online are located at the end of this topic.</span></span>

```sql
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

### <a name="example-reading-overwriting-and-inserting-filestream-data"></a><span data-ttu-id="74908-118">Esempio: Lettura, sovrascrittura e inserimento di dati FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="74908-118">Example: Reading, Overwriting, and Inserting FILESTREAM Data</span></span>

<span data-ttu-id="74908-119">Nell'esempio seguente viene illustrato come leggere i dati da FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="74908-119">The following sample demonstrates how to read data from a FILESTREAM.</span></span> <span data-ttu-id="74908-120">Il codice consente di ottenere il percorso logico del file, impostando `FileAccess` su `Read` e `FileOptions` su `SequentialScan`.</span><span class="sxs-lookup"><span data-stu-id="74908-120">The code gets the logical path to the file, setting the `FileAccess` to `Read` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="74908-121">Tramite il codice vengono quindi letti i byte da SqlFileStream nel buffer.</span><span class="sxs-lookup"><span data-stu-id="74908-121">The code then reads the bytes from the SqlFileStream into the buffer.</span></span> <span data-ttu-id="74908-122">I byte vengono infine scritti nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="74908-122">The bytes are then written to the console window.</span></span>

<span data-ttu-id="74908-123">Nell'esempio seguente viene illustrato come scrivere dati in un oggetto FILESTREAM nel quale vengono sovrascritti tutti i dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="74908-123">The sample also demonstrates how to write data to a FILESTREAM in which all existing data is overwritten.</span></span> <span data-ttu-id="74908-124">Il codice consente di ottenere il percorso logico del file e di creare `SqlFileStream`, impostando `FileAccess` su `Write` e `FileOptions` su `SequentialScan`.</span><span class="sxs-lookup"><span data-stu-id="74908-124">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `Write` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="74908-125">Un singolo byte viene scritto in `SqlFileStream`, sostituendo tutti i dati nel file.</span><span class="sxs-lookup"><span data-stu-id="74908-125">A single byte is written to the `SqlFileStream`, replacing any data in the file.</span></span>

<span data-ttu-id="74908-126">Nell'esempio viene illustrato anche come scrivere i dati in un oggetto FILESTREAM usando il metodo Seek per aggiungere i dati alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="74908-126">The sample also demonstrates how to write data to a FILESTREAM by using the Seek method to append data to the end of the file.</span></span> <span data-ttu-id="74908-127">Il codice consente di ottenere il percorso logico del file e di creare `SqlFileStream`, impostando `FileAccess` su `ReadWrite` e `FileOptions` su `SequentialScan`.</span><span class="sxs-lookup"><span data-stu-id="74908-127">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `ReadWrite` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="74908-128">Nel codice viene usato il metodo Seek per cercare la fine del file e viene aggiunto un singolo byte al file esistente.</span><span class="sxs-lookup"><span data-stu-id="74908-128">The code uses the Seek method to seek to the end of the file, appending a single byte to the existing file.</span></span>

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
            ReadFileStream(builder);
            OverwriteFileStream(builder);
            InsertFileStream(builder);

            Console.WriteLine("Done");
        }

        private static void ReadFileStream(SqlConnectionStringBuilder connStringBuilder)
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

        private static void OverwriteFileStream(SqlConnectionStringBuilder connStringBuilder)
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

        private static void InsertFileStream(SqlConnectionStringBuilder connStringBuilder)
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

<span data-ttu-id="74908-129">Per un altro esempio, vedere [come archiviare e recuperare dati binari in una colonna di flusso di file](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span><span class="sxs-lookup"><span data-stu-id="74908-129">For another sample, see [How to store and fetch binary data into a file stream column](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span></span>

## <a name="resources-in-sql-server-books-online"></a><span data-ttu-id="74908-130">Risorse nella documentazione online di SQL Server</span><span class="sxs-lookup"><span data-stu-id="74908-130">Resources in SQL Server Books Online</span></span>

<span data-ttu-id="74908-131">La documentazione completa per FILESTREAM è disponibile nelle sezioni seguenti nella documentazione Online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="74908-131">The complete documentation for FILESTREAM is located in the following sections in SQL Server Books Online.</span></span>

|<span data-ttu-id="74908-132">Argomento</span><span class="sxs-lookup"><span data-stu-id="74908-132">Topic</span></span>|<span data-ttu-id="74908-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74908-133">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="74908-134">FILESTREAM (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="74908-134">FILESTREAM (SQL Server)</span></span>](/sql/relational-databases/blob/filestream-sql-server)|<span data-ttu-id="74908-135">Viene descritto quando usare l'archiviazione FILESTREAM e come questa consente l'integrazione del Motore di database di SQL Server con un file system NTFS.</span><span class="sxs-lookup"><span data-stu-id="74908-135">Describes when to use FILESTREAM storage and how it integrates the SQL Server Database Engine with an NTFS file system.</span></span>|
|[<span data-ttu-id="74908-136">Creazione di applicazioni Client per i dati FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="74908-136">Create Client Applications for FILESTREAM Data</span></span>](/sql/relational-databases/blob/create-client-applications-for-filestream-data)|<span data-ttu-id="74908-137">Descrive le funzioni API Windows per l'utilizzo di dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="74908-137">Describes the Windows API functions for working with FILESTREAM data.</span></span>|
|[<span data-ttu-id="74908-138">FILESTREAM e altre funzionalità di SQL Server</span><span class="sxs-lookup"><span data-stu-id="74908-138">FILESTREAM and Other SQL Server Features</span></span>](/sql/relational-databases/blob/filestream-compatibility-with-other-sql-server-features)|<span data-ttu-id="74908-139">Vengono illustrate considerazioni, linee guida e limitazioni per l'uso di dati FILESTREAM con le altre funzionalità di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="74908-139">Provides considerations, guidelines and limitations for using FILESTREAM data with other features of SQL Server.</span></span>|

## <a name="see-also"></a><span data-ttu-id="74908-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74908-140">See also</span></span>

- [<span data-ttu-id="74908-141">Tipi di dati SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="74908-141">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [<span data-ttu-id="74908-142">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="74908-142">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="74908-143">Sicurezza dell'accesso di codice e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="74908-143">Code Access Security and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/code-access-security.md)
- [<span data-ttu-id="74908-144">Dati binari e con valori elevati SQL Server</span><span class="sxs-lookup"><span data-stu-id="74908-144">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="74908-145">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="74908-145">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)

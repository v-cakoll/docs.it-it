---
title: Dati FILESTREAM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 2fde543187d1904da93be255878d6c7a99de6bbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="filestream-data"></a><span data-ttu-id="c296c-102">Dati FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c296c-102">FILESTREAM Data</span></span>
<span data-ttu-id="c296c-103">L'attributo di archiviazione FILESTREAM è per i dati (BLOB) binari archiviati in una colonna varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="c296c-103">The FILESTREAM storage attribute is for binary (BLOB) data stored in a varbinary(max) column.</span></span> <span data-ttu-id="c296c-104">Prima di FILESTREAM, l'archiviazione dei dati binari richiedeva una gestione speciale.</span><span class="sxs-lookup"><span data-stu-id="c296c-104">Before FILESTREAM, storing binary data required special handling.</span></span> <span data-ttu-id="c296c-105">I dati non strutturati, come documenti di testo, immagini e video, sono spesso archiviati fuori dal database e questo ne rende complessa la gestione.</span><span class="sxs-lookup"><span data-stu-id="c296c-105">Unstructured data, such as text documents, images and video, is often stored outside of the database, making it difficult to manage.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c296c-106">Per usare i dati FILESTREAM con SqlClient, è necessario installare .NET Framework 3.5 SP1 (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="c296c-106">You must install the .NET Framework 3.5 SP1 (or later) to work with FILESTREAM data using SqlClient.</span></span>  
  
 <span data-ttu-id="c296c-107">Se si specifica l'attributo FILESTREAM in una colonna varbinary(max), in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] i dati vengono archiviati nel file system NTFS locale anziché nel file di database.</span><span class="sxs-lookup"><span data-stu-id="c296c-107">Specifying the FILESTREAM attribute on a varbinary(max) column causes [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] to store the data on the local NTFS file system instead of in the database file.</span></span> <span data-ttu-id="c296c-108">Sebbene vengano archiviati separatamente, è possibile usare le stesse istruzioni [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] supportate per l'uso di dati varbinary(max) archiviati nel database.</span><span class="sxs-lookup"><span data-stu-id="c296c-108">Although it is stored separately, you can use the same [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statements that are supported for working with varbinary(max) data that is stored in the database.</span></span>  
  
## <a name="sqlclient-support-for-filestream"></a><span data-ttu-id="c296c-109">Supporto di SqlClient per FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c296c-109">SqlClient Support for FILESTREAM</span></span>  
 <span data-ttu-id="c296c-110">Il provider di dati [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] per [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], <xref:System.Data.SqlClient>, supporta la lettura e la scrittura nei dati FILESTREAM usando la classe <xref:System.Data.SqlTypes.SqlFileStream> definita nello spazio dei nomi <xref:System.Data.SqlTypes>.</span><span class="sxs-lookup"><span data-stu-id="c296c-110">The [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], <xref:System.Data.SqlClient>, supports reading and writing to FILESTREAM data using the <xref:System.Data.SqlTypes.SqlFileStream> class defined in the <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="c296c-111">`SqlFileStream` eredita dalla classe <xref:System.IO.Stream> che fornisce metodi per la lettura e la scrittura nei flussi di dati.</span><span class="sxs-lookup"><span data-stu-id="c296c-111">`SqlFileStream` inherits from the <xref:System.IO.Stream> class, which provides methods for reading and writing to streams of data.</span></span> <span data-ttu-id="c296c-112">La lettura da un flusso comporta il trasferimento dei dati dal flusso in una struttura di dati, ad esempio una matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="c296c-112">Reading from a stream transfers data from the stream into a data structure, such as an array of bytes.</span></span> <span data-ttu-id="c296c-113">La scrittura comporta il trasferimento dei dati dalla struttura di dati in un flusso.</span><span class="sxs-lookup"><span data-stu-id="c296c-113">Writing transfers the data from the data structure into a stream.</span></span>  
  
### <a name="creating-the-includessnoversionincludesssnoversion-mdmd-table"></a><span data-ttu-id="c296c-114">Creazione di una tabella [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c296c-114">Creating the [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Table</span></span>  
 <span data-ttu-id="c296c-115">Le istruzioni [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] seguenti consentono di creare una tabella denominata employees e di inserire una riga di dati.</span><span class="sxs-lookup"><span data-stu-id="c296c-115">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statements creates a table named employees and inserts a row of data.</span></span> <span data-ttu-id="c296c-116">Dopo avere abilitato l'archiviazione FILESTREAM, è possibile usare questa tabella insieme agli esempi di codice seguenti.</span><span class="sxs-lookup"><span data-stu-id="c296c-116">Once you have enabled FILESTREAM storage, you can use this table in conjunction with the code examples that follow.</span></span> <span data-ttu-id="c296c-117">I collegamenti alle risorse della documentazione online di [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] sono disponibili alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c296c-117">The links to resources in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online are located at the end of this topic.</span></span>  
  
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
  
### <a name="example-reading-overwriting-and-inserting-filestream-data"></a><span data-ttu-id="c296c-118">Esempio: lettura, sovrascrittura e inserimento di dati FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c296c-118">Example: Reading, Overwriting, and Inserting FILESTREAM Data</span></span>  
 <span data-ttu-id="c296c-119">Nell'esempio seguente viene illustrato come leggere i dati da FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c296c-119">The following sample demonstrates how to read data from a FILESTREAM.</span></span> <span data-ttu-id="c296c-120">Il codice consente di ottenere il percorso logico del file, impostando `FileAccess` su `Read` e `FileOptions` su `SequentialScan`.</span><span class="sxs-lookup"><span data-stu-id="c296c-120">The code gets the logical path to the file, setting the `FileAccess` to `Read` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="c296c-121">Tramite il codice vengono quindi letti i byte da SqlFileStream nel buffer.</span><span class="sxs-lookup"><span data-stu-id="c296c-121">The code then reads the bytes from the SqlFileStream into the buffer.</span></span> <span data-ttu-id="c296c-122">I byte vengono infine scritti nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="c296c-122">The bytes are then written to the console window.</span></span>  
  
 <span data-ttu-id="c296c-123">Nell'esempio seguente viene illustrato come scrivere dati in un oggetto FILESTREAM nel quale vengono sovrascritti tutti i dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="c296c-123">The sample also demonstrates how to write data to a FILESTREAM in which all existing data is overwritten.</span></span> <span data-ttu-id="c296c-124">Il codice consente di ottenere il percorso logico del file e di creare `SqlFileStream`, impostando `FileAccess` su `Write` e `FileOptions` su `SequentialScan`.</span><span class="sxs-lookup"><span data-stu-id="c296c-124">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `Write` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="c296c-125">Un singolo byte viene scritto in `SqlFileStream`, sostituendo tutti i dati nel file.</span><span class="sxs-lookup"><span data-stu-id="c296c-125">A single byte is written to the `SqlFileStream`, replacing any data in the file.</span></span>  
  
 <span data-ttu-id="c296c-126">Nell'esempio viene illustrato anche come scrivere i dati in un oggetto FILESTREAM usando il metodo Seek per aggiungere i dati alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="c296c-126">The sample also demonstrates how to write data to a FILESTREAM by using the Seek method to append data to the end of the file.</span></span> <span data-ttu-id="c296c-127">Il codice consente di ottenere il percorso logico del file e di creare `SqlFileStream`, impostando `FileAccess` su `ReadWrite` e `FileOptions` su `SequentialScan`.</span><span class="sxs-lookup"><span data-stu-id="c296c-127">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `ReadWrite` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="c296c-128">Nel codice viene usato il metodo Seek per cercare la fine del file e viene aggiunto un singolo byte al file esistente.</span><span class="sxs-lookup"><span data-stu-id="c296c-128">The code uses the Seek method to seek to the end of the file, appending a single byte to the existing file.</span></span>  
  
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
  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))  
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
} using (SqlConnection connection = new SqlConnection(  
    connStringBuilder.ToString()))  
{  
    connection.Open();  
  
    SqlCommand command = new SqlCommand("", connection);  
    command.CommandText = "select Top(1) Photo.PathName(), "  
    + "GET_FILESTREAM_TRANSACTION_CONTEXT () from employees";  
  
    SqlTransaction tran = connection.BeginTransaction(  
        System.Data.IsolationLevel.ReadCommitted);  
    command.Transaction = tran;  
  
    using (SqlDataReader reader = command.ExecuteReader())  
    {  
        while (reader.Read())  
        {  
            // Get the pointer for file  
            string path = reader.GetString(0);  
            byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
            FileStream fileStream = new SqlFileStream(path,  
                (byte[])reader.GetValue(1),  
                FileAccess.ReadWrite,  
                FileOptions.SequentialScan, 0);  
  
            // Seek to the end of the file  
            fs.Seek(0, SeekOrigin.End);  
  
            // Append a single byte   
            fileStream.WriteByte(0x01);  
            fileStream.Close();  
        }  
    }  
    tran.Commit();  
}  
```  
  
 <span data-ttu-id="c296c-129">Per un altro esempio, vedere [come archiviare e recuperare dati binari in una colonna del flusso di file](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span><span class="sxs-lookup"><span data-stu-id="c296c-129">For another sample, see [How to store and fetch binary data into a file stream column](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span></span>  
  
## <a name="resources-in-includessnoversionincludesssnoversion-mdmd-books-online"></a><span data-ttu-id="c296c-130">Risorse nella documentazione online di [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c296c-130">Resources in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online</span></span>  
 <span data-ttu-id="c296c-131">La documentazione completa per FILESTREAM è disponibile nelle sezioni seguenti della documentazione online di [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c296c-131">The complete documentation for FILESTREAM is located in the following sections in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
|<span data-ttu-id="c296c-132">Argomento</span><span class="sxs-lookup"><span data-stu-id="c296c-132">Topic</span></span>|<span data-ttu-id="c296c-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c296c-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c296c-134">[Progettazione e implementazione di un'archiviazione FILESTREAM](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c296c-134">[Designing and Implementing FILESTREAM Storage](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)</span></span>|<span data-ttu-id="c296c-135">Vengono forniti collegamenti alla documentazione relativa a FILESTREAM e ad argomenti correlati.</span><span class="sxs-lookup"><span data-stu-id="c296c-135">Provides links to FILESTREAM documentation and related topics.</span></span>|  
|<span data-ttu-id="c296c-136">[Panoramica di FILESTREAM](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c296c-136">[FILESTREAM Overview](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)</span></span>|<span data-ttu-id="c296c-137">Viene descritto quando usare l'archiviazione FILESTREAM e come questa consente l'integrazione del Motore di database di SQL Server con un file system NTFS.</span><span class="sxs-lookup"><span data-stu-id="c296c-137">Describes when to use FILESTREAM storage and how it integrates the SQL Server Database Engine with an NTFS file system.</span></span>|  
|<span data-ttu-id="c296c-138">[Introduzione all'archiviazione FILESTREAM](http://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c296c-138">[Getting Started with FILESTREAM Storage](http://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)</span></span>|<span data-ttu-id="c296c-139">Viene descritto come abilitare FILESTREAM in un'istanza di SQL Server, come creare un database e una tabella per archiviare i dati FILESTREAM e come modificare le righe che contengono dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c296c-139">Describes how to enable FILESTREAM on an instance of SQL Server, how to create a database and a table to stored FILESTREAM data, and how to manipulate rows containing FILESTREAM data.</span></span>|  
|<span data-ttu-id="c296c-140">[Utilizzo dell'archiviazione FILESTREAM nelle applicazioni Client](http://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c296c-140">[Using FILESTREAM Storage in Client Applications](http://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)</span></span>|<span data-ttu-id="c296c-141">Vengono descritte le funzioni dell'API Win32 per l'uso dei dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c296c-141">Describes the Win32 API functions for working with FILESTREAM data.</span></span>|  
|<span data-ttu-id="c296c-142">[FILESTREAM e altre funzionalità SQL Server](http://msdn.microsoft.com/library/bb895334\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c296c-142">[FILESTREAM and Other SQL Server Features](http://msdn.microsoft.com/library/bb895334\(SQL.105\).aspx)</span></span>|<span data-ttu-id="c296c-143">Vengono illustrate considerazioni, linee guida e limitazioni per l'uso di dati FILESTREAM con le altre funzionalità di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c296c-143">Provides considerations, guidelines and limitations for using FILESTREAM data with other features of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c296c-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c296c-144">See Also</span></span>  
 [<span data-ttu-id="c296c-145">Tipi di dati SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c296c-145">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="c296c-146">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c296c-146">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="c296c-147">Sicurezza dall'accesso di codice e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c296c-147">Code Access Security and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/code-access-security.md)  
 [<span data-ttu-id="c296c-148">Dati binari e con valori elevati SQL Server</span><span class="sxs-lookup"><span data-stu-id="c296c-148">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="c296c-149">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="c296c-149">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

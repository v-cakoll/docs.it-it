---
title: Oggetti BFILE Oracle
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: bb0a7dad2b7919130097ddd689739b8d17557ea1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="oracle-bfiles"></a><span data-ttu-id="60b0d-102">Oggetti BFILE Oracle</span><span class="sxs-lookup"><span data-stu-id="60b0d-102">Oracle BFILEs</span></span>
<span data-ttu-id="60b0d-103">Il provider di dati .NET Framework per Oracle include la classe <xref:System.Data.OracleClient.OracleBFile>, usata per i tipi di dati <xref:System.Data.OracleClient.OracleType.BFile> Oracle.</span><span class="sxs-lookup"><span data-stu-id="60b0d-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="60b0d-104">Oracle **BFILE** è di tipo di dati Oracle **LOB** tipo di dati che contiene un riferimento a dati binari con dimensioni massime di 4 GB.</span><span class="sxs-lookup"><span data-stu-id="60b0d-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="60b0d-105">Oracle **BFILE** altri Oracle si differenzia da **LOB** tipi di dati, in quanto i dati sono memorizzati in un file fisico nel sistema operativo anziché sul server.</span><span class="sxs-lookup"><span data-stu-id="60b0d-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="60b0d-106">Si noti che il **BFILE** tipo di dati fornisce l'accesso di sola lettura ai dati.</span><span class="sxs-lookup"><span data-stu-id="60b0d-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="60b0d-107">Altre caratteristiche di un **BFILE** tipo di dati che differenziano da un **LOB** il tipo di dati:</span><span class="sxs-lookup"><span data-stu-id="60b0d-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
-   <span data-ttu-id="60b0d-108">Contiene dati non strutturati.</span><span class="sxs-lookup"><span data-stu-id="60b0d-108">Contains unstructured data.</span></span>  
  
-   <span data-ttu-id="60b0d-109">Supporta il chunking sul lato server.</span><span class="sxs-lookup"><span data-stu-id="60b0d-109">Supports server-side chunking.</span></span>  
  
-   <span data-ttu-id="60b0d-110">Usa la semantica di copia di riferimenti.</span><span class="sxs-lookup"><span data-stu-id="60b0d-110">Uses reference copy semantics.</span></span> <span data-ttu-id="60b0d-111">Ad esempio, se si esegue un'operazione di copia su un **BFILE**, solo il **BFILE** locator (ovvero un riferimento al file) viene copiato.</span><span class="sxs-lookup"><span data-stu-id="60b0d-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="60b0d-112">I dati nel file non vengono copiati.</span><span class="sxs-lookup"><span data-stu-id="60b0d-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="60b0d-113">Il **BFILE** il tipo di dati deve essere utilizzato per fare riferimento a LOB di grandi dimensioni e quindi poco pratici da archiviare nel database.</span><span class="sxs-lookup"><span data-stu-id="60b0d-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="60b0d-114">Altre comunicazioni, client e server è sovraccarico quando si utilizza un **BFILE** rispetto al tipo di dati di **LOB** tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="60b0d-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="60b0d-115">È più efficiente per accedere a un **BFILE** se è necessario ottenere una piccola quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="60b0d-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="60b0d-116">Se è necessario ottenere l'intero oggetto, è opportuno accedere a LOB residenti nel database.</span><span class="sxs-lookup"><span data-stu-id="60b0d-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="60b0d-117">Ogni valore non NULL **OracleBFile** oggetto è associato a due entità che definiscono il percorso del file fisico sottostante:</span><span class="sxs-lookup"><span data-stu-id="60b0d-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1.  <span data-ttu-id="60b0d-118">Un oggetto DIRECTORY Oracle, che è un alias del database per una directory nel file system e</span><span class="sxs-lookup"><span data-stu-id="60b0d-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2.  <span data-ttu-id="60b0d-119">Il nome del file fisico sottostante, che si trova nella directory associata all'oggetto DIRECTORY.</span><span class="sxs-lookup"><span data-stu-id="60b0d-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60b0d-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="60b0d-120">Example</span></span>  
 <span data-ttu-id="60b0d-121">Nell'esempio c# seguente viene illustrato come creare un **BFILE** in una tabella Oracle e quindi come recuperarlo sotto forma di un **OracleBFile** oggetto.</span><span class="sxs-lookup"><span data-stu-id="60b0d-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="60b0d-122">Viene illustrato l'utilizzo di <xref:System.Data.OracleClient.OracleDataReader> oggetto e **OracleBFile** **Seek** e **lettura** metodi.</span><span class="sxs-lookup"><span data-stu-id="60b0d-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="60b0d-123">Si noti che per usare questo esempio, è necessario innanzitutto creare una directory denominata "c:\\\bfiles" e un file denominato "MyFile.jpg" sul server Oracle.</span><span class="sxs-lookup"><span data-stu-id="60b0d-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Data;  
using System.Data.OracleClient;  
  
public class Sample  
{  
   public static void Main(string[] args)  
   {  
      OracleConnection connection = new OracleConnection(  
        "Data Source=Oracle8i;Integrated Security=yes");  
      connection.Open();  
  
      OracleCommand command = connection.CreateCommand();  
      command.CommandText =   
        "CREATE or REPLACE DIRECTORY MyDir as 'c:\\bfiles'";  
      command.ExecuteNonQuery();  
      command.CommandText =   
        "DROP TABLE MyBFileTable";  
      try {  
        command.ExecuteNonQuery();  
      }  
      catch {  
      }  
      command.CommandText =   
        "CREATE TABLE MyBFileTable(col1 number, col2 BFILE)";  
      command.ExecuteNonQuery();  
      command.CommandText =   
        "INSERT INTO MyBFileTable values ('2', BFILENAME('MyDir', " +  
        "'MyFile.jpg'))";  
      command.ExecuteNonQuery();  
      command.CommandText = "SELECT * FROM MyBFileTable";  
  
        byte[] buffer = new byte[100];  
  
      OracleDataReader reader = command.ExecuteReader();  
      using (reader) {  
          if (reader.Read()) {  
                OracleBFile bFile = reader.GetOracleBFile(1);  
                using (bFile) {  
                  bFile.Seek(0, SeekOrigin.Begin);  
                  bFile.Read(buffer, 0, 100);  
              }  
          }  
      }  
  
      connection.Close();  
   }  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="60b0d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60b0d-124">See Also</span></span>  
 [<span data-ttu-id="60b0d-125">Oracle e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="60b0d-125">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="60b0d-126">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="60b0d-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

---
title: Oggetti BFILE Oracle
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 40060a7ea8576e08140d972072d086606d640366
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149440"
---
# <a name="oracle-bfiles"></a><span data-ttu-id="8946b-102">Oggetti BFILE Oracle</span><span class="sxs-lookup"><span data-stu-id="8946b-102">Oracle BFILEs</span></span>
<span data-ttu-id="8946b-103">Il provider di dati .NET Framework per Oracle include la classe <xref:System.Data.OracleClient.OracleBFile>, usata per i tipi di dati <xref:System.Data.OracleClient.OracleType.BFile> Oracle.</span><span class="sxs-lookup"><span data-stu-id="8946b-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="8946b-104">Il tipo di dati Oracle **BFILE** è un tipo di dati **LOB** Oracle che contiene un riferimento a dati binari con una dimensione massima di 4 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="8946b-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="8946b-105">Un Oracle **BFILE** differisce dagli altri tipi di dati **LOB** Oracle in quanto i relativi dati vengono archiviati in un file fisico nel sistema operativo anziché nel server.</span><span class="sxs-lookup"><span data-stu-id="8946b-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="8946b-106">Si noti che il tipo di dati **BFILE** fornisce l'accesso in sola lettura ai dati.</span><span class="sxs-lookup"><span data-stu-id="8946b-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="8946b-107">Altre caratteristiche di un tipo di dati BFILE che lo distinguono da un tipo di dati LOB sono che esso:Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span><span class="sxs-lookup"><span data-stu-id="8946b-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
- <span data-ttu-id="8946b-108">Contiene dati non strutturati.</span><span class="sxs-lookup"><span data-stu-id="8946b-108">Contains unstructured data.</span></span>  
  
- <span data-ttu-id="8946b-109">Supporta il chunking sul lato server.</span><span class="sxs-lookup"><span data-stu-id="8946b-109">Supports server-side chunking.</span></span>  
  
- <span data-ttu-id="8946b-110">Usa la semantica di copia di riferimenti.</span><span class="sxs-lookup"><span data-stu-id="8946b-110">Uses reference copy semantics.</span></span> <span data-ttu-id="8946b-111">Ad esempio, se si esegue un'operazione di copia su un **bFILE**, viene copiato solo il localizzatore **BFILE** (che è un riferimento al file).</span><span class="sxs-lookup"><span data-stu-id="8946b-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="8946b-112">I dati nel file non vengono copiati.</span><span class="sxs-lookup"><span data-stu-id="8946b-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="8946b-113">Il tipo di dati **BFILE** deve essere utilizzato per fare riferimento a LOB di grandi dimensioni e pertanto non è pratico archiviare nel database.</span><span class="sxs-lookup"><span data-stu-id="8946b-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="8946b-114">Quando si utilizza un tipo di dati **BFILE** rispetto al tipo di dati **LOB,** è necessario un sovraccarico di client, server e comunicazione.</span><span class="sxs-lookup"><span data-stu-id="8946b-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="8946b-115">È più efficiente accedere a un **BFILE** se è necessario ottenere solo una piccola quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="8946b-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="8946b-116">Se è necessario ottenere l'intero oggetto, è opportuno accedere a LOB residenti nel database.</span><span class="sxs-lookup"><span data-stu-id="8946b-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="8946b-117">Ogni oggetto **OracleBFile** non NULL è associato a due entità che definiscono la posizione del file fisico sottostante:</span><span class="sxs-lookup"><span data-stu-id="8946b-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1. <span data-ttu-id="8946b-118">Un oggetto DIRECTORY Oracle, che è un alias del database per una directory nel file system e</span><span class="sxs-lookup"><span data-stu-id="8946b-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2. <span data-ttu-id="8946b-119">Il nome del file fisico sottostante, che si trova nella directory associata all'oggetto DIRECTORY.</span><span class="sxs-lookup"><span data-stu-id="8946b-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8946b-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="8946b-120">Example</span></span>  
 <span data-ttu-id="8946b-121">Nell'esempio in Cè riportato di seguito viene illustrato come creare un **BFILE** in una tabella Oracle e quindi recuperarlo sotto forma di un **oggetto OracleBFile.**</span><span class="sxs-lookup"><span data-stu-id="8946b-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="8946b-122">Nell'esempio viene <xref:System.Data.OracleClient.OracleDataReader> illustrato l'utilizzo dell'oggetto e **OracleBFile** **Seek** e **Read** metodi.</span><span class="sxs-lookup"><span data-stu-id="8946b-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="8946b-123">Si noti che per utilizzare questo esempio, è necessario\\innanzitutto creare una directory denominata "c: "bfiles" e un file denominato "MyFile.jpg" sul server Oracle.</span><span class="sxs-lookup"><span data-stu-id="8946b-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8946b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8946b-124">See also</span></span>

- [<span data-ttu-id="8946b-125">Oracle e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8946b-125">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="8946b-126">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8946b-126">ADO.NET Overview</span></span>](ado-net-overview.md)

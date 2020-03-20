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
# <a name="oracle-bfiles"></a>Oggetti BFILE Oracle
Il provider di dati .NET Framework per Oracle include la classe <xref:System.Data.OracleClient.OracleBFile>, usata per i tipi di dati <xref:System.Data.OracleClient.OracleType.BFile> Oracle.  
  
 Il tipo di dati Oracle **BFILE** è un tipo di dati **LOB** Oracle che contiene un riferimento a dati binari con una dimensione massima di 4 gigabyte. Un Oracle **BFILE** differisce dagli altri tipi di dati **LOB** Oracle in quanto i relativi dati vengono archiviati in un file fisico nel sistema operativo anziché nel server. Si noti che il tipo di dati **BFILE** fornisce l'accesso in sola lettura ai dati.  
  
 Altre caratteristiche di un tipo di dati BFILE che lo distinguono da un tipo di dati LOB sono che esso:Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:  
  
- Contiene dati non strutturati.  
  
- Supporta il chunking sul lato server.  
  
- Usa la semantica di copia di riferimenti. Ad esempio, se si esegue un'operazione di copia su un **bFILE**, viene copiato solo il localizzatore **BFILE** (che è un riferimento al file). I dati nel file non vengono copiati.  
  
 Il tipo di dati **BFILE** deve essere utilizzato per fare riferimento a LOB di grandi dimensioni e pertanto non è pratico archiviare nel database. Quando si utilizza un tipo di dati **BFILE** rispetto al tipo di dati **LOB,** è necessario un sovraccarico di client, server e comunicazione. È più efficiente accedere a un **BFILE** se è necessario ottenere solo una piccola quantità di dati. Se è necessario ottenere l'intero oggetto, è opportuno accedere a LOB residenti nel database.  
  
 Ogni oggetto **OracleBFile** non NULL è associato a due entità che definiscono la posizione del file fisico sottostante:  
  
1. Un oggetto DIRECTORY Oracle, che è un alias del database per una directory nel file system e  
  
2. Il nome del file fisico sottostante, che si trova nella directory associata all'oggetto DIRECTORY.  
  
## <a name="example"></a>Esempio  
 Nell'esempio in Cè riportato di seguito viene illustrato come creare un **BFILE** in una tabella Oracle e quindi recuperarlo sotto forma di un **oggetto OracleBFile.** Nell'esempio viene <xref:System.Data.OracleClient.OracleDataReader> illustrato l'utilizzo dell'oggetto e **OracleBFile** **Seek** e **Read** metodi. Si noti che per utilizzare questo esempio, è necessario\\innanzitutto creare una directory denominata "c: "bfiles" e un file denominato "MyFile.jpg" sul server Oracle.  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Oracle e ADO.NET](oracle-and-adonet.md)
- [Panoramica di ADO.NET](ado-net-overview.md)

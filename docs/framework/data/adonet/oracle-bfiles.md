---
title: Oggetti BFILE Oracle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 585245464ce3a2ef4b1da6ec2a7e2770af187876
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="oracle-bfiles"></a>Oggetti BFILE Oracle
Il provider di dati .NET Framework per Oracle include la classe <xref:System.Data.OracleClient.OracleBFile>, usata per i tipi di dati <xref:System.Data.OracleClient.OracleType.BFile> Oracle.  
  
 Oracle **BFILE** è di tipo di dati Oracle **LOB** tipo di dati che contiene un riferimento a dati binari con dimensioni massime di 4 GB. Oracle **BFILE** altri Oracle si differenzia da **LOB** tipi di dati, in quanto i dati sono memorizzati in un file fisico nel sistema operativo anziché sul server. Si noti che il **BFILE** tipo di dati fornisce l'accesso di sola lettura ai dati.  
  
 Altre caratteristiche di un **BFILE** tipo di dati che differenziano da un **LOB** il tipo di dati:  
  
-   Contiene dati non strutturati.  
  
-   Supporta il chunking sul lato server.  
  
-   Usa la semantica di copia di riferimenti. Ad esempio, se si esegue un'operazione di copia su un **BFILE**, solo il **BFILE** locator (ovvero un riferimento al file) viene copiato. I dati nel file non vengono copiati.  
  
 Il **BFILE** il tipo di dati deve essere utilizzato per fare riferimento a LOB di grandi dimensioni e quindi poco pratici da archiviare nel database. Altre comunicazioni, client e server è sovraccarico quando si utilizza un **BFILE** rispetto al tipo di dati di **LOB** tipo di dati. È più efficiente per accedere a un **BFILE** se è necessario ottenere una piccola quantità di dati. Se è necessario ottenere l'intero oggetto, è opportuno accedere a LOB residenti nel database.  
  
 Ogni valore non NULL **OracleBFile** oggetto è associato a due entità che definiscono il percorso del file fisico sottostante:  
  
1.  Un oggetto DIRECTORY Oracle, che è un alias del database per una directory nel file system e  
  
2.  Il nome del file fisico sottostante, che si trova nella directory associata all'oggetto DIRECTORY.  
  
## <a name="example"></a>Esempio  
 Nell'esempio c# seguente viene illustrato come creare un **BFILE** in una tabella Oracle e quindi come recuperarlo sotto forma di un **OracleBFile** oggetto. Viene illustrato l'utilizzo di <xref:System.Data.OracleClient.OracleDataReader> oggetto e **OracleBFile** **Seek** e **lettura** metodi. Si noti che per usare questo esempio, è necessario innanzitutto creare una directory denominata "c:\\\bfiles" e un file denominato "MyFile.jpg" sul server Oracle.  
  
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
 [Oracle e ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)

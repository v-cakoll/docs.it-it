---
title: Oggetti BFILE Oracle
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 5bb9f7e67016cf4b1d467935fe302ab4a40edbfa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771969"
---
# <a name="oracle-bfiles"></a>Oggetti BFILE Oracle
Il provider di dati .NET Framework per Oracle include la classe <xref:System.Data.OracleClient.OracleBFile>, usata per i tipi di dati <xref:System.Data.OracleClient.OracleType.BFile> Oracle.  
  
 Oracle **BFILE** è di tipo di dati Oracle **LOB** tipo di dati che contiene un riferimento a dati binari con dimensioni massime di 4 GB. Oracle **BFILE** differisce da altri Oracle **LOB** i tipi di dati in quanto i relativi dati vengono archiviati in un file fisico nel sistema operativo anziché sul server. Si noti che il **BFILE** tipo di dati fornisce l'accesso di sola lettura ai dati.  
  
 Altre caratteristiche di un **BFILE** tipo di dati che distingue da un **LOB** tipo di dati di seguito sono:  
  
- Contiene dati non strutturati.  
  
- Supporta il chunking sul lato server.  
  
- Usa la semantica di copia di riferimenti. Ad esempio, se si esegue un'operazione di copia in una **BFILE**, solo le **BFILE** localizzatore, ovvero un riferimento al file, viene copiato. I dati nel file non vengono copiati.  
  
 Il **BFILE** tipo di dati deve essere utilizzato per fare riferimento a LOB di grandi dimensioni e di conseguenza, non è pratico archiviare nel database. Più client, server e comunicazioni sovraccarico quando si usa una **BFILE** confrontato con tipo di dati di **LOB** tipo di dati. È più efficiente per accedere a un **BFILE** se è necessario solo ottenere una piccola quantità di dati. Se è necessario ottenere l'intero oggetto, è opportuno accedere a LOB residenti nel database.  
  
 Ogni diverso da NULL **OracleBFile** oggetto è associato a due entità che definiscono il percorso del file fisico sottostante:  
  
1. Un oggetto DIRECTORY Oracle, che è un alias del database per una directory nel file system e  
  
2. Il nome del file fisico sottostante, che si trova nella directory associata all'oggetto DIRECTORY.  
  
## <a name="example"></a>Esempio  
 L'esempio c# seguente illustra come creare un **BFILE** in una tabella Oracle e quindi come recuperarlo sotto forma di un **OracleBFile** oggetto. Nell'esempio viene illustrato come utilizzare il <xref:System.Data.OracleClient.OracleDataReader> oggetto e il **OracleBFile** **Seek** e **lettura** metodi. Si noti che per usare questo esempio, è necessario innanzitutto creare una directory denominata "c:\\\bfiles" e il file denominato "MyFile. jpg" sul server Oracle.  
  
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

- [Oracle e ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)

---
title: Oggetti BFILE Oracle
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 214140bb8fcf43154b014ea3db609d355a27af7c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794624"
---
# <a name="oracle-bfiles"></a>Oggetti BFILE Oracle
Il provider di dati .NET Framework per Oracle include la classe <xref:System.Data.OracleClient.OracleBFile>, usata per i tipi di dati <xref:System.Data.OracleClient.OracleType.BFile> Oracle.  
  
 Il tipo di dati Oracle **BFILE** è un tipo di dati **LOB** Oracle che contiene un riferimento a dati binari con una dimensione massima di 4 gigabyte. Un **BFILE** Oracle è diverso dagli altri tipi di dati **LOB** Oracle in quanto i dati vengono archiviati in un file fisico nel sistema operativo invece che nel server. Si noti che il tipo di dati **BFILE** fornisce l'accesso in sola lettura ai dati.  
  
 Le altre caratteristiche di un tipo di dati **BFILE** che lo distinguono da un tipo di dati **LOB** sono le seguenti:  
  
- Contiene dati non strutturati.  
  
- Supporta il chunking sul lato server.  
  
- Usa la semantica di copia di riferimenti. Se, ad esempio, si esegue un'operazione di copia su un **BFILE**, viene copiato solo il localizzatore **BFILE** , ovvero un riferimento al file. I dati nel file non vengono copiati.  
  
 Il tipo di dati **BFILE** deve essere utilizzato per fare riferimento a LOB di grandi dimensioni e pertanto non è pratico archiviarlo nel database. Quando si utilizza un tipo di dati **BFILE** confrontato con il tipo di dati **LOB** , è necessario più sovraccarico di client, server e comunicazioni. È più efficiente accedere a un **BFILE** se è necessario solo ottenere una piccola quantità di dati. Se è necessario ottenere l'intero oggetto, è opportuno accedere a LOB residenti nel database.  
  
 Ogni oggetto **OracleBFile** non null è associato a due entità che definiscono il percorso del file fisico sottostante:  
  
1. Un oggetto DIRECTORY Oracle, che è un alias del database per una directory nel file system e  
  
2. Il nome del file fisico sottostante, che si trova nella directory associata all'oggetto DIRECTORY.  
  
## <a name="example"></a>Esempio  
 Nell'esempio C# seguente viene illustrato come creare un **BFILE** in una tabella Oracle e quindi recuperarlo sotto forma di oggetto **OracleBFile** . Nell'esempio viene illustrato l' <xref:System.Data.OracleClient.OracleDataReader> utilizzo dell'oggetto e dei metodi **Seek** e **Read** di **OracleBFile** . Si noti che per utilizzare questo esempio, è necessario innanzitutto creare una directory denominata "c:\\\bfiles" e un file denominato "MyFile. jpg" nel server Oracle.  
  
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

---
title: Recupero di dati binari
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: bd524ed605f1fe125480bae0949745f4f045f03a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-binary-data"></a>Recupero di dati binari
Per impostazione predefinita, il **DataReader** Carica dati in arrivo come una riga non appena è disponibile un'intera riga di dati. Tuttavia, è necessario gestire gli oggetti BLOB (Binary Large Object, oggetto binario di grandi dimensioni) in modo diverso, poiché è possibile che contengano gigabyte di dati che non possono risiedere in una sola riga. Il **Command. ExecuteReader** metodo presenta un overload che accetta un <xref:System.Data.CommandBehavior> argomento per modificare il comportamento predefinito del **DataReader**. È possibile passare <xref:System.Data.CommandBehavior.SequentialAccess> per il **ExecuteReader** metodo per modificare il comportamento predefinito del **DataReader** in modo che, invece di caricare righe di dati, carichi i dati in modo sequenziale non appena viene ricevuto. Si consiglia di usare questa procedura per caricare BLOB o altre strutture di dati di grandi dimensioni. Notare che questo comportamento può variare a seconda dell'origine dati. La restituzione di un BLOB da Microsoft Access comporta, ad esempio, il caricamento in memoria dell'intero BLOB, anziché il caricamento sequenziale durante la ricezione.  
  
 Quando si imposta la **DataReader** utilizzare **SequentialAccess**, è importante notare la sequenza in cui si accede ai campi restituiti. Il comportamento predefinito del **DataReader**, che carica un'intera riga, non appena è disponibile, consente di accedere ai campi restituiti in qualsiasi ordine fino a quando non viene letta la riga successiva. Quando si utilizza **SequentialAccess** , tuttavia, è necessario accedere ai campi restituiti dal **DataReader** in ordine. Ad esempio, se la query restituisce tre colonne, di cui la terza è un BLOB, è necessario restituire i valori del primo e del secondo campo prima di accedere ai dati BLOB nel terzo campo. Se si accede al terzo campo prima del primo o del secondo, i valori del primo o del secondo campo non saranno più disponibili. Infatti **SequentialAccess** è modificato il **DataReader** per restituire dati in sequenza e i dati non è disponibile dopo il **DataReader** stati letti.  
  
 Quando l'accesso ai dati nel campo BLOB, utilizzare il **GetBytes** o **GetChars** funzioni di accesso tipizzate di **DataReader**, quale compilare una matrice con i dati. È inoltre possibile utilizzare **GetString** per dati di tipo carattere; tuttavia. è probabile che per risparmiare risorse di sistema si preferisca non caricare un intero valore BLOB in un'unica variabile di stringa. È possibile invece specificare una determinata dimensione del buffer da restituire e una posizione iniziale per il primo byte o carattere da leggere dai dati restituiti. **GetBytes** e **GetChars** restituirà un `long` valore, che rappresenta il numero di byte o caratteri restituiti. Se si passa una matrice null a **GetBytes** o **GetChars**, il valore long restituito corrisponderà al numero totale di byte o caratteri del BLOB. Facoltativamente, è possibile specificare un indice nella matrice come posizione iniziale per i dati che vengono letti.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente restituisce l'ID dell'editore e il logo dal **pubs** database di esempio in Microsoft SQL Server. L'identificatore dell'editore (`pub_id`) è un campo di testo è il logo è un'immagine, quindi un BLOB. Poiché il **logo** è una bitmap, nell'esempio vengono restituiti dati binari utilizzando **GetBytes**. Notare che all'identificatore dell'editore nella riga corrente di dati si accede prima del logo, in quanto i campi devono essere letti in modo sequenziale.  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim command As SqlCommand = New SqlCommand( _  
  "SELECT pub_id, logo FROM pub_info", connection)  
  
' Writes the BLOB to a file (*.bmp).  
Dim stream As FileStream                   
' Streams the binary data to the FileStream object.  
Dim writer As BinaryWriter                 
' The size of the BLOB buffer.  
Dim bufferSize As Integer = 100        
' The BLOB byte() buffer to be filled by GetBytes.  
Dim outByte(bufferSize - 1) As Byte    
' The bytes returned from GetBytes.  
Dim retval As Long                     
' The starting position in the BLOB output.  
Dim startIndex As Long = 0             
  
' The publisher id to use in the file name.  
Dim pubID As String = ""              
  
' Open the connection and read data into the DataReader.  
connection.Open()  
Dim reader As SqlDataReader = command.ExecuteReader(CommandBehavior.SequentialAccess)  
  
Do While reader.Read()  
  ' Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0)  
  
  ' Create a file to hold the output.  
  stream = New FileStream( _  
    "logo" & pubID & ".bmp", FileMode.OpenOrCreate, FileAccess.Write)  
  writer = New BinaryWriter(stream)  
  
  ' Reset the starting byte for a new BLOB.  
  startIndex = 0  
  
  ' Read bytes into outByte() and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  
  ' Continue while there are bytes beyond the size of the buffer.  
  Do While retval = bufferSize  
    writer.Write(outByte)  
    writer.Flush()  
  
    ' Reposition start index to end of the last buffer and fill buffer.  
    startIndex += bufferSize  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  Loop  
  
  ' Write the remaining buffer.  
  writer.Write(outByte, 0 , retval - 1)  
  writer.Flush()  
  
  ' Close the output file.  
  writer.Close()  
  stream.Close()  
Loop  
  
' Close the reader and the connection.  
reader.Close()  
connection.Close()  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
SqlCommand command = new SqlCommand(  
  "SELECT pub_id, logo FROM pub_info", connection);  
  
// Writes the BLOB to a file (*.bmp).  
FileStream stream;                            
// Streams the BLOB to the FileStream object.  
BinaryWriter writer;                          
  
// Size of the BLOB buffer.  
int bufferSize = 100;                     
// The BLOB byte[] buffer to be filled by GetBytes.  
byte[] outByte = new byte[bufferSize];    
// The bytes returned from GetBytes.  
long retval;                              
// The starting position in the BLOB output.  
long startIndex = 0;                      
  
// The publisher id to use in the file name.  
string pubID = "";                       
  
// Open the connection and read data into the DataReader.  
connection.Open();  
SqlDataReader reader = command.ExecuteReader(CommandBehavior.SequentialAccess);  
  
while (reader.Read())  
{  
  // Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0);    
  
  // Create a file to hold the output.  
  stream = new FileStream(  
    "logo" + pubID + ".bmp", FileMode.OpenOrCreate, FileAccess.Write);  
  writer = new BinaryWriter(stream);  
  
  // Reset the starting byte for the new BLOB.  
  startIndex = 0;  
  
  // Read bytes into outByte[] and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  
  // Continue while there are bytes beyond the size of the buffer.  
  while (retval == bufferSize)  
  {  
    writer.Write(outByte);  
    writer.Flush();  
  
    // Reposition start index to end of last buffer and fill buffer.  
    startIndex += bufferSize;  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  }  
  
  // Write the remaining buffer.  
  writer.Write(outByte, 0, (int)retval);  
  writer.Flush();  
  
  // Close the output file.  
  writer.Close();  
  stream.Close();  
}  
  
// Close the reader and the connection.  
reader.Close();  
connection.Close();  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Utilizzo di DataReader](http://msdn.microsoft.com/en-us/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [Dati binari e con valori elevati SQL Server](../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)

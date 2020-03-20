---
title: Recupero di dati binari
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
ms.openlocfilehash: c914a9b0780e2e87e177502b0f9faff0e7c4b617
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149050"
---
# <a name="retrieving-binary-data"></a>Recupero di dati binari
Per impostazione predefinita, il **DataReader** carica i dati in ingresso come riga non appena è disponibile un'intera riga di dati. Tuttavia, è necessario gestire gli oggetti BLOB (Binary Large Object, oggetto binario di grandi dimensioni) in modo diverso, poiché è possibile che contengano gigabyte di dati che non possono risiedere in una sola riga. Il **metodo Command.ExecuteReader** dispone di <xref:System.Data.CommandBehavior> un overload che accetta un argomento per modificare il comportamento predefinito di **DataReader**. È possibile <xref:System.Data.CommandBehavior.SequentialAccess> passare al **metodo ExecuteReader** per modificare il comportamento predefinito di **DataReader** in modo che, anziché caricare righe di dati, caricherà i dati in sequenza man mano che vengono ricevuti. Si consiglia di usare questa procedura per caricare BLOB o altre strutture di dati di grandi dimensioni. Notare che questo comportamento può variare a seconda dell'origine dati. La restituzione di un BLOB da Microsoft Access comporta, ad esempio, il caricamento in memoria dell'intero BLOB, anziché il caricamento sequenziale durante la ricezione.  
  
 Quando si imposta **DataReader** per l'utilizzo di **SequentialAccess**, è importante prendere nota della sequenza in cui si accede ai campi restituiti. Il comportamento predefinito di **DataReader**, che carica un'intera riga non appena disponibile, consente di accedere ai campi restituiti in qualsiasi ordine fino a quando non viene letta la riga successiva. Quando si utilizza **l'accesso sequenziale,** tuttavia, è necessario accedere ai campi restituiti da **DataReader** nell'ordine. Ad esempio, se la query restituisce tre colonne, di cui la terza è un BLOB, è necessario restituire i valori del primo e del secondo campo prima di accedere ai dati BLOB nel terzo campo. Se si accede al terzo campo prima del primo o del secondo, i valori del primo o del secondo campo non saranno più disponibili. Ciò è dovuto al fatto che **SequentialAccess** ha modificato **il DataReader** per restituire i dati in sequenza e i dati non sono disponibili dopo che il **DataReader** li ha letti in precedente.  
  
 Quando si accede ai dati nel campo BLOB, utilizzare le funzioni di accesso tipizzate **GetBytes** o **GetChars** di **DataReader**, che riempiono i dati di una matrice. È inoltre possibile utilizzare **GetString** per i dati di tipo carattere; Tuttavia. è probabile che per risparmiare risorse di sistema si preferisca non caricare un intero valore BLOB in un'unica variabile di stringa. È possibile invece specificare una determinata dimensione del buffer da restituire e una posizione iniziale per il primo byte o carattere da leggere dai dati restituiti. **GetBytes** e **GetChars** `long` restituiranno un valore, che rappresenta il numero di byte o caratteri restituiti. Se si passa una matrice null a **GetBytes** o **GetChars**, il valore long restituito sarà il numero totale di byte o caratteri nel BLOB. Facoltativamente, è possibile specificare un indice nella matrice come posizione iniziale per i dati che vengono letti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono restituiti l'ID e il logo dell'editore dal database di esempio **pubs** in Microsoft SQL Server. L'identificatore dell'editore (`pub_id`) è un campo di testo è il logo è un'immagine, quindi un BLOB. Poiché il campo **logo** è una bitmap, nell'esempio vengono restituiti dati binari utilizzando **GetBytes**. Notare che all'identificatore dell'editore nella riga corrente di dati si accede prima del logo, in quanto i campi devono essere letti in modo sequenziale.  
  
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

- [SQL Server Binary and Large-Value Data](./sql/sql-server-binary-and-large-value-data.md)
- [Panoramica di ADO.NET](ado-net-overview.md)

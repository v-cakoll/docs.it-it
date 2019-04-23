---
title: Recupero di dati binari
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
ms.openlocfilehash: 068b84e8704b54e6aea148ec5fc5bf9f0c4cb958
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085974"
---
# <a name="retrieving-binary-data"></a>Recupero di dati binari
Per impostazione predefinita, il **DataReader** carica i dati in arrivo come una riga, non appena è disponibile un'intera riga di dati. Tuttavia, è necessario gestire gli oggetti BLOB (Binary Large Object, oggetto binario di grandi dimensioni) in modo diverso, poiché è possibile che contengano gigabyte di dati che non possono risiedere in una sola riga. Il **Command. ExecuteReader** metodo ha un overload che accetta un <xref:System.Data.CommandBehavior> per modificare il comportamento predefinito dell'argomento il **DataReader**. È possibile passare <xref:System.Data.CommandBehavior.SequentialAccess> per il **ExecuteReader** metodo per modificare il comportamento predefinito del **DataReader** in modo che invece di caricare le righe di dati, caricherà i dati in modo sequenziale non appena viene ricevuto. Si consiglia di usare questa procedura per caricare BLOB o altre strutture di dati di grandi dimensioni. Notare che questo comportamento può variare a seconda dell'origine dati. La restituzione di un BLOB da Microsoft Access comporta, ad esempio, il caricamento in memoria dell'intero BLOB, anziché il caricamento sequenziale durante la ricezione.  
  
 Quando si impostano i **DataReader** usare **SequentialAccess**, è importante notare la sequenza in cui si accede ai campi restituiti. Il comportamento predefinito del **DataReader**, che consente di caricare un'intera riga, non appena è disponibile, consente di accedere ai campi restituiti in qualsiasi ordine fino a quando non viene letta la riga successiva. Quando si usa **SequentialAccess** tuttavia, è necessario accedere ai campi restituiti dai **DataReader** in ordine. Ad esempio, se la query restituisce tre colonne, di cui la terza è un BLOB, è necessario restituire i valori del primo e del secondo campo prima di accedere ai dati BLOB nel terzo campo. Se si accede al terzo campo prima del primo o del secondo, i valori del primo o del secondo campo non saranno più disponibili. Infatti **SequentialAccess** ha modificato il **DataReader** per restituire i dati in sequenza e i dati non è disponibile dopo la **DataReader** stati letti.  
  
 Quando si accede ai dati del campo BLOB, usare il **GetBytes** oppure **GetChars** funzioni di accesso tipizzate il **DataReader**, quale compilare una matrice con dati. È anche possibile usare **GetString** per dati di tipo carattere; tuttavia. è probabile che per risparmiare risorse di sistema si preferisca non caricare un intero valore BLOB in un'unica variabile di stringa. È possibile invece specificare una determinata dimensione del buffer da restituire e una posizione iniziale per il primo byte o carattere da leggere dai dati restituiti. **GetBytes** e **GetChars** restituirà un `long` valore, che rappresenta il numero di byte o caratteri restituiti. Se si passa una matrice null per **GetBytes** oppure **GetChars**, il valore long restituito corrisponderà al numero totale di byte o caratteri nell'oggetto BLOB. Facoltativamente, è possibile specificare un indice nella matrice come posizione iniziale per i dati che vengono letti.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente restituisce l'ID dell'editore e il logo dal **pubs** database di esempio in Microsoft SQL Server. L'identificatore dell'editore (`pub_id`) è un campo di testo è il logo è un'immagine, quindi un BLOB. Poiché il **logo** campo è una bitmap, nell'esempio vengono restituiti i dati binari utilizzando **GetBytes**. Notare che all'identificatore dell'editore nella riga corrente di dati si accede prima del logo, in quanto i campi devono essere letti in modo sequenziale.  
  
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

- [Dati binari e con valori elevati SQL Server](../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)

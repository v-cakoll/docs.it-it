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
# <a name="retrieving-binary-data"></a><span data-ttu-id="2f7cc-102">Recupero di dati binari</span><span class="sxs-lookup"><span data-stu-id="2f7cc-102">Retrieving Binary Data</span></span>
<span data-ttu-id="2f7cc-103">Per impostazione predefinita, il **DataReader** carica i dati in ingresso come riga non appena è disponibile un'intera riga di dati.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-103">By default, the **DataReader** loads incoming data as a row as soon as an entire row of data is available.</span></span> <span data-ttu-id="2f7cc-104">Tuttavia, è necessario gestire gli oggetti BLOB (Binary Large Object, oggetto binario di grandi dimensioni) in modo diverso, poiché è possibile che contengano gigabyte di dati che non possono risiedere in una sola riga.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-104">Binary large objects (BLOBs) need different treatment, however, because they can contain gigabytes of data that cannot be contained in a single row.</span></span> <span data-ttu-id="2f7cc-105">Il **metodo Command.ExecuteReader** dispone di <xref:System.Data.CommandBehavior> un overload che accetta un argomento per modificare il comportamento predefinito di **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-105">The **Command.ExecuteReader** method has an overload that will take a <xref:System.Data.CommandBehavior> argument to modify the default behavior of the **DataReader**.</span></span> <span data-ttu-id="2f7cc-106">È possibile <xref:System.Data.CommandBehavior.SequentialAccess> passare al **metodo ExecuteReader** per modificare il comportamento predefinito di **DataReader** in modo che, anziché caricare righe di dati, caricherà i dati in sequenza man mano che vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-106">You can pass <xref:System.Data.CommandBehavior.SequentialAccess> to the **ExecuteReader** method to modify the default behavior of the **DataReader** so that instead of loading rows of data, it will load data sequentially as it is received.</span></span> <span data-ttu-id="2f7cc-107">Si consiglia di usare questa procedura per caricare BLOB o altre strutture di dati di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-107">This is ideal for loading BLOBs or other large data structures.</span></span> <span data-ttu-id="2f7cc-108">Notare che questo comportamento può variare a seconda dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-108">Note that this behavior may depend on your data source.</span></span> <span data-ttu-id="2f7cc-109">La restituzione di un BLOB da Microsoft Access comporta, ad esempio, il caricamento in memoria dell'intero BLOB, anziché il caricamento sequenziale durante la ricezione.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-109">For example, returning a BLOB from Microsoft Access will load the entire BLOB being loaded into memory, rather than sequentially as it is received.</span></span>  
  
 <span data-ttu-id="2f7cc-110">Quando si imposta **DataReader** per l'utilizzo di **SequentialAccess**, è importante prendere nota della sequenza in cui si accede ai campi restituiti.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-110">When setting the **DataReader** to use **SequentialAccess**, it is important to note the sequence in which you access the fields returned.</span></span> <span data-ttu-id="2f7cc-111">Il comportamento predefinito di **DataReader**, che carica un'intera riga non appena disponibile, consente di accedere ai campi restituiti in qualsiasi ordine fino a quando non viene letta la riga successiva.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-111">The default behavior of the **DataReader**, which loads an entire row as soon as it is available, allows you to access the fields returned in any order until the next row is read.</span></span> <span data-ttu-id="2f7cc-112">Quando si utilizza **l'accesso sequenziale,** tuttavia, è necessario accedere ai campi restituiti da **DataReader** nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-112">When using **SequentialAccess** however, you must access the fields returned by the **DataReader** in order.</span></span> <span data-ttu-id="2f7cc-113">Ad esempio, se la query restituisce tre colonne, di cui la terza è un BLOB, è necessario restituire i valori del primo e del secondo campo prima di accedere ai dati BLOB nel terzo campo.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-113">For example, if your query returns three columns, the third of which is a BLOB, you must return the values of the first and second fields before accessing the BLOB data in the third field.</span></span> <span data-ttu-id="2f7cc-114">Se si accede al terzo campo prima del primo o del secondo, i valori del primo o del secondo campo non saranno più disponibili.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-114">If you access the third field before the first or second fields, the first and second field values are no longer available.</span></span> <span data-ttu-id="2f7cc-115">Ciò è dovuto al fatto che **SequentialAccess** ha modificato **il DataReader** per restituire i dati in sequenza e i dati non sono disponibili dopo che il **DataReader** li ha letti in precedente.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-115">This is because **SequentialAccess** has modified the **DataReader** to return data in sequence and the data is not available after the **DataReader** has read past it.</span></span>  
  
 <span data-ttu-id="2f7cc-116">Quando si accede ai dati nel campo BLOB, utilizzare le funzioni di accesso tipizzate **GetBytes** o **GetChars** di **DataReader**, che riempiono i dati di una matrice.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-116">When accessing the data in the BLOB field, use the **GetBytes** or **GetChars** typed accessors of the **DataReader**, which fill an array with data.</span></span> <span data-ttu-id="2f7cc-117">È inoltre possibile utilizzare **GetString** per i dati di tipo carattere; Tuttavia.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-117">You can also use **GetString** for character data; however.</span></span> <span data-ttu-id="2f7cc-118">è probabile che per risparmiare risorse di sistema si preferisca non caricare un intero valore BLOB in un'unica variabile di stringa.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-118">to conserve system resources you might not want to load an entire BLOB value into a single string variable.</span></span> <span data-ttu-id="2f7cc-119">È possibile invece specificare una determinata dimensione del buffer da restituire e una posizione iniziale per il primo byte o carattere da leggere dai dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-119">You can instead specify a specific buffer size of data to be returned, and a starting location for the first byte or character to be read from the returned data.</span></span> <span data-ttu-id="2f7cc-120">**GetBytes** e **GetChars** `long` restituiranno un valore, che rappresenta il numero di byte o caratteri restituiti.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-120">**GetBytes** and **GetChars** will return a `long` value, which represents the number of bytes or characters returned.</span></span> <span data-ttu-id="2f7cc-121">Se si passa una matrice null a **GetBytes** o **GetChars**, il valore long restituito sarà il numero totale di byte o caratteri nel BLOB.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-121">If you pass a null array to **GetBytes** or **GetChars**, the long value returned will be the total number of bytes or characters in the BLOB.</span></span> <span data-ttu-id="2f7cc-122">Facoltativamente, è possibile specificare un indice nella matrice come posizione iniziale per i dati che vengono letti.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-122">You can optionally specify an index in the array as a starting position for the data being read.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f7cc-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f7cc-123">Example</span></span>  
 <span data-ttu-id="2f7cc-124">Nell'esempio seguente vengono restituiti l'ID e il logo dell'editore dal database di esempio **pubs** in Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-124">The following example returns the publisher ID and logo from the **pubs** sample database in Microsoft SQL Server.</span></span> <span data-ttu-id="2f7cc-125">L'identificatore dell'editore (`pub_id`) è un campo di testo è il logo è un'immagine, quindi un BLOB.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-125">The publisher ID (`pub_id`) is a character field, and the logo is an image, which is a BLOB.</span></span> <span data-ttu-id="2f7cc-126">Poiché il campo **logo** è una bitmap, nell'esempio vengono restituiti dati binari utilizzando **GetBytes**.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-126">Because the **logo** field is a bitmap, the example returns binary data using **GetBytes**.</span></span> <span data-ttu-id="2f7cc-127">Notare che all'identificatore dell'editore nella riga corrente di dati si accede prima del logo, in quanto i campi devono essere letti in modo sequenziale.</span><span class="sxs-lookup"><span data-stu-id="2f7cc-127">Notice that the publisher ID is accessed for the current row of data before the logo, because the fields must be accessed sequentially.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2f7cc-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f7cc-128">See also</span></span>

- [<span data-ttu-id="2f7cc-129">SQL Server Binary and Large-Value Data</span><span class="sxs-lookup"><span data-stu-id="2f7cc-129">SQL Server Binary and Large-Value Data</span></span>](./sql/sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="2f7cc-130">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2f7cc-130">ADO.NET Overview</span></span>](ado-net-overview.md)

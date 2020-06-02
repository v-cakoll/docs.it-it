---
title: Decrittografia di dati
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [.NET Framework], decryption
- symmetric decryption
- asymmetric decryption
- decryption
ms.assetid: 9b266b6c-a9b2-4d20-afd8-b3a0d8fd48a0
ms.openlocfilehash: 844561c0d207106a183243f5f2b3e0cea3e70422
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288368"
---
# <a name="decrypting-data"></a><span data-ttu-id="4d259-102">Decrittografia di dati</span><span class="sxs-lookup"><span data-stu-id="4d259-102">Decrypting Data</span></span>

<span data-ttu-id="4d259-103">La decrittografia è l'inverso della crittografia.</span><span class="sxs-lookup"><span data-stu-id="4d259-103">Decryption is the reverse operation of encryption.</span></span> <span data-ttu-id="4d259-104">Per la crittografia a chiave privata è necessario conoscere sia la chiave che il valore di inizializzazione usati per crittografare i dati.</span><span class="sxs-lookup"><span data-stu-id="4d259-104">For secret-key encryption, you must know both the key and IV that were used to encrypt the data.</span></span> <span data-ttu-id="4d259-105">Per la crittografia a chiave pubblica, è necessario conoscere sia la chiave pubblica (se i dati sono stati crittografati mediante la chiave privata) che la chiave privata (se i dati sono stati crittografati mediante la chiave pubblica).</span><span class="sxs-lookup"><span data-stu-id="4d259-105">For public-key encryption, you must know either the public key (if the data was encrypted using the private key) or the private key (if the data was encrypted using the public key).</span></span>

## <a name="symmetric-decryption"></a><span data-ttu-id="4d259-106">Decrittografia simmetrica</span><span class="sxs-lookup"><span data-stu-id="4d259-106">Symmetric Decryption</span></span>

<span data-ttu-id="4d259-107">La decrittografia dei dati crittografati con gli algoritmi simmetrici è simile al processo usato per crittografare i dati con algoritmi simmetrici.</span><span class="sxs-lookup"><span data-stu-id="4d259-107">The decryption of data encrypted with symmetric algorithms is similar to the process used to encrypt data with symmetric algorithms.</span></span> <span data-ttu-id="4d259-108">La classe <xref:System.Security.Cryptography.CryptoStream> viene usata con le classi di crittografia simmetrica fornite da .NET Framework per decrittografare i dati letti da qualsiasi oggetto flusso gestito.</span><span class="sxs-lookup"><span data-stu-id="4d259-108">The <xref:System.Security.Cryptography.CryptoStream> class is used with symmetric cryptography classes provided by the .NET Framework to decrypt data read from any managed stream object.</span></span>

<span data-ttu-id="4d259-109">L'esempio seguente illustra come creare una nuova istanza della classe <xref:System.Security.Cryptography.RijndaelManaged> e usarla per eseguire la decrittografia su un oggetto <xref:System.Security.Cryptography.CryptoStream> .</span><span class="sxs-lookup"><span data-stu-id="4d259-109">The following example illustrates how to create a new instance of the <xref:System.Security.Cryptography.RijndaelManaged> class and use it to perform decryption on a <xref:System.Security.Cryptography.CryptoStream> object.</span></span> <span data-ttu-id="4d259-110">Questo esempio crea prima di tutto una nuova istanza della classe **RijndaelManaged** .</span><span class="sxs-lookup"><span data-stu-id="4d259-110">This example first creates a new instance of the **RijndaelManaged** class.</span></span> <span data-ttu-id="4d259-111">Crea quindi un oggetto **CryptoStream** e lo inizializza sul valore di un flusso gestito denominato `myStream`.</span><span class="sxs-lookup"><span data-stu-id="4d259-111">Next it creates a **CryptoStream** object and initializes it to the value of a managed stream called `myStream`.</span></span> <span data-ttu-id="4d259-112">Al metodo **CreateDecryptor** della classe **RijndaelManaged** vengono quindi passati la stessa chiave e lo stesso valore di inizializzazione usati per la crittografia e il metodo viene quindi passato al costruttore **CryptoStream** .</span><span class="sxs-lookup"><span data-stu-id="4d259-112">Next, the **CreateDecryptor** method from the **RijndaelManaged** class is passed the same key and IV that was used for encryption and is then passed to the **CryptoStream** constructor.</span></span> <span data-ttu-id="4d259-113">L'enumerazione **CryptoStreamMode.Read** viene infine passata al costruttore **CryptoStream** per specificare l'accesso in lettura al flusso.</span><span class="sxs-lookup"><span data-stu-id="4d259-113">Finally, the **CryptoStreamMode.Read** enumeration is passed to the **CryptoStream** constructor to specify read access to the stream.</span></span>

```vb
Dim rmCrypto As New RijndaelManaged()
Dim cryptStream As New CryptoStream(myStream, rmCrypto.CreateDecryptor(rmCrypto.Key, rmCrypto.IV), CryptoStreamMode.Read)
```

```csharp
RijndaelManaged rmCrypto = new RijndaelManaged();
CryptoStream cryptStream = new CryptoStream(myStream, rmCrypto.CreateDecryptor(Key, IV), CryptoStreamMode.Read);
```

<span data-ttu-id="4d259-114">L'esempio seguente illustra l'intero processo di creazione di un flusso, decrittografia del flusso, lettura dal flusso e chiusura dei flussi.</span><span class="sxs-lookup"><span data-stu-id="4d259-114">The following example shows the entire process of creating a stream, decrypting the stream, reading from the stream, and closing the streams.</span></span> <span data-ttu-id="4d259-115">Viene creato un oggetto <xref:System.Net.Sockets.TcpListener> che inizializza un flusso di rete quando viene stabilita una connessione all'oggetto in ascolto.</span><span class="sxs-lookup"><span data-stu-id="4d259-115">A <xref:System.Net.Sockets.TcpListener> object is created that initializes a network stream when a connection to the listening object is made.</span></span> <span data-ttu-id="4d259-116">Il flusso di rete viene quindi decrittografato mediante la classe **CryptoStream** e la classe **RijndaelManaged** .</span><span class="sxs-lookup"><span data-stu-id="4d259-116">The network stream is then decrypted using the **CryptoStream** class and the **RijndaelManaged** class.</span></span> <span data-ttu-id="4d259-117">Questo esempio presuppone che il valore della chiave e il valore di inizializzazione siano stati trasferiti correttamente o siano stati concordati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="4d259-117">This example assumes that the key and IV values have been either successfully transferred or previously agreed upon.</span></span> <span data-ttu-id="4d259-118">Non mostra il codice necessario per crittografare e trasferire questi valori.</span><span class="sxs-lookup"><span data-stu-id="4d259-118">It does not show the code needed to encrypt and transfer these values.</span></span>

```vb
Imports System.IO
Imports System.Net
Imports System.Net.Sockets
Imports System.Security.Cryptography
Imports System.Threading

Module Module1
    Sub Main()
            'The key and IV must be the same values that were used
            'to encrypt the stream.
            Dim key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
            Dim iv As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
        Try
            'Initialize a TCPListener on port 11000
            'using the current IP address.
            Dim tcpListen As New TcpListener(IPAddress.Any, 11000)

            'Start the listener.
            tcpListen.Start()

            'Check for a connection every five seconds.
            While Not tcpListen.Pending()
                Console.WriteLine("Still listening. Will try in 5 seconds.")

                Thread.Sleep(5000)
            End While

            'Accept the client if one is found.
            Dim tcp As TcpClient = tcpListen.AcceptTcpClient()

            'Create a network stream from the connection.
            Dim netStream As NetworkStream = tcp.GetStream()

            'Create a new instance of the RijndaelManaged class
            'and decrypt the stream.
            Dim rmCrypto As New RijndaelManaged()

            'Create an instance of the CryptoStream class, pass it the NetworkStream, and decrypt
            'it with the Rijndael class using the key and IV.
            Dim cryptStream As New CryptoStream(netStream, rmCrypto.CreateDecryptor(key, iv), CryptoStreamMode.Read)

            'Read the stream.
            Dim sReader As New StreamReader(cryptStream)

            'Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd())

            'Close the streams.
            sReader.Close()
            netStream.Close()
            tcp.Close()
            'Catch any exceptions.
        Catch
            Console.WriteLine("The Listener Failed.")
        End Try
    End Sub
End Module
```

```csharp
using System;
using System.IO;
using System.Net;
using System.Net.Sockets;
using System.Security.Cryptography;
using System.Threading;

class Class1
{
   static void Main(string[] args)
   {
      //The key and IV must be the same values that were used
      //to encrypt the stream.
      byte[] key = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};
      byte[] iv = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};
      try
      {
         //Initialize a TCPListener on port 11000
         //using the current IP address.
         TcpListener tcpListen = new TcpListener(IPAddress.Any, 11000);

         //Start the listener.
         tcpListen.Start();

         //Check for a connection every five seconds.
         while(!tcpListen.Pending())
         {
            Console.WriteLine("Still listening. Will try in 5 seconds.");
            Thread.Sleep(5000);
         }

         //Accept the client if one is found.
         TcpClient tcp = tcpListen.AcceptTcpClient();

         //Create a network stream from the connection.
         NetworkStream netStream = tcp.GetStream();

         //Create a new instance of the RijndaelManaged class
         // and decrypt the stream.
         RijndaelManaged rmCrypto = new RijndaelManaged();

         //Create a CryptoStream, pass it the NetworkStream, and decrypt
         //it with the Rijndael class using the key and IV.
         CryptoStream cryptStream = new CryptoStream(netStream,
            rmCrypto.CreateDecryptor(key, iv),
            CryptoStreamMode.Read);

         //Read the stream.
         StreamReader sReader = new StreamReader(cryptStream);

         //Display the message.
         Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd());

         //Close the streams.
         sReader.Close();
         netStream.Close();
         tcp.Close();
      }
      //Catch any exceptions.
      catch
      {
         Console.WriteLine("The Listener Failed.");
      }
   }
}
```

<span data-ttu-id="4d259-119">Per permettere il funzionamento dell'esempio precedente, è necessario stabilire una connessione crittografata con il listener.</span><span class="sxs-lookup"><span data-stu-id="4d259-119">For the previous sample to work, an encrypted connection must be made to the listener.</span></span> <span data-ttu-id="4d259-120">La connessione deve usare la stessa chiave, lo stesso valore di inizializzazione e lo stesso algoritmo usati nel listener.</span><span class="sxs-lookup"><span data-stu-id="4d259-120">The connection must use the same key, IV, and algorithm used in the listener.</span></span> <span data-ttu-id="4d259-121">Se si stabilisce la connessione, il messaggio verrà crittografato e visualizzato nella console.</span><span class="sxs-lookup"><span data-stu-id="4d259-121">If such a connection is made, the message is decrypted and displayed to the console.</span></span>

## <a name="asymmetric-decryption"></a><span data-ttu-id="4d259-122">Decrittografia asimmetrica</span><span class="sxs-lookup"><span data-stu-id="4d259-122">Asymmetric Decryption</span></span>

<span data-ttu-id="4d259-123">In genere, una parte (parte A) genera la sia la chiave pubblica che quella privata e archivia la chiave in memoria o in un contenitore di chiavi crittografiche.</span><span class="sxs-lookup"><span data-stu-id="4d259-123">Typically, a party (party A) generates both a public and private key and stores the key either in memory or in a cryptographic key container.</span></span> <span data-ttu-id="4d259-124">La parte A invia quindi la chiave pubblica a un'altra parte (parte B).</span><span class="sxs-lookup"><span data-stu-id="4d259-124">Party A then sends the public key to another party (party B).</span></span> <span data-ttu-id="4d259-125">Utilizzando la chiave pubblica, l'entità B crittografa i dati e li invia all'entità A. Dopo la ricezione dei dati, l'entità A la decrittografa usando la chiave privata corrispondente A.</span><span class="sxs-lookup"><span data-stu-id="4d259-125">Using the public key, party B encrypts data and sends the data back to party A. After receiving the data, party A decrypts it using the private key that corresponds.</span></span> <span data-ttu-id="4d259-126">La decrittografia avrà esito positivo solo se la parte A usa la chiave privata corrispondente alla chiave pubblica usata dalla parte B per crittografare i dati.</span><span class="sxs-lookup"><span data-stu-id="4d259-126">Decryption will be successful only if party A uses the private key that corresponds to the public key Party B used to encrypt the data.</span></span>

<span data-ttu-id="4d259-127">Per informazioni su come archiviare una chiave asimmetrica in un contenitore protetto di chiavi crittografiche e su come recuperare in seguito la chiave asimmetrica, vedere [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="4d259-127">For information on how to store an asymmetric key in secure cryptographic key container and how to later retrieve the asymmetric key, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>

<span data-ttu-id="4d259-128">L'esempio seguente illustra la decrittografia di due matrici di byte che rappresentano una chiave simmetrica e il valore di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="4d259-128">The following example illustrates the decryption of two arrays of bytes that represent a symmetric key and IV.</span></span> <span data-ttu-id="4d259-129">Per informazioni su come estrarre la chiave pubblica simmetrica dall'oggetto <xref:System.Security.Cryptography.RSACryptoServiceProvider> in un formato facilmente inviabile a terze parti, vedere [Encrypting Data](encrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="4d259-129">For information on how to extract the asymmetric public key from the <xref:System.Security.Cryptography.RSACryptoServiceProvider> object in a format that you can easily send to a third party, see [Encrypting Data](encrypting-data.md).</span></span>

```vb
'Create a new instance of the RSACryptoServiceProvider class.
Dim rsa As New RSACryptoServiceProvider()

' Export the public key information and send it to a third party.
' Wait for the third party to encrypt some data and send it back.

'Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, False)
symmetricIV = rsa.Decrypt(encryptedSymmetricIV, False)
```

```csharp
//Create a new instance of the RSACryptoServiceProvider class.
RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();

// Export the public key information and send it to a third party.
// Wait for the third party to encrypt some data and send it back.

//Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, false);
symmetricIV = rsa.Decrypt(encryptedSymmetricIV , false);
```

## <a name="see-also"></a><span data-ttu-id="4d259-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d259-130">See also</span></span>

- [<span data-ttu-id="4d259-131">Generazione di chiavi per crittografia e decrittografia</span><span class="sxs-lookup"><span data-stu-id="4d259-131">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="4d259-132">Encrypting Data</span><span class="sxs-lookup"><span data-stu-id="4d259-132">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="4d259-133">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="4d259-133">Cryptographic Services</span></span>](cryptographic-services.md)

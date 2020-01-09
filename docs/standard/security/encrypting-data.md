---
title: Crittografia dei dati
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET Framework], symmetric
- symmetric encryption
- cryptography [.NET Framework], asymmetric
- asymmetric encryption
ms.assetid: 7ecce51f-db5f-4bd4-9321-cceb6fcb2a77
ms.openlocfilehash: b335e0d39c1809b028e2005a472fe77729e9d267
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706214"
---
# <a name="encrypting-data"></a>Crittografia dei dati
La crittografia simmetrica e quella asimmetrica vengono eseguite usando processi diversi. La crittografia simmetrica viene eseguita sui flussi e di conseguenza è utile per crittografare grandi quantità di dati. La crittografia asimmetrica viene eseguita su un numero ridotto di byte e di conseguenza è utile solo per piccole quantità di dati.  
  
## <a name="symmetric-encryption"></a>Crittografia simmetrica  
 Le classi di crittografia simmetrica gestite vengono usate con una classe di flusso speciale chiamata <xref:System.Security.Cryptography.CryptoStream> , che crittografa i dati letti nel flusso. La classe **CryptoStream** viene inizializzata con una classe di flusso gestita, una classe che implementa l'interfaccia <xref:System.Security.Cryptography.ICryptoTransform> (creata da una classe che implementa un algoritmo di crittografia) e un'enumerazione <xref:System.Security.Cryptography.CryptoStreamMode> che descrive il tipo di accesso consentito alla classe **CryptoStream**. La classe **CryptoStream** può essere inizializzata usando qualsiasi classe derivata dalla classe <xref:System.IO.Stream> , tra cui <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream>e <xref:System.Net.Sockets.NetworkStream>. Usando queste classi, è possibile eseguire crittografia simmetrica su svariati oggetti flusso.  
  
 L'esempio seguente mostra come creare una nuova istanza della classe <xref:System.Security.Cryptography.RijndaelManaged> , che implementa l'algoritmo di crittografia Rijndael, e usarla per eseguire la crittografia su una classe **CryptoStream** . In questo esempio la classe **CryptoStream** viene inizializzata con un oggetto flusso chiamato `myStream` , che può essere qualsiasi tipo di flusso gestito. Al metodo **CreateDecryptor** della classe **RijndaelManaged** vengono passati la chiave e il vettore di inizializzazione usati per la crittografia. In questo caso, vengono usati la chiave e il vettore di inizializzazione predefiniti generati da `rmCrypto` . Infine, viene passato **CryptoStreamMode.Write** , che specifica l'accesso in scrittura al flusso.  
  
```vb  
Dim rmCrypto As New RijndaelManaged()  
Dim cryptStream As New CryptoStream(myStream, rmCrypto.CreateEncryptor(rmCrypto.Key, rmCrypto.IV), CryptoStreamMode.Write)  
```  
  
```csharp  
RijndaelManaged rmCrypto = new RijndaelManaged();  
CryptoStream cryptStream = new CryptoStream(myStream, rmCrypto.CreateEncryptor(), CryptoStreamMode.Write);  
```  
  
 Una volta eseguito questo codice, tutti i dati scritti nell'oggetto **CryptoStream** vengono crittografati usando l'algoritmo Rijndael.  
  
 L'esempio seguente illustra l'intero processo di creazione di un flusso, decrittografia del flusso, scrittura nel flusso e chiusura del flusso. Questo esempio crea un flusso di rete che viene crittografato con le classi **CryptoStream** e **RijndaelManaged** . Viene scritto un messaggio al flusso crittografato con la classe <xref:System.IO.StreamWriter> .  
  
> [!NOTE]
> È possibile usare questo esempio anche per scrivere in un file. A questo scopo, eliminare il riferimento <xref:System.Net.Sockets.TcpClient> e sostituire <xref:System.Net.Sockets.NetworkStream> con <xref:System.IO.FileStream>.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Security.Cryptography  
Imports System.Net.Sockets  
  
Module Module1  
Sub Main()  
   Try  
      'Create a TCP connection to a listening TCP process.  
      'Use "localhost" to specify the current computer or  
      'replace "localhost" with the IP address of the   
      'listening process.   
      Dim tcp As New TcpClient("localhost", 11000)  
  
      'Create a network stream from the TCP connection.   
      Dim netStream As NetworkStream = tcp.GetStream()  
  
      'Create a new instance of the RijndaelManaged class  
      'and encrypt the stream.  
      Dim rmCrypto As New RijndaelManaged()  
  
            Dim key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
            Dim iv As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
  
      'Create a CryptoStream, pass it the NetworkStream, and encrypt   
      'it with the Rijndael class.  
      Dim cryptStream As New CryptoStream(netStream, rmCrypto.CreateEncryptor(key, iv), CryptoStreamMode.Write)  
  
      'Create a StreamWriter for easy writing to the   
      'network stream.  
      Dim sWriter As New StreamWriter(cryptStream)  
  
      'Write to the stream.  
      sWriter.WriteLine("Hello World!")  
  
      'Inform the user that the message was written  
      'to the stream.  
      Console.WriteLine("The message was sent.")  
  
      'Close all the connections.  
      sWriter.Close()  
      cryptStream.Close()  
      netStream.Close()  
      tcp.Close()  
   Catch  
      'Inform the user that an exception was raised.  
      Console.WriteLine("The connection failed.")  
   End Try  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Security.Cryptography;  
using System.Net.Sockets;  
  
public class main  
{  
   public static void Main(string[] args)  
   {  
      try  
      {  
         //Create a TCP connection to a listening TCP process.  
         //Use "localhost" to specify the current computer or  
         //replace "localhost" with the IP address of the   
         //listening process.    
         TcpClient tcp = new TcpClient("localhost",11000);  
  
         //Create a network stream from the TCP connection.   
         NetworkStream netStream = tcp.GetStream();  
  
         //Create a new instance of the RijndaelManaged class  
         // and encrypt the stream.  
         RijndaelManaged rmCrypto = new RijndaelManaged();  
  
         byte[] key = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
         byte[] iv = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
  
         //Create a CryptoStream, pass it the NetworkStream, and encrypt   
         //it with the Rijndael class.  
         CryptoStream cryptStream = new CryptoStream(netStream,   
         rmCrypto.CreateEncryptor(key, iv),     
         CryptoStreamMode.Write);  
  
         //Create a StreamWriter for easy writing to the   
         //network stream.  
         StreamWriter sWriter = new StreamWriter(cryptStream);  
  
         //Write to the stream.  
         sWriter.WriteLine("Hello World!");  
  
         //Inform the user that the message was written  
         //to the stream.  
         Console.WriteLine("The message was sent.");  
  
         //Close all the connections.  
         sWriter.Close();  
         cryptStream.Close();  
         netStream.Close();  
         tcp.Close();  
      }  
      catch  
      {  
         //Inform the user that an exception was raised.  
         Console.WriteLine("The connection failed.");  
      }  
   }  
}  
```  
  
 Per la corretta esecuzione dell'esempio precedente, deve essere presente un processo in ascolto sull'indirizzo IP e il numero di porta specificati nella classe <xref:System.Net.Sockets.TcpClient> . Se esiste un processo di ascolto, il codice si connetterà al processo, crittograferà il flusso usando l'algoritmo simmetrico Rijndael e scriverà "Hello World!" nel flusso. Se il codice è corretto, visualizza il testo seguente nella console:  
  
```console  
The message was sent.  
```  
  
 Tuttavia, se non viene trovato alcun processo di ascolto o viene generata un'eccezione, il codice visualizza il testo seguente nella console:  
  
```console  
The connection failed.  
```  
  
## <a name="asymmetric-encryption"></a>Crittografia asimmetrica  
 Gli algoritmi asimmetrici vengono in genere usati per crittografare piccole quantità di dati, ad esempio per la crittografia di una chiave simmetrica e un vettore di inizializzazione. In genere, un utente che esegue la crittografia asimmetrica usa la chiave pubblica generata da un'altra parte. La classe <xref:System.Security.Cryptography.RSACryptoServiceProvider> viene fornita da .NET Framework a questo scopo.  
  
 L'esempio seguente usa le informazioni della chiave pubblica per crittografare una chiave simmetrica e un vettore di inizializzazione. Vengono inizializzate due matrici di byte che rappresentano la chiave pubblica di una terza parte. Viene inizializzato un oggetto <xref:System.Security.Cryptography.RSAParameters> su questi valori. Quindi, l'oggetto **RSAParameters** (insieme alla chiave pubblica che rappresenta) viene importato in un oggetto **RSACryptoServiceProvider** usando il metodo <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A?displayProperty=nameWithType> . Vengono infine crittografati la chiave privata e il vettore di inizializzazione creati da una classe <xref:System.Security.Cryptography.RijndaelManaged> . Per questo esempio, è necessario che nei sistemi siano installati strumenti di crittografia a 128 bit.  
  
```vb  
Imports System  
Imports System.Security.Cryptography  
  
Module Module1  
  
    Sub Main()  
        'Initialize the byte arrays to the public key information.  
      Dim publicKey As Byte() =  {214, 46, 220, 83, 160, 73, 40, 39, 201, 155, 19,202, 3, 11, 191, 178, 56, 74, 90, 36, 248, 103, 18, 144, 170, 163, 145, 87, 54, 61, 34, 220, 222, 207, 137, 149, 173, 14, 92, 120, 206, 222, 158, 28, 40, 24, 30, 16, 175, 108, 128, 35, 230, 118, 40, 121, 113, 125, 216, 130, 11, 24, 90, 48, 194, 240, 105, 44, 76, 34, 57, 249, 228, 125, 80, 38, 9, 136, 29, 117, 207, 139, 168, 181, 85, 137, 126, 10, 126, 242, 120, 247, 121, 8, 100, 12, 201, 171, 38, 226, 193, 180, 190, 117, 177, 87, 143, 242, 213, 11, 44, 180, 113, 93, 106, 99, 179, 68, 175, 211, 164, 116, 64, 148, 226, 254, 172, 147}  
  
        Dim exponent As Byte() = {1, 0, 1}  
  
        'Create values to store encrypted symmetric keys.  
        Dim encryptedSymmetricKey() As Byte  
        Dim encryptedSymmetricIV() As Byte  
  
        'Create a new instance of the RSACryptoServiceProvider class.  
        Dim rsa As New RSACryptoServiceProvider()  
  
        'Create a new instance of the RSAParameters structure.  
        Dim rsaKeyInfo As New RSAParameters()  
  
        'Set rsaKeyInfo to the public key values.   
        rsaKeyInfo.Modulus = publicKey  
        rsaKeyInfo.Exponent = exponent  
  
        'Import key parameters into rsa.  
        rsa.ImportParameters(rsaKeyInfo)  
  
        'Create a new instance of the RijndaelManaged class.  
        Dim RM As New RijndaelManaged()  
  
        'Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(RM.Key, False)  
        encryptedSymmetricIV = rsa.Encrypt(RM.IV, False)  
    End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using System.Security.Cryptography;  
  
class Class1  
{  
   static void Main()  
   {  
      //Initialize the byte arrays to the public key information.  
      byte[] publicKey = {214,46,220,83,160,73,40,39,201,155,19,202,3,11,191,178,56,  
            74,90,36,248,103,18,144,170,163,145,87,54,61,34,220,222,  
            207,137,149,173,14,92,120,206,222,158,28,40,24,30,16,175,  
            108,128,35,230,118,40,121,113,125,216,130,11,24,90,48,194,  
            240,105,44,76,34,57,249,228,125,80,38,9,136,29,117,207,139,  
            168,181,85,137,126,10,126,242,120,247,121,8,100,12,201,171,  
            38,226,193,180,190,117,177,87,143,242,213,11,44,180,113,93,  
            106,99,179,68,175,211,164,116,64,148,226,254,172,147};  
  
      byte[] exponent = {1,0,1};  
  
      //Create values to store encrypted symmetric keys.  
      byte[] encryptedSymmetricKey;  
      byte[] encryptedSymmetricIV;  
  
      //Create a new instance of the RSACryptoServiceProvider class.  
      RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();  
  
      //Create a new instance of the RSAParameters structure.  
      RSAParameters rsaKeyInfo = new RSAParameters();  
  
      //Set rsaKeyInfo to the public key values.   
      rsaKeyInfo.Modulus = publicKey;  
      rsaKeyInfo.Exponent = exponent;  
  
      //Import key parameters into RSA.  
      rsa.ImportParameters(rsaKeyInfo);  
  
      //Create a new instance of the RijndaelManaged class.  
      RijndaelManaged rm = new RijndaelManaged();  
  
      //Encrypt the symmetric key and IV.  
      encryptedSymmetricKey = rsa.Encrypt(rm.Key, false);  
      encryptedSymmetricIV = rsa.Encrypt(rm.IV, false);  
   }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Generazione di chiavi per crittografia e decrittografia](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)
- [Decrittografia di dati](../../../docs/standard/security/decrypting-data.md)
- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)

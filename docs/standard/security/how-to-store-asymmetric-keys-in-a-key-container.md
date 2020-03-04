---
title: 'Procedura: archiviare chiavi asimmetriche in un contenitore di chiavi'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET Framework], asymmetric keys
- storing asymmetric keys
- keys, asymmetric
- encryption keys
- keys, storing in key containers
- asymmetric keys [.NET Framework]
- encryption [.NET Framework], asymmetric keys
- decryption keys
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
ms.openlocfilehash: 6b703156b38f52513c86f7b2507ac6c185a9dd50
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155945"
---
# <a name="how-to-store-asymmetric-keys-in-a-key-container"></a>Procedura: archiviare chiavi asimmetriche in un contenitore di chiavi
Le chiavi private asimmetriche non devono essere mai archiviate in modalità verbatim o in testo normale nel computer locale. Se è necessario archiviare una chiave privata, è opportuno usare un contenitore di chiavi. Per altre informazioni sui contenitori di chiavi, vedere[Informazioni sui contenitori di chiavi RSA a livello di computer e utente](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).  
  
### <a name="to-create-an-asymmetric-key-and-save-it-in-a-key-container"></a>Per creare una chiave asimmetrica e salvarla in un contenitore di chiavi  
  
1. Creare una nuova istanza di una classe <xref:System.Security.Cryptography.CspParameters> e passare il nome a cui si desidera chiamare il contenitore di chiavi nel campo <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType>.  
  
2. Creare una nuova istanza di una classe che deriva dalla classe <xref:System.Security.Cryptography.AsymmetricAlgorithm> (in genere **RSACryptoServiceProvider** o **DSACryptoServiceProvider**) e passare l'oggetto **CspParameters** creato in precedenza al relativo costruttore.  
  
### <a name="to-delete-the-key-from-a-key-container"></a>Per eliminare la chiave da un contenitore di chiavi  
  
1. Creare una nuova istanza di una classe **CspParameters** e passare il nome da usare per il contenitore di chiavi al campo **CspParameters.KeyContainerName**.  
  
2. Creare una nuova istanza di una classe derivata dalla classe **AsymmetricAlgorithm** (in genere **RSACryptoServiceProvider** o **DSACryptoServiceProvider**), quindi passare l'oggetto **CspParameters** creato in precedenza al rispettivo costruttore.  
  
3. Impostare la proprietà **PersistKeyInCSP** della classe derivata da **AsymmetricAlgorithm** su **false** (**False** in Visual Basic).  
  
4. Chiamare il metodo **Clear** della classe derivata da **AsymmetricAlgorithm**. Questo metodo rilascia tutte le risorse della classe e cancella il contenitore di chiavi.  
  
## <a name="example"></a>Esempio  
 Il seguente esempio illustra come creare una chiave asimmetrica, salvarla in un contenitore di chiavi, recuperare la chiave in un secondo momento ed eliminarla dal contenitore.  
  
 Si noti che il codice del metodo `GenKey_SaveInContainer` è simile a quello del metodo `GetKeyFromContainer`.  Quando si specifica un nome di contenitore di chiavi per un oggetto <xref:System.Security.Cryptography.CspParameters> e lo si passa a un oggetto <xref:System.Security.Cryptography.AsymmetricAlgorithm> con la proprietà <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> o la proprietà <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> impostata su true, si verifica quanto segue.  Se un contenitore di chiavi con il nome specificato non esiste, ne sarà creato uno e la chiave sarà resa persistente.  Se esiste un contenitore di chiavi con il nome specificato, la chiave nel contenitore sarà caricata automaticamente nell'oggetto <xref:System.Security.Cryptography.AsymmetricAlgorithm> corrente.  Il codice nel metodo `GenKey_SaveInContainer` rende quindi permanente la chiave poiché è eseguito per primo, mentre il codice nel metodo `GetKeyFromContainer` carica la chiave poiché è eseguito per secondo.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Security.Cryptography  
 _  
  
Public Class StoreKey  
  
    Public Shared Sub Main()  
        Try  
            ' Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer")  
  
            ' Retrieve the key from the container.  
            GetKeyFromContainer("MyKeyContainer")  
  
            ' Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer")  
  
            ' Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer")  
  
            ' Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer")  
        Catch e As CryptographicException  
            Console.WriteLine(e.Message)  
        End Try  
    End Sub  
  
    Public Shared Sub GenKey_SaveInContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container
        ' name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container MyKeyContainerName.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Display the key information to the console.  
        Console.WriteLine("Key added to container:  {0}", rsa.ToXmlString(True))  
    End Sub  
  
    Public Shared Sub GetKeyFromContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container MyKeyContainerName.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Display the key information to the console.  
        Console.WriteLine("Key retrieved from container : {0}", rsa.ToXmlString(True))  
    End Sub  
  
    Public Shared Sub DeleteKeyFromContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Delete the key entry in the container.  
        rsa.PersistKeyInCsp = False  
  
        ' Call Clear to release resources and delete the key from the container.  
        rsa.Clear()  
  
        Console.WriteLine("Key deleted.")  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Security.Cryptography;  
  
public class StoreKey  
  
{  
    public static void Main()  
    {  
        try  
        {  
            // Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer");  
  
            // Retrieve the key from the container.  
            GetKeyFromContainer("MyKeyContainer");  
  
            // Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer");  
  
            // Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer");  
  
            // Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer");  
        }  
        catch(CryptographicException e)  
        {  
            Console.WriteLine(e.Message);  
        }  
  
    }  
  
    public static void GenKey_SaveInContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container MyKeyContainerName.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Display the key information to the console.  
        Console.WriteLine("Key added to container: \n  {0}", rsa.ToXmlString(true));  
    }  
  
    public static void GetKeyFromContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container MyKeyContainerName.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Display the key information to the console.  
        Console.WriteLine("Key retrieved from container : \n {0}", rsa.ToXmlString(true));  
    }  
  
    public static void DeleteKeyFromContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Delete the key entry in the container.  
        rsa.PersistKeyInCsp = false;  
  
        // Call Clear to release resources and delete the key from the container.  
        rsa.Clear();  
  
        Console.WriteLine("Key deleted.");  
    }  
}  
```  
  
```console  
Key added to container:  
<RSAKeyValue> Key Information A</RSAKeyValue>  
Key retrieved from container :  
<RSAKeyValue> Key Information A</RSAKeyValue>  
Key deleted.  
Key added to container:  
<RSAKeyValue> Key Information B</RSAKeyValue>  
Key deleted.  
```  
  
## <a name="see-also"></a>Vedere anche

- [Generazione di chiavi per crittografia e decrittografia](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)
- [Crittografia di dati](../../../docs/standard/security/encrypting-data.md)
- [Decrittografia di dati](../../../docs/standard/security/decrypting-data.md)
- [Servizi di crittografia](../../../docs/standard/security/cryptographic-services.md)

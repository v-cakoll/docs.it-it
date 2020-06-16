---
title: 'Procedura: archiviare chiavi asimmetriche in un contenitore di chiavi'
description: Informazioni su come archiviare chiavi asimmetriche in un contenitore di chiavi in .NET. Vedere come creare una chiave asimmetrica, salvarla in un contenitore di chiavi e recuperare ed eliminare la chiave.
ms.date: 05/26/2020
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
ms.openlocfilehash: a0fbde37491043cc1aab71e9733087bf410b997d
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769029"
---
# <a name="store-asymmetric-keys-in-a-key-container"></a>Archiviare chiavi asimmetriche in un contenitore di chiavi

Le chiavi private asimmetriche non devono essere mai archiviate in modalità verbatim o in testo normale nel computer locale. Se è necessario archiviare una chiave privata, usare un contenitore di chiavi. Per altre informazioni sui contenitori di chiavi, vedere [informazioni sui contenitori di chiavi RSA a livello di computer e](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100))a livello di utente.

## <a name="create-an-asymmetric-key-and-save-it-in-a-key-container"></a>Creare una chiave asimmetrica e salvarla in un contenitore di chiavi

1. Creare una nuova istanza di una <xref:System.Security.Cryptography.CspParameters> classe e passare il nome che si desidera chiamare al campo dal contenitore di chiavi <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> .

1. Creare una nuova istanza di una classe che deriva dalla <xref:System.Security.Cryptography.AsymmetricAlgorithm> classe ( <xref:System.Security.Cryptography.RSACryptoServiceProvider> in genere o <xref:System.Security.Cryptography.DSACryptoServiceProvider> ) e passare l'oggetto creato in precedenza `CspParameters` al relativo costruttore.

> [!NOTE]
> La creazione e il recupero di una chiave asimmetrica sono un'operazione. Se una chiave non è già presente nel contenitore, viene creata prima di essere restituita.
>
> - <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType>
> - <xref:System.Security.Cryptography.DSA.ToXmlString%2A?displayProperty=nameWithType>

## <a name="delete-the-key-from-the-key-container"></a>Eliminare la chiave dal contenitore di chiavi

1. Creare una nuova istanza di una `CspParameters` classe e passare il nome che si desidera chiamare al campo dal contenitore di chiavi <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> .

1. Creare una nuova istanza di una classe che deriva dalla <xref:System.Security.Cryptography.AsymmetricAlgorithm> classe ( `RSACryptoServiceProvider` in genere o `DSACryptoServiceProvider` ) e passare l'oggetto creato in precedenza `CspParameters` al relativo costruttore.

1. Impostare la <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> proprietà o <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> della classe che deriva da `AsymmetricAlgorithm` a `false` ( `False` in Visual Basic).

1. Chiamare il `Clear` metodo della classe che deriva da `AsymmetricAlgorithm` . Questo metodo rilascia tutte le risorse della classe e cancella il contenitore di chiavi.

## <a name="example"></a>Esempio

Il seguente esempio illustra come creare una chiave asimmetrica, salvarla in un contenitore di chiavi, recuperare la chiave in un secondo momento ed eliminarla dal contenitore.

Si noti che il codice del metodo `GenKey_SaveInContainer` è simile a quello del metodo `GetKeyFromContainer`. Quando si specifica un nome del contenitore di chiavi per un <xref:System.Security.Cryptography.CspParameters> oggetto e lo si passa a un <xref:System.Security.Cryptography.AsymmetricAlgorithm> oggetto con la <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> proprietà o la <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> proprietà impostata su `true` , il comportamento è il seguente:

- Se un contenitore di chiavi con il nome specificato non esiste, ne sarà creato uno e la chiave sarà resa persistente.
- Se esiste un contenitore di chiavi con il nome specificato, la chiave nel contenitore sarà caricata automaticamente nell'oggetto <xref:System.Security.Cryptography.AsymmetricAlgorithm> corrente.

Pertanto, il codice nel `GenKey_SaveInContainer` metodo rende permanente la chiave perché viene eseguita per prima, mentre il codice nel `GetKeyFromContainer` metodo carica la chiave perché viene eseguita secondo.

```vb
Imports System
Imports System.Security.Cryptography

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

    Private Shared Sub GenKey_SaveInContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        ' name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container MyKeyContainerName.
        Using rsa As New RSACryptoServiceProvider(parameters)
            ' Display the key information to the console.
            Console.WriteLine($"Key added to container:  {rsa.ToXmlString(True)}")
        End Using
    End Sub

    Private Shared Sub GetKeyFromContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container MyKeyContainerName.
        Using rsa As New RSACryptoServiceProvider(parameters)
            ' Display the key information to the console.
            Console.WriteLine($"Key retrieved from container : {rsa.ToXmlString(True)}")
        End Using
    End Sub

    Private Shared Sub DeleteKeyFromContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container.
        ' Delete the key entry in the container.
        Dim rsa As New RSACryptoServiceProvider(parameters) With {
            .PersistKeyInCsp = False
        }

        ' Call Clear to release resources and delete the key from the container.
        rsa.Clear()

        Console.WriteLine("Key deleted.")
    End Sub
End Class
```

```csharp
using System;
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
        catch (CryptographicException e)
        {
            Console.WriteLine(e.Message);
        }
    }

    private static void GenKey_SaveInContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container MyKeyContainerName.
        using var rsa = new RSACryptoServiceProvider(parameters);

        // Display the key information to the console.
        Console.WriteLine($"Key added to container: \n  {rsa.ToXmlString(true)}");
    }

    private static void GetKeyFromContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container MyKeyContainerName.
        using var rsa = new RSACryptoServiceProvider(parameters);

        // Display the key information to the console.
        Console.WriteLine($"Key retrieved from container : \n {rsa.ToXmlString(true)}");
    }

    private static void DeleteKeyFromContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container.
        using var rsa = new RSACryptoServiceProvider(parameters)
        {
            // Delete the key entry in the container.
            PersistKeyInCsp = false
        };

        // Call Clear to release resources and delete the key from the container.
        rsa.Clear();

        Console.WriteLine("Key deleted.");
    }
}
```

L'output è il seguente:

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

- [Generazione di chiavi per la crittografia e la decrittografia](generating-keys-for-encryption-and-decryption.md)
- [Crittografia dei dati](encrypting-data.md)
- [Decrittografia di dati](decrypting-data.md)
- [Servizi di crittografia](cryptographic-services.md)

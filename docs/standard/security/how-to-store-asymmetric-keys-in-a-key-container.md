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
# <a name="store-asymmetric-keys-in-a-key-container"></a><span data-ttu-id="7cf06-104">Archiviare chiavi asimmetriche in un contenitore di chiavi</span><span class="sxs-lookup"><span data-stu-id="7cf06-104">Store asymmetric keys in a key container</span></span>

<span data-ttu-id="7cf06-105">Le chiavi private asimmetriche non devono essere mai archiviate in modalità verbatim o in testo normale nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="7cf06-105">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="7cf06-106">Se è necessario archiviare una chiave privata, usare un contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="7cf06-106">If you need to store a private key, use a key container.</span></span> <span data-ttu-id="7cf06-107">Per altre informazioni sui contenitori di chiavi, vedere [informazioni sui contenitori di chiavi RSA a livello di computer e](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100))a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="7cf06-107">For more information on key containers, see [Understanding machine-level and user-level RSA key containers](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span></span>

## <a name="create-an-asymmetric-key-and-save-it-in-a-key-container"></a><span data-ttu-id="7cf06-108">Creare una chiave asimmetrica e salvarla in un contenitore di chiavi</span><span class="sxs-lookup"><span data-stu-id="7cf06-108">Create an asymmetric key and save it in a key container</span></span>

1. <span data-ttu-id="7cf06-109">Creare una nuova istanza di una <xref:System.Security.Cryptography.CspParameters> classe e passare il nome che si desidera chiamare al campo dal contenitore di chiavi <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="7cf06-109">Create a new instance of a <xref:System.Security.Cryptography.CspParameters> class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="7cf06-110">Creare una nuova istanza di una classe che deriva dalla <xref:System.Security.Cryptography.AsymmetricAlgorithm> classe ( <xref:System.Security.Cryptography.RSACryptoServiceProvider> in genere o <xref:System.Security.Cryptography.DSACryptoServiceProvider> ) e passare l'oggetto creato in precedenza `CspParameters` al relativo costruttore.</span><span class="sxs-lookup"><span data-stu-id="7cf06-110">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually <xref:System.Security.Cryptography.RSACryptoServiceProvider> or <xref:System.Security.Cryptography.DSACryptoServiceProvider>) and pass the previously created `CspParameters` object to its constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="7cf06-111">La creazione e il recupero di una chiave asimmetrica sono un'operazione.</span><span class="sxs-lookup"><span data-stu-id="7cf06-111">The creation and retrieval of an asymmetric key is one operation.</span></span> <span data-ttu-id="7cf06-112">Se una chiave non è già presente nel contenitore, viene creata prima di essere restituita.</span><span class="sxs-lookup"><span data-stu-id="7cf06-112">If a key is not already in the container, it's created before being returned.</span></span>
>
> - <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType>
> - <xref:System.Security.Cryptography.DSA.ToXmlString%2A?displayProperty=nameWithType>

## <a name="delete-the-key-from-the-key-container"></a><span data-ttu-id="7cf06-113">Eliminare la chiave dal contenitore di chiavi</span><span class="sxs-lookup"><span data-stu-id="7cf06-113">Delete the key from the key container</span></span>

1. <span data-ttu-id="7cf06-114">Creare una nuova istanza di una `CspParameters` classe e passare il nome che si desidera chiamare al campo dal contenitore di chiavi <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="7cf06-114">Create a new instance of a `CspParameters` class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="7cf06-115">Creare una nuova istanza di una classe che deriva dalla <xref:System.Security.Cryptography.AsymmetricAlgorithm> classe ( `RSACryptoServiceProvider` in genere o `DSACryptoServiceProvider` ) e passare l'oggetto creato in precedenza `CspParameters` al relativo costruttore.</span><span class="sxs-lookup"><span data-stu-id="7cf06-115">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually `RSACryptoServiceProvider` or `DSACryptoServiceProvider`) and pass the previously created `CspParameters` object to its constructor.</span></span>

1. <span data-ttu-id="7cf06-116">Impostare la <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> proprietà o <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> della classe che deriva da `AsymmetricAlgorithm` a `false` ( `False` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="7cf06-116">Set the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> or the <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> property of the class that derives from `AsymmetricAlgorithm` to `false` (`False` in Visual Basic).</span></span>

1. <span data-ttu-id="7cf06-117">Chiamare il `Clear` metodo della classe che deriva da `AsymmetricAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="7cf06-117">Call the `Clear` method of the class that derives from `AsymmetricAlgorithm`.</span></span> <span data-ttu-id="7cf06-118">Questo metodo rilascia tutte le risorse della classe e cancella il contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="7cf06-118">This method releases all resources of the class and clears the key container.</span></span>

## <a name="example"></a><span data-ttu-id="7cf06-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="7cf06-119">Example</span></span>

<span data-ttu-id="7cf06-120">Il seguente esempio illustra come creare una chiave asimmetrica, salvarla in un contenitore di chiavi, recuperare la chiave in un secondo momento ed eliminarla dal contenitore.</span><span class="sxs-lookup"><span data-stu-id="7cf06-120">The following example demonstrates how to create an asymmetric key, save it in a key container, retrieve the key at a later time, and delete the key from the container.</span></span>

<span data-ttu-id="7cf06-121">Si noti che il codice del metodo `GenKey_SaveInContainer` è simile a quello del metodo `GetKeyFromContainer`.</span><span class="sxs-lookup"><span data-stu-id="7cf06-121">Notice that code in the `GenKey_SaveInContainer` method and the `GetKeyFromContainer` method is similar.</span></span> <span data-ttu-id="7cf06-122">Quando si specifica un nome del contenitore di chiavi per un <xref:System.Security.Cryptography.CspParameters> oggetto e lo si passa a un <xref:System.Security.Cryptography.AsymmetricAlgorithm> oggetto con la <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> proprietà o la <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> proprietà impostata su `true` , il comportamento è il seguente:</span><span class="sxs-lookup"><span data-stu-id="7cf06-122">When you specify a key container name for a <xref:System.Security.Cryptography.CspParameters> object and pass it to an <xref:System.Security.Cryptography.AsymmetricAlgorithm> object with the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> property or <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> property set to `true`, the behavior is as follows:</span></span>

- <span data-ttu-id="7cf06-123">Se un contenitore di chiavi con il nome specificato non esiste, ne sarà creato uno e la chiave sarà resa persistente.</span><span class="sxs-lookup"><span data-stu-id="7cf06-123">If a key container with the specified name does not exist, then one is created and the key is persisted.</span></span>
- <span data-ttu-id="7cf06-124">Se esiste un contenitore di chiavi con il nome specificato, la chiave nel contenitore sarà caricata automaticamente nell'oggetto <xref:System.Security.Cryptography.AsymmetricAlgorithm> corrente.</span><span class="sxs-lookup"><span data-stu-id="7cf06-124">If a key container with the specified name does exist, then the key in the container is automatically loaded into the current <xref:System.Security.Cryptography.AsymmetricAlgorithm> object.</span></span>

<span data-ttu-id="7cf06-125">Pertanto, il codice nel `GenKey_SaveInContainer` metodo rende permanente la chiave perché viene eseguita per prima, mentre il codice nel `GetKeyFromContainer` metodo carica la chiave perché viene eseguita secondo.</span><span class="sxs-lookup"><span data-stu-id="7cf06-125">Therefore, the code in the `GenKey_SaveInContainer` method persists the key because it is run first, while the code in the `GetKeyFromContainer` method loads the key because it's run second.</span></span>

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

<span data-ttu-id="7cf06-126">L'output è il seguente:</span><span class="sxs-lookup"><span data-stu-id="7cf06-126">The output is as follows:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7cf06-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cf06-127">See also</span></span>

- [<span data-ttu-id="7cf06-128">Generazione di chiavi per la crittografia e la decrittografia</span><span class="sxs-lookup"><span data-stu-id="7cf06-128">Generating keys for encryption and decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="7cf06-129">Crittografia dei dati</span><span class="sxs-lookup"><span data-stu-id="7cf06-129">Encrypting data</span></span>](encrypting-data.md)
- [<span data-ttu-id="7cf06-130">Decrittografia di dati</span><span class="sxs-lookup"><span data-stu-id="7cf06-130">Decrypting data</span></span>](decrypting-data.md)
- [<span data-ttu-id="7cf06-131">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="7cf06-131">Cryptographic services</span></span>](cryptographic-services.md)

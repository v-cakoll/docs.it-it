---
title: Firme di crittografia
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- digital signatures
- cryptography [.NET Framework], signatures
- digital signatures, XML signing
- signatures, cryptographic
- digital signatures, generating
- verifying signatures
- generating signatures
- digital signatures, about
- encryption [.NET Framework], signatures
- security [.NET Framework], signatures
- XML signing
- digital signatures, verifying
- signing XML
ms.assetid: aa87cb7f-e608-4a81-948b-c9b8a1225783
ms.openlocfilehash: 1de6b3f2eb30df270339910e7b8287101bde65ca
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706253"
---
# <a name="cryptographic-signatures"></a><span data-ttu-id="ebf0f-102">Firme di crittografia</span><span class="sxs-lookup"><span data-stu-id="ebf0f-102">Cryptographic Signatures</span></span>

<span data-ttu-id="ebf0f-103">Le firme digitali di crittografia usano algoritmi con chiave pubblica per garantire l'integrità dei dati.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-103">Cryptographic digital signatures use public key algorithms to provide data integrity.</span></span> <span data-ttu-id="ebf0f-104">Quando viene applicata una firma digitale ai dati, questa può essere verificata da altri e può quindi provare che i dati non sono stati modificati dopo l'applicazione della firma.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-104">When you sign data with a digital signature, someone else can verify the signature, and can prove that the data originated from you and was not altered after you signed it.</span></span> <span data-ttu-id="ebf0f-105">Per altre informazioni sulle firme digitali, vedere [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="ebf0f-105">For more information about digital signatures, see [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span></span>

<span data-ttu-id="ebf0f-106">Questo argomento spiega come generare e verificare firme digitali usando le classi nello <xref:System.Security.Cryptography?displayProperty=nameWithType> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-106">This topic explains how to generate and verify digital signatures using classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>

## <a name="generating-signatures"></a><span data-ttu-id="ebf0f-107">Generazione di firme</span><span class="sxs-lookup"><span data-stu-id="ebf0f-107">Generating Signatures</span></span>

<span data-ttu-id="ebf0f-108">Le firme digitali vengono generalmente applicate a valori hash che rappresentano dati di maggiori dimensioni.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-108">Digital signatures are usually applied to hash values that represent larger data.</span></span> <span data-ttu-id="ebf0f-109">Nell'esempio che segue viene applicata una firma digitale a un valore hash.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-109">The following example applies a digital signature to a hash value.</span></span> <span data-ttu-id="ebf0f-110">Viene creata prima di tutto una nuova istanza della classe <xref:System.Security.Cryptography.RSACryptoServiceProvider> per generare una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-110">First, a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class is created to generate a public/private key pair.</span></span> <span data-ttu-id="ebf0f-111">Viene quindi passato <xref:System.Security.Cryptography.RSACryptoServiceProvider> a una nuova istanza della classe <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> .</span><span class="sxs-lookup"><span data-stu-id="ebf0f-111">Next, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> is passed to a new instance of the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class.</span></span> <span data-ttu-id="ebf0f-112">In questo modo la chiave privata viene trasferita a <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>che esegue l'effettiva apposizione della firma digitale.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-112">This transfers the private key to the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>, which actually performs the digital signing.</span></span> <span data-ttu-id="ebf0f-113">Prima di firmare il codice hash, è necessario specificare un algoritmo hash da usare.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-113">Before you can sign the hash code, you must specify a hash algorithm to use.</span></span> <span data-ttu-id="ebf0f-114">Questo esempio usa l'algoritmo SHA1.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-114">This example uses the SHA1 algorithm.</span></span> <span data-ttu-id="ebf0f-115">Infine viene chiamato il metodo <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> per apporre la firma.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-115">Finally, the <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> method is called to perform the signing.</span></span>

<span data-ttu-id="ebf0f-116">A causa di problemi di collisione con SHA1, Microsoft consiglia di SHA256 o meglio.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-116">Due to collision problems with SHA1, Microsoft recommends SHA256 or better.</span></span>

```vb
Imports System.Security.Cryptography

Module Module1
    Sub Main()
        'The hash value to sign.
        Dim hashValue As Byte() = {59, 4, 248, 102, 77, 97, 142, 201, 210, 12, 224, 93, 25, 41, 100, 197, 213, 134, 130, 135}

        'The value to hold the signed value.
        Dim signedHashValue() As Byte

        'Generate a public/private key pair.
        Dim rsa As New RSACryptoServiceProvider()

        'Create an RSAPKCS1SignatureFormatter object and pass it
        'the RSACryptoServiceProvider to transfer the private key.
        Dim rsaFormatter As New RSAPKCS1SignatureFormatter(rsa)

        'Set the hash algorithm to SHA1.
        rsaFormatter.SetHashAlgorithm("SHA1")

        'Create a signature for hashValue and assign it to
        'signedHashValue.
        signedHashValue = rsaFormatter.CreateSignature(hashValue)
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
      //The hash value to sign.
      byte[] hashValue = {59,4,248,102,77,97,142,201,210,12,224,93,25,41,100,197,213,134,130,135};

      //The value to hold the signed value.
      byte[] signedHashValue;

      //Generate a public/private key pair.
      RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();

      //Create an RSAPKCS1SignatureFormatter object and pass it the
      //RSACryptoServiceProvider to transfer the private key.
      RSAPKCS1SignatureFormatter rsaFormatter = new RSAPKCS1SignatureFormatter(rsa);

      //Set the hash algorithm to SHA1.
      rsaFormatter.SetHashAlgorithm("SHA1");

      //Create a signature for hashValue and assign it to
      //signedHashValue.
      signedHashValue = rsaFormatter.CreateSignature(hashValue);
   }
}
```

### <a name="signing-xml-files"></a><span data-ttu-id="ebf0f-117">Firma di file XML</span><span class="sxs-lookup"><span data-stu-id="ebf0f-117">Signing XML Files</span></span>

<span data-ttu-id="ebf0f-118">.NET Framework fornisce lo spazio dei nomi <xref:System.Security.Cryptography.Xml> che consente di firmare il codice XML.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-118">The .NET Framework provides the <xref:System.Security.Cryptography.Xml> namespace, which enables you sign XML.</span></span> <span data-ttu-id="ebf0f-119">La firma XML è importante quando si vuole verificare l'origine del linguaggio XML.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-119">Signing XML is important when you want to verify that the XML originates from a certain source.</span></span> <span data-ttu-id="ebf0f-120">Se si usa ad esempio un servizio di quotazione dei titoli di borsa che usa il linguaggio XML, è possibile verificarne l'origine se è presente la firma.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-120">For example, if you are using a stock quote service that uses XML, you can verify the source of the XML if it is signed.</span></span>

<span data-ttu-id="ebf0f-121">Le classi in questo spazio dei nomi sono conformi alla [raccomandazione relativa alla sintassi e all'elaborazione della firma XML](https://www.w3.org/TR/xmldsig-core/) del World Wide Web Consortium.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-121">The classes in this namespace follow the [XML-Signature Syntax and Processing recommendation](https://www.w3.org/TR/xmldsig-core/) from the World Wide Web Consortium.</span></span>

## <a name="verifying-signatures"></a><span data-ttu-id="ebf0f-122">Verifica di firme</span><span class="sxs-lookup"><span data-stu-id="ebf0f-122">Verifying Signatures</span></span>

<span data-ttu-id="ebf0f-123">Per verificare che i dati siano stati firmati da una determinata parte, è necessario avere le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ebf0f-123">To verify that data was signed by a particular party, you must have the following information:</span></span>

- <span data-ttu-id="ebf0f-124">La chiave pubblica della parte che ha firmato i dati.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-124">The public key of the party that signed the data.</span></span>

- <span data-ttu-id="ebf0f-125">La firma digitale.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-125">The digital signature.</span></span>

- <span data-ttu-id="ebf0f-126">I dati che sono stati firmati.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-126">The data that was signed.</span></span>

- <span data-ttu-id="ebf0f-127">L'algoritmo hash usato dal firmatario.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-127">The hash algorithm used by the signer.</span></span>

<span data-ttu-id="ebf0f-128">Usare la classe <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> per verificare una firma eseguita dalla classe <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> .</span><span class="sxs-lookup"><span data-stu-id="ebf0f-128">To verify a signature signed by the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class, use the <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class.</span></span> <span data-ttu-id="ebf0f-129">Alla classe <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> deve essere fornita la chiave pubblica del firmatario.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-129">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class must be supplied the public key of the signer.</span></span> <span data-ttu-id="ebf0f-130">Sarà necessario avere i valori del modulo e l'esponente per specificare la chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-130">You will need the values of the modulus and the exponent to specify the public key.</span></span> <span data-ttu-id="ebf0f-131">L'entità che ha generato la coppia di chiavi pubblica/privata deve fornire questi valori. Creare innanzitutto un oggetto <xref:System.Security.Cryptography.RSACryptoServiceProvider> per conservare la chiave pubblica che verificherà la firma, quindi inizializzare una struttura <xref:System.Security.Cryptography.RSAParameters> per i valori di modulo ed esponente che specificano la chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-131">(The party that generated the public/private key pair should provide these values.) First create an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to hold the public key that will verify the signature, and then initialize an <xref:System.Security.Cryptography.RSAParameters> structure to the modulus and exponent values that specify the public key.</span></span>

<span data-ttu-id="ebf0f-132">Il codice seguente illustra la creazione di una struttura <xref:System.Security.Cryptography.RSAParameters> .</span><span class="sxs-lookup"><span data-stu-id="ebf0f-132">The following code shows the creation of an <xref:System.Security.Cryptography.RSAParameters> structure.</span></span> <span data-ttu-id="ebf0f-133">La proprietà `Modulus` è impostata sul valore di una matrice di byte denominata `modulusData` e la proprietà `Exponent` è impostata sul valore di una matrice di byte denominata `exponentData`.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-133">The `Modulus` property is set to the value of a byte array called `modulusData` and the `Exponent` property is set to the value of a byte array called `exponentData`.</span></span>

```vb
Dim rsaKeyInfo As RSAParameters
rsaKeyInfo.Modulus = modulusData
rsaKeyInfo.Exponent = exponentData
```

```csharp
RSAParameters rsaKeyInfo;
rsaKeyInfo.Modulus = modulusData;
rsaKeyInfo.Exponent = exponentData;
```

<span data-ttu-id="ebf0f-134">Dopo avere creato l'oggetto <xref:System.Security.Cryptography.RSAParameters> , è possibile inizializzare una nuova istanza della classe <xref:System.Security.Cryptography.RSACryptoServiceProvider> per i valori specificati in <xref:System.Security.Cryptography.RSAParameters>.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-134">After you have created the <xref:System.Security.Cryptography.RSAParameters> object, you can initialize a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class to the values specified in <xref:System.Security.Cryptography.RSAParameters>.</span></span> <span data-ttu-id="ebf0f-135"><xref:System.Security.Cryptography.RSACryptoServiceProvider> viene a sua volta passato al costruttore di un oggetto <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> per trasferire la chiave.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-135">The <xref:System.Security.Cryptography.RSACryptoServiceProvider> is, in turn, passed to the constructor of an <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> to transfer the key.</span></span>

<span data-ttu-id="ebf0f-136">Nell'esempio che segue viene illustrato questo processo.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-136">The following example illustrates this process.</span></span> <span data-ttu-id="ebf0f-137">`hashValue` e `signedHashValue` sono in questo caso matrici di byte fornite da una parte remota.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-137">In this example, `hashValue` and `signedHashValue` are arrays of bytes provided by a remote party.</span></span> <span data-ttu-id="ebf0f-138">La parte remota ha firmato `hashValue` usando l'algoritmo SHA1, producendo la firma digitale `signedHashValue`.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-138">The remote party has signed the `hashValue` using the SHA1 algorithm, producing the digital signature `signedHashValue`.</span></span> <span data-ttu-id="ebf0f-139">Il metodo <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> verifica che la firma digitale sia valida e usata per firmare il `hashValue`.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-139">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> method verifies that the digital signature is valid and was used to sign the `hashValue`.</span></span>

```vb
Dim rsa As New RSACryptoServiceProvider()
rsa.ImportParameters(rsaKeyInfo)
Dim rsaDeformatter As New RSAPKCS1SignatureDeformatter(rsa)
rsaDeformatter.SetHashAlgorithm("SHA1")
If rsaDeformatter.VerifySignature(hashValue, signedHashValue) Then
   Console.WriteLine("The signature is valid.")
Else
   Console.WriteLine("The signature is not valid.")
End If
```

```csharp
RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();
rsa.ImportParameters(rsaKeyInfo);
RSAPKCS1SignatureDeformatter rsaDeformatter = new RSAPKCS1SignatureDeformatter(rsa);
rsaDeformatter.SetHashAlgorithm("SHA1");
if(rsaDeformatter.VerifySignature(hashValue, signedHashValue))
{
   Console.WriteLine("The signature is valid.");
}
else
{
   Console.WriteLine("The signature is not valid.");
}
```

<span data-ttu-id="ebf0f-140">Nel frammento di codice sarà visualizzato il messaggio "`The signature is valid`" se la firma è valida e "`The signature is not valid`" in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="ebf0f-140">This code fragment will display "`The signature is valid`" if the signature is valid and "`The signature is not valid`" if it is not.</span></span>

## <a name="see-also"></a><span data-ttu-id="ebf0f-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebf0f-141">See also</span></span>

- [<span data-ttu-id="ebf0f-142">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="ebf0f-142">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)

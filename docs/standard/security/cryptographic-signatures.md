---
title: Firme di crittografia
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c4e460c11e0e78d56a54da1dd178b3f8e9f381b6
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2018
---
# <a name="cryptographic-signatures"></a><span data-ttu-id="86563-102">Firme di crittografia</span><span class="sxs-lookup"><span data-stu-id="86563-102">Cryptographic Signatures</span></span>
<a name="top"></a> <span data-ttu-id="86563-103">Le firme digitali di crittografia usano algoritmi con chiave pubblica per garantire l'integrità dei dati.</span><span class="sxs-lookup"><span data-stu-id="86563-103">Cryptographic digital signatures use public key algorithms to provide data integrity.</span></span> <span data-ttu-id="86563-104">Quando viene applicata una firma digitale ai dati, questa può essere verificata da altri e può quindi provare che i dati non sono stati modificati dopo l'applicazione della firma.</span><span class="sxs-lookup"><span data-stu-id="86563-104">When you sign data with a digital signature, someone else can verify the signature, and can prove that the data originated from you and was not altered after you signed it.</span></span> <span data-ttu-id="86563-105">Per altre informazioni sulle firme digitali, vedere [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="86563-105">For more information about digital signatures, see [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span></span>  
  
 <span data-ttu-id="86563-106">Questo argomento spiega come generare e verificare firme digitali usando le classi nello <xref:System.Security.Cryptography?displayProperty=nameWithType>spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="86563-106">This topic explains how to generate and verify digital signatures using classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>  
  
-   [<span data-ttu-id="86563-107">Generazione di firme</span><span class="sxs-lookup"><span data-stu-id="86563-107">Generating Signatures</span></span>](#generate)  
  
-   [<span data-ttu-id="86563-108">Verifica di firme</span><span class="sxs-lookup"><span data-stu-id="86563-108">Verifying Signatures</span></span>](#verify)  
  
<a name="generate"></a>   
## <a name="generating-signatures"></a><span data-ttu-id="86563-109">Generazione di firme</span><span class="sxs-lookup"><span data-stu-id="86563-109">Generating Signatures</span></span>  
 <span data-ttu-id="86563-110">Le firme digitali vengono generalmente applicate a valori hash che rappresentano dati di maggiori dimensioni.</span><span class="sxs-lookup"><span data-stu-id="86563-110">Digital signatures are usually applied to hash values that represent larger data.</span></span> <span data-ttu-id="86563-111">Nell'esempio che segue viene applicata una firma digitale a un valore hash.</span><span class="sxs-lookup"><span data-stu-id="86563-111">The following example applies a digital signature to a hash value.</span></span> <span data-ttu-id="86563-112">Viene creata prima di tutto una nuova istanza della classe <xref:System.Security.Cryptography.RSACryptoServiceProvider> per generare una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="86563-112">First, a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class is created to generate a public/private key pair.</span></span> <span data-ttu-id="86563-113">Viene quindi passato <xref:System.Security.Cryptography.RSACryptoServiceProvider> a una nuova istanza della classe <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> .</span><span class="sxs-lookup"><span data-stu-id="86563-113">Next, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> is passed to a new instance of the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class.</span></span> <span data-ttu-id="86563-114">In questo modo la chiave privata viene trasferita a <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>che esegue l'effettiva apposizione della firma digitale.</span><span class="sxs-lookup"><span data-stu-id="86563-114">This transfers the private key to the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>, which actually performs the digital signing.</span></span> <span data-ttu-id="86563-115">Prima di firmare il codice hash, è necessario specificare un algoritmo hash da usare.</span><span class="sxs-lookup"><span data-stu-id="86563-115">Before you can sign the hash code, you must specify a hash algorithm to use.</span></span> <span data-ttu-id="86563-116">Questo esempio usa l'algoritmo SHA1.</span><span class="sxs-lookup"><span data-stu-id="86563-116">This example uses the SHA1 algorithm.</span></span> <span data-ttu-id="86563-117">Infine viene chiamato il metodo <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> per apporre la firma.</span><span class="sxs-lookup"><span data-stu-id="86563-117">Finally, the <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> method is called to perform the signing.</span></span>  
  
```vb  
Imports System  
Imports System.Security.Cryptography  
  
Module Module1  
    Sub Main()  
        'The hash value to sign.  
        Dim HashValue As Byte() = {59, 4, 248, 102, 77, 97, 142, 201, 210, 12, 224, 93, 25, 41, 100, 197, 213, 134, 130, 135}  
  
        'The value to hold the signed value.  
        Dim SignedHashValue() As Byte  
  
        'Generate a public/private key pair.  
        Dim RSA As New RSACryptoServiceProvider()  
  
        'Create an RSAPKCS1SignatureFormatter object and pass it   
        'the RSACryptoServiceProvider to transfer the private key.  
        Dim RSAFormatter As New RSAPKCS1SignatureFormatter(RSA)  
  
        'Set the hash algorithm to SHA1.  
        RSAFormatter.SetHashAlgorithm("SHA1")  
  
        'Create a signature for HashValue and assign it to   
        'SignedHashValue.  
        SignedHashValue = RSAFormatter.CreateSignature(HashValue)  
    End Sub  
End Module  
  
using System;  
using System.Security.Cryptography;  
```  
  
```csharp  
class Class1  
{  
   static void Main()  
   {  
      //The hash value to sign.  
      byte[] HashValue = {59,4,248,102,77,97,142,201,210,12,224,93,25,41,100,197,213,134,130,135};  
  
      //The value to hold the signed value.  
      byte[] SignedHashValue;  
  
      //Generate a public/private key pair.  
      RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
  
      //Create an RSAPKCS1SignatureFormatter object and pass it the   
      //RSACryptoServiceProvider to transfer the private key.  
      RSAPKCS1SignatureFormatter RSAFormatter = new RSAPKCS1SignatureFormatter(RSA);  
  
      //Set the hash algorithm to SHA1.  
      RSAFormatter.SetHashAlgorithm("SHA1");  
  
      //Create a signature for HashValue and assign it to   
      //SignedHashValue.  
      SignedHashValue = RSAFormatter.CreateSignature(HashValue);  
   }  
}  
```  
  
### <a name="signing-xml-files"></a><span data-ttu-id="86563-118">Firma di file XML</span><span class="sxs-lookup"><span data-stu-id="86563-118">Signing XML Files</span></span>  
 <span data-ttu-id="86563-119">.NET Framework fornisce lo spazio dei nomi <xref:System.Security.Cryptography.Xml> che consente di firmare il codice XML.</span><span class="sxs-lookup"><span data-stu-id="86563-119">The .NET Framework provides the <xref:System.Security.Cryptography.Xml> namespace, which enables you sign XML.</span></span> <span data-ttu-id="86563-120">La firma XML è importante quando si vuole verificare l'origine del linguaggio XML.</span><span class="sxs-lookup"><span data-stu-id="86563-120">Signing XML is important when you want to verify that the XML originates from a certain source.</span></span> <span data-ttu-id="86563-121">Se si usa ad esempio un servizio di quotazione dei titoli di borsa che usa il linguaggio XML, è possibile verificarne l'origine se è presente la firma.</span><span class="sxs-lookup"><span data-stu-id="86563-121">For example, if you are using a stock quote service that uses XML, you can verify the source of the XML if it is signed.</span></span>  
  
 <span data-ttu-id="86563-122">Le classi in questo spazio dei nomi conformi il [indicazione di elaborazione e alla sintassi XML firma](http://www.w3.org/TR/xmldsig-core/) dal World Wide Web Consortium.</span><span class="sxs-lookup"><span data-stu-id="86563-122">The classes in this namespace follow the [XML-Signature Syntax and Processing recommendation](http://www.w3.org/TR/xmldsig-core/) from the World Wide Web Consortium.</span></span>  
  
 [<span data-ttu-id="86563-123">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="86563-123">Back to top</span></span>](#top)  
  
<a name="verify"></a>   
## <a name="verifying-signatures"></a><span data-ttu-id="86563-124">Verifica di firme</span><span class="sxs-lookup"><span data-stu-id="86563-124">Verifying Signatures</span></span>  
 <span data-ttu-id="86563-125">Per verificare che i dati siano stati firmati da una determinata parte, è necessario avere le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="86563-125">To verify that data was signed by a particular party, you must have the following information:</span></span>  
  
-   <span data-ttu-id="86563-126">La chiave pubblica della parte che ha firmato i dati.</span><span class="sxs-lookup"><span data-stu-id="86563-126">The public key of the party that signed the data.</span></span>  
  
-   <span data-ttu-id="86563-127">La firma digitale.</span><span class="sxs-lookup"><span data-stu-id="86563-127">The digital signature.</span></span>  
  
-   <span data-ttu-id="86563-128">I dati che sono stati firmati.</span><span class="sxs-lookup"><span data-stu-id="86563-128">The data that was signed.</span></span>  
  
-   <span data-ttu-id="86563-129">L'algoritmo hash usato dal firmatario.</span><span class="sxs-lookup"><span data-stu-id="86563-129">The hash algorithm used by the signer.</span></span>  
  
 <span data-ttu-id="86563-130">Usare la classe <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> per verificare una firma eseguita dalla classe <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> .</span><span class="sxs-lookup"><span data-stu-id="86563-130">To verify a signature signed by the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class, use the <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class.</span></span> <span data-ttu-id="86563-131">Alla classe <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> deve essere fornita la chiave pubblica del firmatario.</span><span class="sxs-lookup"><span data-stu-id="86563-131">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class must be supplied the public key of the signer.</span></span> <span data-ttu-id="86563-132">Sarà necessario avere i valori del modulo e l'esponente per specificare la chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="86563-132">You will need the values of the modulus and the exponent to specify the public key.</span></span> <span data-ttu-id="86563-133">Tali valori dovrebbero essere forniti dalla parte che ha generato la coppia di chiavi pubblica/privata. Creare innanzitutto un <xref:System.Security.Cryptography.RSACryptoServiceProvider> oggetto che contenga la chiave pubblica che verificherà la firma, quindi inizializzare un <xref:System.Security.Cryptography.RSAParameters> struttura ai valori di modulo ed esponente che specificano la chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="86563-133">(The party that generated the public/private key pair should provide these values.) First create an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to hold the public key that will verify the signature, and then initialize an <xref:System.Security.Cryptography.RSAParameters> structure to the modulus and exponent values that specify the public key.</span></span>  
  
 <span data-ttu-id="86563-134">Il codice seguente illustra la creazione di una struttura <xref:System.Security.Cryptography.RSAParameters> .</span><span class="sxs-lookup"><span data-stu-id="86563-134">The following code shows the creation of an <xref:System.Security.Cryptography.RSAParameters> structure.</span></span> <span data-ttu-id="86563-135">La proprietà `Modulus` è impostata sul valore di una matrice di byte denominata `ModulusData` e la proprietà `Exponent` è impostata sul valore di una matrice di byte denominata `ExponentData`.</span><span class="sxs-lookup"><span data-stu-id="86563-135">The `Modulus` property is set to the value of a byte array called `ModulusData` and the `Exponent` property is set to the value of a byte array called `ExponentData`.</span></span>  
  
```vb  
Dim RSAKeyInfo As RSAParameters  
RSAKeyInfo.Modulus = ModulusData  
RSAKeyInfo.Exponent = ExponentData  
```  
  
```csharp  
RSAParameters RSAKeyInfo;  
RSAKeyInfo.Modulus = ModulusData;  
RSAKeyInfo.Exponent = ExponentData;  
```  
  
 <span data-ttu-id="86563-136">Dopo avere creato l'oggetto <xref:System.Security.Cryptography.RSAParameters> , è possibile inizializzare una nuova istanza della classe <xref:System.Security.Cryptography.RSACryptoServiceProvider> per i valori specificati in <xref:System.Security.Cryptography.RSAParameters>.</span><span class="sxs-lookup"><span data-stu-id="86563-136">After you have created the <xref:System.Security.Cryptography.RSAParameters> object, you can initialize a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class to the values specified in <xref:System.Security.Cryptography.RSAParameters>.</span></span> <span data-ttu-id="86563-137"><xref:System.Security.Cryptography.RSACryptoServiceProvider> viene a sua volta passato al costruttore di un oggetto <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> per trasferire la chiave.</span><span class="sxs-lookup"><span data-stu-id="86563-137">The <xref:System.Security.Cryptography.RSACryptoServiceProvider> is, in turn, passed to the constructor of an <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> to transfer the key.</span></span>  
  
 <span data-ttu-id="86563-138">Nell'esempio che segue viene illustrato questo processo.</span><span class="sxs-lookup"><span data-stu-id="86563-138">The following example illustrates this process.</span></span> <span data-ttu-id="86563-139">`HashValue` e `SignedHashValue` sono in questo caso matrici di byte fornite da una parte remota.</span><span class="sxs-lookup"><span data-stu-id="86563-139">In this example, `HashValue` and `SignedHashValue` are arrays of bytes provided by a remote party.</span></span> <span data-ttu-id="86563-140">La parte remota ha firmato `HashValue` usando l'algoritmo SHA1, producendo la firma digitale `SignedHashValue`.</span><span class="sxs-lookup"><span data-stu-id="86563-140">The remote party has signed the `HashValue` using the SHA1 algorithm, producing the digital signature `SignedHashValue`.</span></span> <span data-ttu-id="86563-141">Alla classe</span><span class="sxs-lookup"><span data-stu-id="86563-141">The</span></span>  
  
 <span data-ttu-id="86563-142">metodo <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> verifica che la firma digitale sia valida e usata per firmare il `HashValue`.</span><span class="sxs-lookup"><span data-stu-id="86563-142"><xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> method verifies that the digital signature is valid and was used to sign the `HashValue`.</span></span>  
  
```vb  
Dim RSA As New RSACryptoServiceProvider()  
RSA.ImportParameters(RSAKeyInfo)  
Dim RSADeformatter As New RSAPKCS1SignatureDeformatter(RSA)  
RSADeformatter.SetHashAlgorithm("SHA1")  
If RSADeformatter.VerifySignature(HashValue, SignedHashValue) Then  
   Console.WriteLine("The signature is valid.")  
Else  
   Console.WriteLine("The signture is not valid.")  
End If  
```  
  
```csharp  
RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
RSA.ImportParameters(RSAKeyInfo);  
RSAPKCS1SignatureDeformatter RSADeformatter = new RSAPKCS1SignatureDeformatter(RSA);  
RSADeformatter.SetHashAlgorithm("SHA1");  
if(RSADeformatter.VerifySignature(HashValue, SignedHashValue))  
{  
   Console.WriteLine("The signature is valid.");  
}  
else  
{  
   Console.WriteLine("The signature is not valid.");  
}  
```  
  
 <span data-ttu-id="86563-143">Nel frammento di codice sarà visualizzato il messaggio "`The signature is valid`" se la firma è valida e "`The signature is not valid`" in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="86563-143">This code fragment will display "`The signature is valid`" if the signature is valid and "`The signature is not valid`" if it is not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86563-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86563-144">See Also</span></span>  
 [<span data-ttu-id="86563-145">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="86563-145">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)

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
# <a name="cryptographic-signatures"></a>Firme di crittografia

Le firme digitali di crittografia usano algoritmi con chiave pubblica per garantire l'integrità dei dati. Quando viene applicata una firma digitale ai dati, questa può essere verificata da altri e può quindi provare che i dati non sono stati modificati dopo l'applicazione della firma. Per altre informazioni sulle firme digitali, vedere [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).

Questo argomento spiega come generare e verificare firme digitali usando le classi nello <xref:System.Security.Cryptography?displayProperty=nameWithType> spazio dei nomi.

## <a name="generating-signatures"></a>Generazione di firme

Le firme digitali vengono generalmente applicate a valori hash che rappresentano dati di maggiori dimensioni. Nell'esempio che segue viene applicata una firma digitale a un valore hash. Viene creata prima di tutto una nuova istanza della classe <xref:System.Security.Cryptography.RSACryptoServiceProvider> per generare una coppia di chiavi pubblica/privata. Viene quindi passato <xref:System.Security.Cryptography.RSACryptoServiceProvider> a una nuova istanza della classe <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> . In questo modo la chiave privata viene trasferita a <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>che esegue l'effettiva apposizione della firma digitale. Prima di firmare il codice hash, è necessario specificare un algoritmo hash da usare. Questo esempio usa l'algoritmo SHA1. Infine viene chiamato il metodo <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> per apporre la firma.

A causa di problemi di collisione con SHA1, Microsoft consiglia di SHA256 o meglio.

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

### <a name="signing-xml-files"></a>Firma di file XML

.NET Framework fornisce lo spazio dei nomi <xref:System.Security.Cryptography.Xml> che consente di firmare il codice XML. La firma XML è importante quando si vuole verificare l'origine del linguaggio XML. Se si usa ad esempio un servizio di quotazione dei titoli di borsa che usa il linguaggio XML, è possibile verificarne l'origine se è presente la firma.

Le classi in questo spazio dei nomi sono conformi alla [raccomandazione relativa alla sintassi e all'elaborazione della firma XML](https://www.w3.org/TR/xmldsig-core/) del World Wide Web Consortium.

## <a name="verifying-signatures"></a>Verifica di firme

Per verificare che i dati siano stati firmati da una determinata parte, è necessario avere le informazioni seguenti:

- La chiave pubblica della parte che ha firmato i dati.

- La firma digitale.

- I dati che sono stati firmati.

- L'algoritmo hash usato dal firmatario.

Usare la classe <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> per verificare una firma eseguita dalla classe <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> . Alla classe <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> deve essere fornita la chiave pubblica del firmatario. Sarà necessario avere i valori del modulo e l'esponente per specificare la chiave pubblica. L'entità che ha generato la coppia di chiavi pubblica/privata deve fornire questi valori. Creare innanzitutto un oggetto <xref:System.Security.Cryptography.RSACryptoServiceProvider> per conservare la chiave pubblica che verificherà la firma, quindi inizializzare una struttura <xref:System.Security.Cryptography.RSAParameters> per i valori di modulo ed esponente che specificano la chiave pubblica.

Il codice seguente illustra la creazione di una struttura <xref:System.Security.Cryptography.RSAParameters> . La proprietà `Modulus` è impostata sul valore di una matrice di byte denominata `modulusData` e la proprietà `Exponent` è impostata sul valore di una matrice di byte denominata `exponentData`.

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

Dopo avere creato l'oggetto <xref:System.Security.Cryptography.RSAParameters> , è possibile inizializzare una nuova istanza della classe <xref:System.Security.Cryptography.RSACryptoServiceProvider> per i valori specificati in <xref:System.Security.Cryptography.RSAParameters>. <xref:System.Security.Cryptography.RSACryptoServiceProvider> viene a sua volta passato al costruttore di un oggetto <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> per trasferire la chiave.

Nell'esempio che segue viene illustrato questo processo. `hashValue` e `signedHashValue` sono in questo caso matrici di byte fornite da una parte remota. La parte remota ha firmato `hashValue` usando l'algoritmo SHA1, producendo la firma digitale `signedHashValue`. Il metodo <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> verifica che la firma digitale sia valida e usata per firmare il `hashValue`.

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

Nel frammento di codice sarà visualizzato il messaggio "`The signature is valid`" se la firma è valida e "`The signature is not valid`" in caso contrario.

## <a name="see-also"></a>Vedere anche

- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)

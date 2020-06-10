---
title: Generazione di chiavi per crittografia e decrittografia
description: Informazioni su come creare e gestire chiavi simmetriche e asimmetriche per la crittografia e la decrittografia in .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET Framework], keys
- symmetric keys
- asymmetric keys [.NET Framework]
- cryptography [.NET Framework], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
ms.openlocfilehash: f8c3633d18e200037235502487d0d91d42083241
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84661809"
---
# <a name="generating-keys-for-encryption-and-decryption"></a><span data-ttu-id="dda26-103">Generazione di chiavi per crittografia e decrittografia</span><span class="sxs-lookup"><span data-stu-id="dda26-103">Generating Keys for Encryption and Decryption</span></span>
<span data-ttu-id="dda26-104">La creazione e la gestione di chiavi sono due momenti importanti del processo di crittografia.</span><span class="sxs-lookup"><span data-stu-id="dda26-104">Creating and managing keys is an important part of the cryptographic process.</span></span> <span data-ttu-id="dda26-105">Per gli algoritmi simmetrici è richiesta la creazione di una chiave e un vettore di inizializzazione (IV).</span><span class="sxs-lookup"><span data-stu-id="dda26-105">Symmetric algorithms require the creation of a key and an initialization vector (IV).</span></span> <span data-ttu-id="dda26-106">La chiave deve rimanere segreta per chiunque non debba decrittografare i dati.</span><span class="sxs-lookup"><span data-stu-id="dda26-106">The key must be kept secret from anyone who should not decrypt your data.</span></span> <span data-ttu-id="dda26-107">Il vettore di inizializzazione non deve rimanere segreto, ma dovrebbe essere modificato per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="dda26-107">The IV does not have to be secret, but should be changed for each session.</span></span> <span data-ttu-id="dda26-108">Gli algoritmi asimmetrici richiedono la creazione di una chiave pubblica e di una chiave privata.</span><span class="sxs-lookup"><span data-stu-id="dda26-108">Asymmetric algorithms require the creation of a public key and a private key.</span></span> <span data-ttu-id="dda26-109">La chiave pubblica può essere resa pubblica a chiunque, mentre quella privata deve essere nota solo alla parte che decrittograferà i dati crittografati con la chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="dda26-109">The public key can be made public to anyone, while the private key must known only by the party who will decrypt the data encrypted with the public key.</span></span> <span data-ttu-id="dda26-110">Questa sezione descrive come generare e gestire chiavi sia per gli algoritmi simmetrici che per quelli asimmetrici.</span><span class="sxs-lookup"><span data-stu-id="dda26-110">This section describes how to generate and manage keys for both symmetric and asymmetric algorithms.</span></span>  
  
## <a name="symmetric-keys"></a><span data-ttu-id="dda26-111">Chiavi simmetriche</span><span class="sxs-lookup"><span data-stu-id="dda26-111">Symmetric Keys</span></span>  
 <span data-ttu-id="dda26-112">Le classi di crittografia simmetrica disponibili in .NET Framework richiedono una chiave e un nuovo vettore di inizializzazione (IV, Initialization Vector) per crittografare e decrittografare i dati.</span><span class="sxs-lookup"><span data-stu-id="dda26-112">The symmetric encryption classes supplied by the .NET Framework require a key and a new initialization vector (IV) to encrypt and decrypt data.</span></span> <span data-ttu-id="dda26-113">Ogni volta che si crea una nuova istanza di una delle classi crittografiche simmetriche gestite usando il costruttore senza parametri, vengono create automaticamente una nuova chiave e un vettore di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="dda26-113">Whenever you create a new instance of one of the managed symmetric cryptographic classes using the parameterless constructor, a new key and IV are automatically created.</span></span> <span data-ttu-id="dda26-114">Per riuscire a decrittografare i dati, i destinatari devono avere la stessa chiave e lo stesso vettore di inizializzazione e devono usare il medesimo algoritmo di crittografia.</span><span class="sxs-lookup"><span data-stu-id="dda26-114">Anyone that you allow to decrypt your data must possess the same key and IV and use the same algorithm.</span></span> <span data-ttu-id="dda26-115">Generalmente è necessario creare una chiave e un vettore di inizializzazione nuovi per ogni sessione e né la chiave né il vettore devono essere archiviati per un uso in una sessione successiva.</span><span class="sxs-lookup"><span data-stu-id="dda26-115">Generally, a new key and IV should be created for every session, and neither the key nor IV should be stored for use in a later session.</span></span>  
  
 <span data-ttu-id="dda26-116">Per comunicare una chiave simmetrica e un vettore di inizializzazione a una parte remota, la chiave simmetrica viene generalmente crittografata mediante la crittografia asimmetrica.</span><span class="sxs-lookup"><span data-stu-id="dda26-116">To communicate a symmetric key and IV to a remote party, you would usually encrypt the symmetric key by using asymmetric encryption.</span></span> <span data-ttu-id="dda26-117">L'invio della chiave in una rete non protetta senza crittografarla non è sicuro, poiché chiunque intercetti la chiave e il vettore di inizializzazione è in grado di decrittografare i dati.</span><span class="sxs-lookup"><span data-stu-id="dda26-117">Sending the key across an insecure network without encrypting it is unsafe, because anyone who intercepts the key and IV can then decrypt your data.</span></span> <span data-ttu-id="dda26-118">Per ulteriori informazioni sullo scambio di dati utilizzando la crittografia, vedere [Creare uno schema di crittografia](creating-a-cryptographic-scheme.md).</span><span class="sxs-lookup"><span data-stu-id="dda26-118">For more information about exchanging data by using encryption, see [Creating a Cryptographic Scheme](creating-a-cryptographic-scheme.md).</span></span>  
  
 <span data-ttu-id="dda26-119">L'esempio seguente illustra la creazione di una nuova istanza della classe <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> che implementa l'algoritmo TripleDES.</span><span class="sxs-lookup"><span data-stu-id="dda26-119">The following example shows the creation of a new instance of the <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> class that implements the TripleDES algorithm.</span></span>  
  
```vb  
Dim tdes As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
```  
  
```csharp  
TripleDESCryptoServiceProvider tdes = new TripleDESCryptoServiceProvider();  
```  
  
 <span data-ttu-id="dda26-120">Quando viene eseguito il codice precedente, una chiave e un vettore di inizializzazione nuovi vengono generati e inseriti rispettivamente nelle proprietà **Key** e **IV** .</span><span class="sxs-lookup"><span data-stu-id="dda26-120">When the previous code is executed, a new key and IV are generated and placed in the **Key** and **IV** properties, respectively.</span></span>  
  
 <span data-ttu-id="dda26-121">Talvolta può essere necessario generare più chiavi.</span><span class="sxs-lookup"><span data-stu-id="dda26-121">Sometimes you might need to generate multiple keys.</span></span> <span data-ttu-id="dda26-122">In questa situazione è possibile creare una nuova istanza di una classe che implementa un algoritmo simmetrico e quindi creare una chiave e un vettore di inizializzazione nuovi chiamando i metodi **GenerateKey** e **GenerateIV** .</span><span class="sxs-lookup"><span data-stu-id="dda26-122">In this situation, you can create a new instance of a class that implements a symmetric algorithm and then create a new key and IV by calling the **GenerateKey** and **GenerateIV** methods.</span></span> <span data-ttu-id="dda26-123">Nell'esempio di codice seguente viene illustrato come creare nuove chiavi e IV dopo che è stata creata una nuova istanza della classe di crittografia simmetrica.</span><span class="sxs-lookup"><span data-stu-id="dda26-123">The following code example illustrates how to create new keys and IVs after a new instance of the symmetric cryptographic class has been made.</span></span>  
  
```vb  
Dim tdes As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
tdes.GenerateIV()  
tdes.GenerateKey()  
```  
  
```csharp  
TripleDESCryptoServiceProvider tdes = new TripleDESCryptoServiceProvider();  
tdes.GenerateIV();  
tdes.GenerateKey();  
```  
  
 <span data-ttu-id="dda26-124">Quando viene eseguito il codice precedente, una chiave e un vettore di inizializzazione nuovi vengono generati quando viene creata la nuova istanza di **TripleDESCryptoServiceProvider** .</span><span class="sxs-lookup"><span data-stu-id="dda26-124">When the previous code is executed, a key and IV are generated when the new instance of **TripleDESCryptoServiceProvider** is made.</span></span> <span data-ttu-id="dda26-125">Un'altra chiave e vettore di inizializzazione vengono creati quando vengono chiamati i metodi **GenerateKey** e **GenerateIV** .</span><span class="sxs-lookup"><span data-stu-id="dda26-125">Another key and IV are created when the **GenerateKey** and **GenerateIV** methods are called.</span></span>  
  
## <a name="asymmetric-keys"></a><span data-ttu-id="dda26-126">Chiavi asimmetriche</span><span class="sxs-lookup"><span data-stu-id="dda26-126">Asymmetric Keys</span></span>  
 <span data-ttu-id="dda26-127">In .NET Framework sono incluse le classi <xref:System.Security.Cryptography.RSACryptoServiceProvider> e <xref:System.Security.Cryptography.DSACryptoServiceProvider> per la crittografia asimmetrica.</span><span class="sxs-lookup"><span data-stu-id="dda26-127">The .NET Framework provides the <xref:System.Security.Cryptography.RSACryptoServiceProvider> and <xref:System.Security.Cryptography.DSACryptoServiceProvider> classes for asymmetric encryption.</span></span> <span data-ttu-id="dda26-128">Queste classi creano una coppia di chiavi pubblica/privata quando si usa il costruttore senza parametri per creare una nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="dda26-128">These classes create a public/private key pair when you use the parameterless constructor to create a new instance.</span></span> <span data-ttu-id="dda26-129">Le chiavi asimmetriche possono essere archiviate per un uso in più sessioni o generate per una sola sessione.</span><span class="sxs-lookup"><span data-stu-id="dda26-129">Asymmetric keys can be either stored for use in multiple sessions or generated for one session only.</span></span> <span data-ttu-id="dda26-130">Mentre la chiave pubblica può essere generalmente resa disponibile, la chiave privata va custodita con cura.</span><span class="sxs-lookup"><span data-stu-id="dda26-130">While the public key can be made generally available, the private key should be closely guarded.</span></span>  
  
 <span data-ttu-id="dda26-131">Una coppia di chiavi pubblica/privata viene generata ogni volta che viene creata una nuova istanza di una classe di algoritmo asimmetrico.</span><span class="sxs-lookup"><span data-stu-id="dda26-131">A public/private key pair is generated whenever a new instance of an asymmetric algorithm class is created.</span></span> <span data-ttu-id="dda26-132">Dopo che è stata creata una nuova istanza della classe, le informazioni sulla chiave possono essere estratte con uno dei metodi indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="dda26-132">After a new instance of the class is created, the key information can be extracted using one of two methods:</span></span>  
  
- <span data-ttu-id="dda26-133">Il metodo <xref:System.Security.Cryptography.RSA.ToXmlString%2A> , che restituisce una rappresentazione XML delle informazioni sulla chiave.</span><span class="sxs-lookup"><span data-stu-id="dda26-133">The <xref:System.Security.Cryptography.RSA.ToXmlString%2A> method, which returns an XML representation of the key information.</span></span>  
  
- <span data-ttu-id="dda26-134">Il metodo <xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> , che restituisce una struttura <xref:System.Security.Cryptography.RSAParameters> contenente le informazioni sulla chiave.</span><span class="sxs-lookup"><span data-stu-id="dda26-134">The <xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> method, which returns an <xref:System.Security.Cryptography.RSAParameters> structure that holds the key information.</span></span>  
  
 <span data-ttu-id="dda26-135">Entrambi i metodi accettano un valore Boolean che indica se restituire solo le informazioni sulla chiave pubblica o le informazioni sia sulla chiave pubblica che sulla chiave privata.</span><span class="sxs-lookup"><span data-stu-id="dda26-135">Both methods accept a Boolean value that indicates whether to return only the public key information or to return both the public-key and the private-key information.</span></span> <span data-ttu-id="dda26-136">Una classe **RSACryptoServiceProvider** può essere inizializzata in base al valore di una struttura **RSAParameters** usando il metodo <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> .</span><span class="sxs-lookup"><span data-stu-id="dda26-136">An **RSACryptoServiceProvider** class can be initialized to the value of an **RSAParameters** structure by using the <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> method.</span></span>  
  
 <span data-ttu-id="dda26-137">Le chiavi private asimmetriche non devono essere mai archiviate in modalità verbatim o in testo normale nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="dda26-137">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="dda26-138">Se è necessario archiviare una chiave privata, è opportuno usare un contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="dda26-138">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="dda26-139">Per altre informazioni su come archiviare una chiave privata in un contenitore di chiavi, vedere [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="dda26-139">For more on how to store a private key in a key container, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>  
  
 <span data-ttu-id="dda26-140">L'esempio di codice seguente crea una nuova istanza della classe **RSACryptoServiceProvider** , che crea una coppia di chiavi pubblica/privata e salva le informazioni sulla chiave pubblica in una struttura **RSAParameters** .</span><span class="sxs-lookup"><span data-stu-id="dda26-140">The following code example creates a new instance of the **RSACryptoServiceProvider** class, creating a public/private key pair, and saves the public key information to an **RSAParameters** structure.</span></span>  
  
```vb  
'Generate a public/private key pair.  
Dim rsa as RSACryptoServiceProvider = new RSACryptoServiceProvider()  
'Save the public key information to an RSAParameters structure.  
Dim rsaKeyInfo As RSAParameters = rsa.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();  
//Save the public key information to an RSAParameters structure.  
RSAParameters rsaKeyInfo = rsa.ExportParameters(false);  
```  
  
## <a name="see-also"></a><span data-ttu-id="dda26-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dda26-141">See also</span></span>

- [<span data-ttu-id="dda26-142">Encrypting Data</span><span class="sxs-lookup"><span data-stu-id="dda26-142">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="dda26-143">Decrittografia di dati</span><span class="sxs-lookup"><span data-stu-id="dda26-143">Decrypting Data</span></span>](decrypting-data.md)
- [<span data-ttu-id="dda26-144">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="dda26-144">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="dda26-145">How to: Store Asymmetric Keys in a Key Container</span><span class="sxs-lookup"><span data-stu-id="dda26-145">How to: Store Asymmetric Keys in a Key Container</span></span>](how-to-store-asymmetric-keys-in-a-key-container.md)

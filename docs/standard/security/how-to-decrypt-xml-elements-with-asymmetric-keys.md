---
title: 'Procedura: Decrittografare gli elementi XML con chiavi asimmetriche'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.RSACryptoServiceProvider class
- asymmetric keys
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- decryption
ms.assetid: dd5de491-dafe-4b94-966d-99714b2e754a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c1891bf91095a5c09257b795c66e96dbc2bf69d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64653889"
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a><span data-ttu-id="c463b-102">Procedura: Decrittografare gli elementi XML con chiavi asimmetriche</span><span class="sxs-lookup"><span data-stu-id="c463b-102">How to: Decrypt XML Elements with Asymmetric Keys</span></span>
<span data-ttu-id="c463b-103">È possibile usare le classi dello spazio dei nomi <xref:System.Security.Cryptography.Xml> per crittografare e decrittografare un elemento all'interno di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="c463b-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="c463b-104">La crittografia XML consente di scambiare o archiviare dati XML crittografati in modo standard, garantendo un'adeguata protezione dei dati da letture non autorizzate.</span><span class="sxs-lookup"><span data-stu-id="c463b-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="c463b-105">Per altre informazioni sullo standard della crittografia XML, vedere la raccomandazione del World Wide Web Consortium (W3C) [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span><span class="sxs-lookup"><span data-stu-id="c463b-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  
  
 <span data-ttu-id="c463b-106">L'esempio in questa procedura decrittografa un elemento XML che era stato crittografato mediante i metodi descritti in [come: Crittografare gli elementi XML con chiavi asimmetriche](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="c463b-106">The example in this procedure decrypts an XML element that was encrypted using the methods described in [How to: Encrypt XML Elements with Asymmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  <span data-ttu-id="c463b-107">Trova un <`EncryptedData`> elemento, decrittografa l'elemento e quindi sostituisce l'elemento con l'elemento XML originale in testo normale.</span><span class="sxs-lookup"><span data-stu-id="c463b-107">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
 <span data-ttu-id="c463b-108">Questo esempio decrittografa un elemento XML mediante due chiavi.</span><span class="sxs-lookup"><span data-stu-id="c463b-108">This example decrypts an XML element using two keys.</span></span>  <span data-ttu-id="c463b-109">Recupera una chiave privata RSA generata in precedenza da un contenitore di chiavi e quindi Usa la chiave RSA per decrittografare una chiave della sessione archiviati nel <`EncryptedKey`> dell'elemento il <`EncryptedData`> elemento.</span><span class="sxs-lookup"><span data-stu-id="c463b-109">It retrieves a previously generated RSA private key from a key container, and then uses the RSA key to decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="c463b-110">L'esempio usa quindi la chiave di sessione per decrittografare l'elemento XML.</span><span class="sxs-lookup"><span data-stu-id="c463b-110">The example then uses the session key to decrypt the XML element.</span></span>  
  
 <span data-ttu-id="c463b-111">Questo esempio è adatto per situazioni in cui più applicazioni devono condividere dati crittografati o in cui un'applicazione deve salvare dati crittografati tra un'esecuzione e l'altra.</span><span class="sxs-lookup"><span data-stu-id="c463b-111">This example is appropriate for situations where multiple applications have to share encrypted data or where an application has to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a><span data-ttu-id="c463b-112">Per decrittografare un elemento XML con una chiave asimmetrica</span><span class="sxs-lookup"><span data-stu-id="c463b-112">To decrypt an XML element with an asymmetric key</span></span>  
  
1. <span data-ttu-id="c463b-113">Creare un oggetto <xref:System.Security.Cryptography.CspParameters> e specificare il nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="c463b-113">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="c463b-114">Recuperare una chiave asimmetrica generata in precedenza dal contenitore usando l'oggetto <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="c463b-114">Retrieve a previously generated asymmetric key from the container using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> object.</span></span>  <span data-ttu-id="c463b-115">La chiave viene recuperata automaticamente dal contenitore di chiavi quando si passa l'oggetto <xref:System.Security.Cryptography.CspParameters> al costruttore <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="c463b-115">The key is automatically retrieved from the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the <xref:System.Security.Cryptography.RSACryptoServiceProvider> constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="c463b-116">Creare un nuovo oggetto <xref:System.Security.Cryptography.Xml.EncryptedXml> per decrittografare il documento.</span><span class="sxs-lookup"><span data-stu-id="c463b-116">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object to decrypt the document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4. <span data-ttu-id="c463b-117">Aggiungere un mapping di chiave/nome per associare la chiave RSA all'elemento entro il documento da decrittografare.</span><span class="sxs-lookup"><span data-stu-id="c463b-117">Add a key/name mapping to associate the RSA key with the element within the document that should be decrypted.</span></span>  <span data-ttu-id="c463b-118">È necessario usare per la chiave lo stesso nome specificato durante la crittografia del documento.</span><span class="sxs-lookup"><span data-stu-id="c463b-118">You must use the same name for the key that you used when you encrypted the document.</span></span>  <span data-ttu-id="c463b-119">Si noti che questo nome è distinto dal nome usato per identificare la chiave nel contenitore di chiavi specificato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="c463b-119">Note that this name is separate from the name used to identify the key in the key container specified in step 1.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5. <span data-ttu-id="c463b-120">Chiamare il <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> metodo per decrittografare il <`EncryptedData`> elemento.</span><span class="sxs-lookup"><span data-stu-id="c463b-120">Call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to decrypt the <`EncryptedData`> element.</span></span>  <span data-ttu-id="c463b-121">Questo metodo usa la chiave RSA per decrittografare la chiave di sessione e usa automaticamente la chiave di sessione per decrittografare l'elemento XML.</span><span class="sxs-lookup"><span data-stu-id="c463b-121">This method uses the RSA key to decrypt the session key and automatically uses the session key to decrypt the XML element.</span></span>  <span data-ttu-id="c463b-122">Sostituisce anche automaticamente il <`EncryptedData`> elemento con il testo non crittografato originale.</span><span class="sxs-lookup"><span data-stu-id="c463b-122">It also automatically replaces the <`EncryptedData`> element with the original plaintext.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6. <span data-ttu-id="c463b-123">Salvare il documento XML.</span><span class="sxs-lookup"><span data-stu-id="c463b-123">Save the XML document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="c463b-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="c463b-124">Example</span></span>  
 <span data-ttu-id="c463b-125">Questo esempio presuppone che sia presente un file denominato `test.xml` nella stessa directory del programma compilato</span><span class="sxs-lookup"><span data-stu-id="c463b-125">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="c463b-126">Presuppone anche che `test.xml` contiene un elemento XML che era stato crittografato mediante le tecniche descritte in [come: Crittografare gli elementi XML con chiavi asimmetriche](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="c463b-126">It also assumes that `test.xml` contains an XML element that was encrypted using the techniques described in [How to: Encrypt XML Elements with Asymmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  
  
 [!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c463b-127">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c463b-127">Compiling the Code</span></span>  
  
- <span data-ttu-id="c463b-128">Per compilare questo esempio, è necessario includere un riferimento a `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="c463b-128">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="c463b-129">Includere gli spazi dei nomi seguenti: <xref:System.Xml>, <xref:System.Security.Cryptography> e <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="c463b-129">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c463b-130">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c463b-130">.NET Framework Security</span></span>  
 <span data-ttu-id="c463b-131">Non archiviare mai una chiave crittografica in testo non crittografato e non trasferire mai in testo non crittografato una chiave simmetrica tra computer.</span><span class="sxs-lookup"><span data-stu-id="c463b-131">Never store a symmetric cryptographic key in plaintext or transfer a symmetric key between machines in plaintext.</span></span>  <span data-ttu-id="c463b-132">Non archiviare né trasferire mai in testo non crittografato, inoltre, la chiave privata di una coppia di chiavi asimmetriche.</span><span class="sxs-lookup"><span data-stu-id="c463b-132">Additionally, never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="c463b-133">Per altre informazioni sulle chiavi crittografiche simmetriche e asimmetriche, vedere [generazione di chiavi per crittografia e decrittografia](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="c463b-133">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="c463b-134">Non incorporare mai una chiave direttamente nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="c463b-134">Never embed a key directly into your source code.</span></span>  <span data-ttu-id="c463b-135">Le chiavi incorporate possono essere lette facilmente da un assembly tramite [Ildasm.exe (Disassembler IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) oppure aprendo l'assembly in un editor di testo quale Blocco note.</span><span class="sxs-lookup"><span data-stu-id="c463b-135">Embedded keys can be easily read from an assembly by using [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
 <span data-ttu-id="c463b-136">Dopo avere usato una chiave crittografica, cancellarla dalla memoria impostando ogni byte su zero oppure chiamando il metodo <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> della classe di crittografia gestita.</span><span class="sxs-lookup"><span data-stu-id="c463b-136">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  <span data-ttu-id="c463b-137">Le chiavi crittografiche possono essere a volte lette dalla memoria da un debugger oppure possono essere lette da un disco rigido, se viene eseguito il paging su disco della posizione di memoria.</span><span class="sxs-lookup"><span data-stu-id="c463b-137">Cryptographic keys can sometimes be read from memory by a debugger or read from a hard drive if the memory location is paged to disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c463b-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c463b-138">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="c463b-139">Procedura: Crittografare gli elementi XML con chiavi asimmetriche</span><span class="sxs-lookup"><span data-stu-id="c463b-139">How to: Encrypt XML Elements with Asymmetric Keys</span></span>](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)

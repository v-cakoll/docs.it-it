---
title: 'Procedura: decrittografare gli elementi XML con chiavi simmetriche'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- symmetric keys
- System.Security.Cryptography.EncryptedXml class
- System.Security.Cryptography.RijndaelManaged class
- XML encryption
- Rijndael
- decryption
ms.assetid: 6038aff0-f92c-4e29-a618-d793410410d8
ms.openlocfilehash: bb34332d345ee7bcb9037dc7bdf0deebbe70c3c9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277427"
---
# <a name="how-to-decrypt-xml-elements-with-symmetric-keys"></a><span data-ttu-id="3c912-102">Procedura: decrittografare gli elementi XML con chiavi simmetriche</span><span class="sxs-lookup"><span data-stu-id="3c912-102">How to: Decrypt XML Elements with Symmetric Keys</span></span>
<span data-ttu-id="3c912-103">È possibile usare le classi dello spazio dei nomi <xref:System.Security.Cryptography.Xml> per crittografare un elemento all'interno di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="3c912-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="3c912-104">La crittografia XML consente di archiviare o trasportare contenuti XML sensibili, senza preoccuparsi che i dati vengano letti con facilità.</span><span class="sxs-lookup"><span data-stu-id="3c912-104">XML Encryption allows you to store or transport sensitive XML, without worrying about the data being easily read.</span></span>  <span data-ttu-id="3c912-105">Questo esempio di codice consente di decrittografare un elemento XML usando l'algoritmo Advanced Encryption Standard (AES), noto anche come Rijndael.</span><span class="sxs-lookup"><span data-stu-id="3c912-105">This code example decrypts an XML element using the Advanced Encryption Standard (AES) algorithm, also known as Rijndael.</span></span>  
  
 <span data-ttu-id="3c912-106">Per informazioni su come crittografare un elemento XML usando questa procedura, vedere [procedura: crittografare gli elementi XML con chiavi simmetriche](how-to-encrypt-xml-elements-with-symmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="3c912-106">For information about how to encrypt an XML element using this procedure, see [How to: Encrypt XML Elements with Symmetric Keys](how-to-encrypt-xml-elements-with-symmetric-keys.md).</span></span>  
  
 <span data-ttu-id="3c912-107">Quando si usa un algoritmo simmetrico come AES per crittografare i dati XML, è necessario usare la stessa chiave per crittografare e decrittografare i dati XML.</span><span class="sxs-lookup"><span data-stu-id="3c912-107">When you use a symmetric algorithm like AES to encrypt XML data, you must use the same key to encrypt and decrypt the XML data.</span></span>  <span data-ttu-id="3c912-108">L'esempio riportato in questa procedura presuppone che i dati XML crittografati siano stati decrittografati mediante la stessa chiave e che le parti che eseguono le operazioni di crittografia e decrittografia si accordino sull'algoritmo e sulla chiave da usare.</span><span class="sxs-lookup"><span data-stu-id="3c912-108">The example in this procedure assumes that the encrypted XML was encrypted using the same key, and that the encrypting and decrypting parties agree on the algorithm and key to use.</span></span>  <span data-ttu-id="3c912-109">L'esempio non archivia né crittografa la chiave AES nei dati XML crittografati.</span><span class="sxs-lookup"><span data-stu-id="3c912-109">This example does not store or encrypt the AES key within the encrypted XML.</span></span>  
  
 <span data-ttu-id="3c912-110">Questo esempio è appropriato per situazioni in cui una singola applicazione deve crittografare i dati in base a una chiave della sessione archiviata in memoria o in base a una chiave di crittografia avanzata derivata da una password.</span><span class="sxs-lookup"><span data-stu-id="3c912-110">This example is appropriate for situations where a single application needs to encrypt data based on a session key stored in memory, or based on a cryptographically strong key derived from a password.</span></span>  <span data-ttu-id="3c912-111">Per i casi in cui due o più applicazioni devono condividere dati XML crittografati, è consigliabile usare uno schema di crittografia basato su un algoritmo asimmetrico o un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="3c912-111">For situations where two or more applications need to share encrypted XML data, consider using an encryption scheme based on an asymmetric algorithm or an X.509 certificate.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-a-symmetric-key"></a><span data-ttu-id="3c912-112">Per decrittografare un elemento XML con una chiave simmetrica</span><span class="sxs-lookup"><span data-stu-id="3c912-112">To decrypt an XML element with a symmetric key</span></span>  
  
1. <span data-ttu-id="3c912-113">Crittografare un elemento XML con la chiave generata in precedenza usando le tecniche descritte in [procedura: crittografare gli elementi XML con chiavi simmetriche](how-to-encrypt-xml-elements-with-symmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="3c912-113">Encrypt an XML element with the previously generated key using the techniques described in [How to: Encrypt XML Elements with Symmetric Keys](how-to-encrypt-xml-elements-with-symmetric-keys.md).</span></span>  
  
2. <span data-ttu-id="3c912-114">Trovare l' `EncryptedData` elemento <> (definito dallo standard di crittografia XML) in un <xref:System.Xml.XmlDocument> oggetto che contiene il codice XML crittografato e creare un nuovo <xref:System.Xml.XmlElement> oggetto per rappresentare tale elemento.</span><span class="sxs-lookup"><span data-stu-id="3c912-114">Find the <`EncryptedData`> element (defined by the XML Encryption standard) in an <xref:System.Xml.XmlDocument> object that contains the encrypted XML and create a new <xref:System.Xml.XmlElement> object to represent that element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementSymmetric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#10)]  
  
3. <span data-ttu-id="3c912-115">Creare un oggetto <xref:System.Security.Cryptography.Xml.EncryptedData> caricando i dati XML non elaborati dall'oggetto <xref:System.Xml.XmlElement> creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="3c912-115">Create an <xref:System.Security.Cryptography.Xml.EncryptedData> object by loading the raw XML data from the previously created <xref:System.Xml.XmlElement> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementSymmetric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#11)]  
  
4. <span data-ttu-id="3c912-116">Creare un nuovo oggetto <xref:System.Security.Cryptography.Xml.EncryptedXml> e usarlo per decrittografare i dati XML mediante la stessa chiave usata per la crittografia.</span><span class="sxs-lookup"><span data-stu-id="3c912-116">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object and use it to decrypt the XML data using the same key that was used for encryption.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#12)]
     [!code-vb[HowToEncryptXMLElementSymmetric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#12)]  
  
5. <span data-ttu-id="3c912-117">Sostituire l'elemento crittografato con l'elemento di testo normale appena decrittografato all'interno del documento XML.</span><span class="sxs-lookup"><span data-stu-id="3c912-117">Replace the encrypted element with the newly decrypted plaintext element within the XML document.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#13)]
     [!code-vb[HowToEncryptXMLElementSymmetric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="3c912-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c912-118">Example</span></span>  
 <span data-ttu-id="3c912-119">Questo esempio presuppone che sia presente un file denominato `"test.xml"` nella stessa directory del programma compilato</span><span class="sxs-lookup"><span data-stu-id="3c912-119">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="3c912-120">e che `"test.xml"` contenga un elemento `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="3c912-120">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="3c912-121">È possibile inserire il codice XML seguente in un file denominato `test.xml` e usarlo con questo esempio.</span><span class="sxs-lookup"><span data-stu-id="3c912-121">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3c912-122">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3c912-122">Compiling the Code</span></span>  
  
- <span data-ttu-id="3c912-123">Per compilare questo esempio, è necessario includere un riferimento a `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="3c912-123">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="3c912-124">Includere gli spazi dei nomi seguenti: <xref:System.Xml>, <xref:System.Security.Cryptography> e <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="3c912-124">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="3c912-125">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3c912-125">.NET Framework Security</span></span>  
 <span data-ttu-id="3c912-126">Non archiviare mai una chiave crittografica in testo non crittografato e non trasferire mai in testo non crittografato una chiave tra computer.</span><span class="sxs-lookup"><span data-stu-id="3c912-126">Never store a cryptographic key in plaintext or transfer a key between machines in plaintext.</span></span>  
  
 <span data-ttu-id="3c912-127">Dopo aver usato una chiave di crittografia simmetrica, cancellarla dalla memoria impostando ogni byte su zero o chiamando il metodo <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> della classe di crittografia gestita.</span><span class="sxs-lookup"><span data-stu-id="3c912-127">When you are done using a symmetric cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c912-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c912-128">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="3c912-129">Procedura: crittografare gli elementi XML con chiavi simmetriche</span><span class="sxs-lookup"><span data-stu-id="3c912-129">How to: Encrypt XML Elements with Symmetric Keys</span></span>](how-to-encrypt-xml-elements-with-symmetric-keys.md)

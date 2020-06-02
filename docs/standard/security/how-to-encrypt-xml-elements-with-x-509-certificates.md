---
title: 'Procedura: crittografare gli elementi XML con certificati X.509'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET Framework], X.509 certificates
- cryptography [.NET Framework], X.509 certificates
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: 761f1c66-631c-47af-aa86-ad9c50cfa453
ms.openlocfilehash: 9cdd8e52be11eeba86ec406510f40f1a08809ff8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277219"
---
# <a name="how-to-encrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="6692c-102">Procedura: crittografare gli elementi XML con certificati X.509</span><span class="sxs-lookup"><span data-stu-id="6692c-102">How to: Encrypt XML Elements with X.509 Certificates</span></span>
<span data-ttu-id="6692c-103">È possibile usare le classi dello spazio dei nomi <xref:System.Security.Cryptography.Xml> per crittografare un elemento all'interno di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="6692c-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="6692c-104">La crittografia XML consente di scambiare o archiviare dati XML crittografati in modo standard, garantendo un'adeguata protezione dei dati da letture non autorizzate.</span><span class="sxs-lookup"><span data-stu-id="6692c-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="6692c-105">Per ulteriori informazioni sullo standard di crittografia XML, vedere la specifica World Wide Web Consortium (W3C) per la crittografia XML disponibile all'indirizzo <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="6692c-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="6692c-106">È possibile usare la crittografia XML per sostituire qualsiasi elemento o documento XML con un elemento <`EncryptedData`> contenente i dati XML crittografati.</span><span class="sxs-lookup"><span data-stu-id="6692c-106">You can use XML Encryption to replace any XML element or document with an <`EncryptedData`> element that contains the encrypted XML data.</span></span> <span data-ttu-id="6692c-107">Nell'elemento <`EncryptedData`> possono essere inclusi sottoelementi in cui sono incluse informazioni sulle chiavi e sui processi usati durante la crittografia.</span><span class="sxs-lookup"><span data-stu-id="6692c-107">The <`EncryptedData`> element can contain sub elements that include information about the keys and processes used during encryption.</span></span>  <span data-ttu-id="6692c-108">La crittografia XML consente a un documento di contenere più elementi crittografati e consente a un elemento di essere crittografato più volte.</span><span class="sxs-lookup"><span data-stu-id="6692c-108">XML Encryption allows a document to contain multiple encrypted elements and allows an element to be encrypted multiple times.</span></span>  <span data-ttu-id="6692c-109">L'esempio di codice relativo a questa procedura illustra come creare un elemento <`EncryptedData`> insieme a diversi altri sottoelementi utilizzabili in un secondo momento durante la decrittografia.</span><span class="sxs-lookup"><span data-stu-id="6692c-109">The code example in this procedure shows you how to create an <`EncryptedData`> element along with several other sub elements that you can use later during decryption.</span></span>  
  
 <span data-ttu-id="6692c-110">Questo esempio crittografa un elemento XML mediante due chiavi.</span><span class="sxs-lookup"><span data-stu-id="6692c-110">This example encrypts an XML element using two keys.</span></span> <span data-ttu-id="6692c-111">Genera un certificato X.509 di test usando lo [Strumento di creazione dei certificati (Makecert.exe)](/windows/desktop/SecCrypto/makecert) e lo salva in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="6692c-111">It generates a test X.509 certificate using the [Certificate Creation Tool (Makecert.exe)](/windows/desktop/SecCrypto/makecert) and saves the certificate to a certificate store.</span></span> <span data-ttu-id="6692c-112">Questo esempio richiama il certificato a livello di codice e lo usa per crittografare un elemento XML mediante il metodo <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A>.</span><span class="sxs-lookup"><span data-stu-id="6692c-112">The example then programmatically retrieves the certificate and uses it to encrypt an XML element using the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method.</span></span> <span data-ttu-id="6692c-113">Internamente, il metodo <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> crea una chiave di sessione separata e la usa per crittografare il documento XML.</span><span class="sxs-lookup"><span data-stu-id="6692c-113">Internally, the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method creates a separate session key and uses it to encrypt the XML document.</span></span> <span data-ttu-id="6692c-114">La chiave di sessione viene crittografata da questo metodo e salvata insieme ai dati XML crittografati all'interno di un nuovo elemento <`EncryptedData`>.</span><span class="sxs-lookup"><span data-stu-id="6692c-114">This method encrypts the session key and saves it along with the encrypted XML within a new <`EncryptedData`> element.</span></span>  
  
 <span data-ttu-id="6692c-115">Per decrittografare l'elemento XML, chiamare semplicemente il metodo <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>, che richiama automaticamente il certificato X.509 dall'archivio ed esegue la descrizione necessaria.</span><span class="sxs-lookup"><span data-stu-id="6692c-115">To decrypt the XML element, simply call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method, which automatically retrieves the X.509 certificate from the store and performs the necessary decryption.</span></span>  <span data-ttu-id="6692c-116">Per altre informazioni su come decrittografare un elemento XML che era stato crittografato tramite questa procedura, vedere [Procedura: Decrittografare gli elementi XML con certificati X.509](how-to-decrypt-xml-elements-with-x-509-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6692c-116">For more information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with X.509 Certificates](how-to-decrypt-xml-elements-with-x-509-certificates.md).</span></span>  
  
 <span data-ttu-id="6692c-117">Questo esempio è adatto per situazioni in cui più applicazioni devono condividere dati crittografati o in cui un'applicazione deve salvare dati crittografati tra un'esecuzione e l'altra.</span><span class="sxs-lookup"><span data-stu-id="6692c-117">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="6692c-118">Per crittografare un elemento XML con un certificato X.509</span><span class="sxs-lookup"><span data-stu-id="6692c-118">To encrypt an XML element with an X.509 certificate</span></span>  
  
1. <span data-ttu-id="6692c-119">Usare lo [Strumento di creazione dei certificati (Makecert.exe)](/windows/desktop/SecCrypto/makecert) per generare un certificato X.509 di test e inserirlo nell'archivio utente locale.</span><span class="sxs-lookup"><span data-stu-id="6692c-119">Use the [Certificate Creation Tool (Makecert.exe)](/windows/desktop/SecCrypto/makecert) to generate a test X.509 certificate and place it in the local user store.</span></span> <span data-ttu-id="6692c-120">Si deve generare una chiave di scambio e si deve rendere esportabile la chiave.</span><span class="sxs-lookup"><span data-stu-id="6692c-120">You must generate an exchange key and you must make the key exportable.</span></span> <span data-ttu-id="6692c-121">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="6692c-121">Run the following command:</span></span>  
  
    ```console  
    makecert -r -pe -n "CN=XML_ENC_TEST_CERT" -b 01/01/2005 -e 01/01/2010 -sky exchange -ss my  
    ```  
  
2. <span data-ttu-id="6692c-122">Creare un oggetto <xref:System.Security.Cryptography.X509Certificates.X509Store> e inizializzarlo per aprire l'archivio utente corrente.</span><span class="sxs-lookup"><span data-stu-id="6692c-122">Create an <xref:System.Security.Cryptography.X509Certificates.X509Store> object and initialize it to open the current user store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#2)]  
  
3. <span data-ttu-id="6692c-123">Aprire l'archivio in modalità di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="6692c-123">Open the store in read-only mode.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#3)]  
  
4. <span data-ttu-id="6692c-124">Inizializzare un <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> con tutti i certificati dell'archivio.</span><span class="sxs-lookup"><span data-stu-id="6692c-124">Initialize an <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> with all of the certificates in the store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#4)]  
  
5. <span data-ttu-id="6692c-125">Enumerare i certificati dell'archivio e trovare il certificato con il nome appropriato.</span><span class="sxs-lookup"><span data-stu-id="6692c-125">Enumerate through the certificates in the store and find the certificate with the appropriate name.</span></span>  <span data-ttu-id="6692c-126">In questo esempio il certificato è denominato `"CN=XML_ENC_TEST_CERT"`.</span><span class="sxs-lookup"><span data-stu-id="6692c-126">In this example, the certificate is named `"CN=XML_ENC_TEST_CERT"`.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#5)]  
  
6. <span data-ttu-id="6692c-127">Chiudere l'archivio dopo l'individuazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="6692c-127">Close the store after the certificate is located.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementX509#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#6)]  
  
7. <span data-ttu-id="6692c-128">Creare un oggetto <xref:System.Xml.XmlDocument> caricando un file XML dal disco.</span><span class="sxs-lookup"><span data-stu-id="6692c-128">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="6692c-129">L'oggetto <xref:System.Xml.XmlDocument> contiene l'elemento XML da crittografare.</span><span class="sxs-lookup"><span data-stu-id="6692c-129">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementX509#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#7)]  
  
8. <span data-ttu-id="6692c-130">Individuare l'elemento specificato nell'oggetto <xref:System.Xml.XmlDocument> e creare un nuovo oggetto <xref:System.Xml.XmlElement> per rappresentare l'elemento che si vuole crittografare.</span><span class="sxs-lookup"><span data-stu-id="6692c-130">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span>  <span data-ttu-id="6692c-131">In questo esempio l'elemento `"creditcard"` è crittografato.</span><span class="sxs-lookup"><span data-stu-id="6692c-131">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementX509#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#8)]  
  
9. <span data-ttu-id="6692c-132">Creare una nuova istanza della classe <xref:System.Security.Cryptography.Xml.EncryptedXml> e usarla per crittografare l'elemento specificato mediante il certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="6692c-132">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the specified element using the X.509 certificate.</span></span>  <span data-ttu-id="6692c-133">Il metodo <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> restituisce l'elemento crittografato come un oggetto <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="6692c-133">The <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method returns the encrypted element as an <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementX509#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#9)]  
  
10. <span data-ttu-id="6692c-134">Sostituire l'elemento dall'oggetto <xref:System.Xml.XmlDocument> originale con l'elemento <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="6692c-134">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementX509#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#10)]  
  
11. <span data-ttu-id="6692c-135">Salvare l'oggetto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="6692c-135">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementX509#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="6692c-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="6692c-136">Example</span></span>  
 <span data-ttu-id="6692c-137">Questo esempio presuppone che sia presente un file denominato `"test.xml"` nella stessa directory del programma compilato</span><span class="sxs-lookup"><span data-stu-id="6692c-137">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="6692c-138">e che `"test.xml"` contenga un elemento `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="6692c-138">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="6692c-139">È possibile inserire il codice XML seguente in un file denominato `test.xml` e usarlo con questo esempio.</span><span class="sxs-lookup"><span data-stu-id="6692c-139">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6692c-140">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="6692c-140">Compiling the Code</span></span>  
  
- <span data-ttu-id="6692c-141">Per compilare questo esempio, è necessario includere un riferimento a `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="6692c-141">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="6692c-142">Includere gli spazi dei nomi seguenti: <xref:System.Xml>, <xref:System.Security.Cryptography> e <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="6692c-142">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6692c-143">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6692c-143">.NET Framework Security</span></span>  
 <span data-ttu-id="6692c-144">Il certificato X.509 usato in questo esempio è solo a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="6692c-144">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="6692c-145">Le applicazioni devono usare un certificato X.509 generato da un'autorità di certificazione attendibile o usare un certificato generato dal server di certificazione Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="6692c-145">Applications should use an X.509 certificate generated by a trusted certificate authority or use a certificate generated by the Microsoft Windows Certificate Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6692c-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6692c-146">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="6692c-147">Procedura: decrittografare gli elementi XML con certificati X.509</span><span class="sxs-lookup"><span data-stu-id="6692c-147">How to: Decrypt XML Elements with X.509 Certificates</span></span>](how-to-decrypt-xml-elements-with-x-509-certificates.md)

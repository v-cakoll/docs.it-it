---
title: 'Procedura: Decrittografare gli elementi XML con certificati X.509'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- decryption
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: bd015722-d88d-408d-8ca8-e4e475c441ed
ms.openlocfilehash: 46fbefbf7a427ec0d60a34ecc2166f8499d08575
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708888"
---
# <a name="how-to-decrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="d0e83-102">Procedura: Decrittografare gli elementi XML con certificati X.509</span><span class="sxs-lookup"><span data-stu-id="d0e83-102">How to: Decrypt XML Elements with X.509 Certificates</span></span>
<span data-ttu-id="d0e83-103">È possibile usare le classi dello spazio dei nomi <xref:System.Security.Cryptography.Xml> per crittografare e decrittografare un elemento all'interno di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="d0e83-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="d0e83-104">La crittografia XML consente di scambiare o archiviare dati XML crittografati in modo standard, garantendo un'adeguata protezione dei dati da letture non autorizzate.</span><span class="sxs-lookup"><span data-stu-id="d0e83-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="d0e83-105">Per ulteriori informazioni sullo standard di crittografia XML, vedere la specifica World Wide Web Consortium (W3C) per la crittografia XML disponibile in <https://www.w3.org/TR/xmldsig-core/>.</span><span class="sxs-lookup"><span data-stu-id="d0e83-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="d0e83-106">Questo esempio decrittografa un elemento XML crittografato usando i metodi descritti in [procedura: crittografare gli elementi XML con certificati X. 509](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="d0e83-106">This example decrypts an XML element that was encrypted using the methods described in: [How to: Encrypt XML Elements with X.509 Certificates](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md).</span></span>  <span data-ttu-id="d0e83-107">Trova un elemento <`EncryptedData`>, decrittografa l'elemento e quindi sostituisce l'elemento con l'elemento XML originale in testo non crittografato.</span><span class="sxs-lookup"><span data-stu-id="d0e83-107">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
 <span data-ttu-id="d0e83-108">L'esempio di codice in questa procedura decrittografa un elemento XML usando un certificato X.509 dall'archivio certificati locale dell'account utente corrente.</span><span class="sxs-lookup"><span data-stu-id="d0e83-108">The code example in this procedure decrypts an XML element using an X.509 certificate from the local certificate store of the current user account.</span></span>  <span data-ttu-id="d0e83-109">Nell'esempio viene utilizzato il metodo <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> per recuperare automaticamente il certificato X. 509 e decrittografare una chiave di sessione archiviata nell'elemento <`EncryptedKey`> dell'elemento <`EncryptedData`>.</span><span class="sxs-lookup"><span data-stu-id="d0e83-109">The example uses the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to automatically retrieve the X.509 certificate and decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="d0e83-110">Il metodo <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> usa quindi automaticamente la chiave della sessione per decrittografare l'elemento XML.</span><span class="sxs-lookup"><span data-stu-id="d0e83-110">The <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method then automatically uses the session key to decrypt the XML element.</span></span>  
  
 <span data-ttu-id="d0e83-111">Questo esempio è adatto per situazioni in cui più applicazioni devono condividere dati crittografati o in cui un'applicazione deve salvare dati crittografati tra un'esecuzione e l'altra.</span><span class="sxs-lookup"><span data-stu-id="d0e83-111">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="d0e83-112">Per decrittografare un elemento XML con un certificato X.509</span><span class="sxs-lookup"><span data-stu-id="d0e83-112">To decrypt an XML element with an X.509 certificate</span></span>  
  
1. <span data-ttu-id="d0e83-113">Creare un oggetto <xref:System.Xml.XmlDocument> caricando un file XML dal disco.</span><span class="sxs-lookup"><span data-stu-id="d0e83-113">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="d0e83-114">L'oggetto <xref:System.Xml.XmlDocument> contiene l'elemento XML da decrittografare.</span><span class="sxs-lookup"><span data-stu-id="d0e83-114">The <xref:System.Xml.XmlDocument> object contains the XML element to decrypt.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#2)]  
  
2. <span data-ttu-id="d0e83-115">Creare un nuovo oggetto <xref:System.Security.Cryptography.Xml.EncryptedXml> passando l'oggetto <xref:System.Xml.XmlDocument> al costruttore.</span><span class="sxs-lookup"><span data-stu-id="d0e83-115">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object by passing the <xref:System.Xml.XmlDocument> object to the constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#3)]  
  
3. <span data-ttu-id="d0e83-116">Decrittografare il documento XML usando il metodo <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>.</span><span class="sxs-lookup"><span data-stu-id="d0e83-116">Decrypt the XML document using the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToDecryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#4)]  
  
4. <span data-ttu-id="d0e83-117">Salvare l'oggetto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="d0e83-117">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="d0e83-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0e83-118">Example</span></span>  
 <span data-ttu-id="d0e83-119">Questo esempio presuppone che sia presente un file denominato `"test.xml"` nella stessa directory del programma compilato</span><span class="sxs-lookup"><span data-stu-id="d0e83-119">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="d0e83-120">e che `"test.xml"` contenga un elemento `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="d0e83-120">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="d0e83-121">È possibile inserire il codice XML seguente in un file denominato `test.xml` e usarlo con questo esempio.</span><span class="sxs-lookup"><span data-stu-id="d0e83-121">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToDecryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d0e83-122">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d0e83-122">Compiling the Code</span></span>  
  
- <span data-ttu-id="d0e83-123">Per compilare questo esempio, è necessario includere un riferimento a `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="d0e83-123">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="d0e83-124">Includere gli spazi dei nomi seguenti: <xref:System.Xml>, <xref:System.Security.Cryptography> e <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="d0e83-124">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d0e83-125">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d0e83-125">.NET Framework Security</span></span>  
 <span data-ttu-id="d0e83-126">Il certificato X.509 usato in questo esempio è solo a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="d0e83-126">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="d0e83-127">Le applicazioni devono usare un certificato X.509 generato da un'autorità di certificazione attendibile o usare un certificato generato dal server di certificazione Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="d0e83-127">Applications should use an X.509 certificate generated by a trusted certificate authority or use a certificate generated by the Microsoft Windows Certificate Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0e83-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0e83-128">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="d0e83-129">Procedura: Crittografare gli elementi XML con certificati X.509</span><span class="sxs-lookup"><span data-stu-id="d0e83-129">How to: Encrypt XML Elements with X.509 Certificates</span></span>](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md)

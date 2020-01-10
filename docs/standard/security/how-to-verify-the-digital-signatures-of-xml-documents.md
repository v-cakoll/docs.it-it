---
title: 'Procedura: Verificare le firme digitali dei documenti XML'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.SignedXml class
- signatures, cryptographic
- System.Security.Cryptography.RSACryptoServiceProvider class
- verifying signatures
- checking signatures
- XML digital signatures
- digital signatures, verifying
ms.assetid: a4d5ceb1-b9f5-47e8-9e4a-a2b39110002f
ms.openlocfilehash: 5d562c23d3b0fd7eda5dc273932ada77709641a1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706006"
---
# <a name="how-to-verify-the-digital-signatures-of-xml-documents"></a><span data-ttu-id="ab974-102">Procedura: Verificare le firme digitali dei documenti XML</span><span class="sxs-lookup"><span data-stu-id="ab974-102">How to: Verify the Digital Signatures of XML Documents</span></span>
<span data-ttu-id="ab974-103">È possibile usare le classi nello spazio dei nomi <xref:System.Security.Cryptography.Xml> per verificare i dati XML firmati con una firma digitale.</span><span class="sxs-lookup"><span data-stu-id="ab974-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to verify XML data signed with a digital signature.</span></span> <span data-ttu-id="ab974-104">Le firme digitali XML (XMLDSIG) consentono di verificare che i dati non siano stati alterati dopo la firma.</span><span class="sxs-lookup"><span data-stu-id="ab974-104">XML digital signatures (XMLDSIG) allow you to verify that data was not altered after it was signed.</span></span> <span data-ttu-id="ab974-105">Per ulteriori informazioni sullo standard XMLDSIG, vedere la specifica World Wide Web Consortium (W3C) in <https://www.w3.org/TR/xmldsig-core/>.</span><span class="sxs-lookup"><span data-stu-id="ab974-105">For more information about the XMLDSIG standard, see the World Wide Web Consortium (W3C) specification at <https://www.w3.org/TR/xmldsig-core/>.</span></span>
  
 <span data-ttu-id="ab974-106">Nell'esempio di codice di questa procedura viene illustrato come verificare una firma digitale XML contenuta in un elemento <`Signature`>.</span><span class="sxs-lookup"><span data-stu-id="ab974-106">The code example in this procedure demonstrates how to verify an XML digital signature contained in a <`Signature`> element.</span></span>  <span data-ttu-id="ab974-107">L'esempio recupera una chiave pubblica RSA da un contenitore di chiavi, quindi usa la chiave per verificare la firma.</span><span class="sxs-lookup"><span data-stu-id="ab974-107">The example retrieves an RSA public key from a key container and then uses the key to verify the signature.</span></span>  
  
 <span data-ttu-id="ab974-108">Per informazioni su come creare una firma digitale che può essere verificata usando questa tecnica, vedere [procedura: firmare documenti XML con firme digitali](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="ab974-108">For information about how create a digital signature that can be verified using this technique, see [How to: Sign XML Documents with Digital Signatures](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
### <a name="to-verify-the-digital-signature-of-an-xml-document"></a><span data-ttu-id="ab974-109">Per verificare la firma digitale di un documento XML</span><span class="sxs-lookup"><span data-stu-id="ab974-109">To verify the digital signature of an XML document</span></span>  
  
1. <span data-ttu-id="ab974-110">Per verificare il documento, è necessario usare la stessa chiave asimmetrica usata per la firma.</span><span class="sxs-lookup"><span data-stu-id="ab974-110">To verify the document, you must use the same asymmetric key that was used for signing.</span></span>  <span data-ttu-id="ab974-111">Creare un oggetto <xref:System.Security.Cryptography.CspParameters> e specificare il nome del contenitore di chiavi usato per la firma.</span><span class="sxs-lookup"><span data-stu-id="ab974-111">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container that was used for signing.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#2)]  
  
2. <span data-ttu-id="ab974-112">Recuperare la chiave pubblica usando la classe <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="ab974-112">Retrieve the public key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="ab974-113">La chiave viene caricata automaticamente dal contenitore di chiavi in base al nome quando si passa l'oggetto <xref:System.Security.Cryptography.CspParameters> al costruttore della classe <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="ab974-113">The key is automatically loaded from the key container by name when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#3)]  
  
3. <span data-ttu-id="ab974-114">Creare un oggetto <xref:System.Xml.XmlDocument> caricando un file XML dal disco.</span><span class="sxs-lookup"><span data-stu-id="ab974-114">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="ab974-115">L'oggetto <xref:System.Xml.XmlDocument> contiene il documento XML firmato da verificare.</span><span class="sxs-lookup"><span data-stu-id="ab974-115">The <xref:System.Xml.XmlDocument> object contains the signed XML document to verify.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#4)]  
  
4. <span data-ttu-id="ab974-116">Creare un nuovo oggetto <xref:System.Security.Cryptography.Xml.SignedXml> e passare a esso l'oggetto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="ab974-116">Create a new <xref:System.Security.Cryptography.Xml.SignedXml> object and pass the <xref:System.Xml.XmlDocument> object to it.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#5)]  
  
5. <span data-ttu-id="ab974-117">Trovare l'elemento <`signature`> e creare un nuovo oggetto <xref:System.Xml.XmlNodeList>.</span><span class="sxs-lookup"><span data-stu-id="ab974-117">Find the <`signature`> element and create a new <xref:System.Xml.XmlNodeList> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#6)]  
  
6. <span data-ttu-id="ab974-118">Caricare il codice XML del primo <`signature`elemento > nell'oggetto <xref:System.Security.Cryptography.Xml.SignedXml>.</span><span class="sxs-lookup"><span data-stu-id="ab974-118">Load the XML of the first <`signature`> element into the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#7)]  
  
7. <span data-ttu-id="ab974-119">Controllare la firma usando il metodo <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> e la chiave pubblica RSA.</span><span class="sxs-lookup"><span data-stu-id="ab974-119">Check the signature using the <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> method and the RSA public key.</span></span>  <span data-ttu-id="ab974-120">Il metodo restituisce un valore booleano che indica l'esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="ab974-120">This method returns a Boolean value that indicates success or failure.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="ab974-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="ab974-121">Example</span></span>  
 <span data-ttu-id="ab974-122">Questo esempio presuppone che sia presente un file denominato `"test.xml"` nella stessa directory del programma compilato</span><span class="sxs-lookup"><span data-stu-id="ab974-122">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="ab974-123">Il file di `"test.xml"` deve essere firmato usando le tecniche descritte in [procedura: firmare documenti XML con firme digitali](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="ab974-123">The `"test.xml"` file must be signed using the techniques described in [How to: Sign XML Documents with Digital Signatures](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
 [!code-csharp[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ab974-124">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ab974-124">Compiling the Code</span></span>  
  
- <span data-ttu-id="ab974-125">Per compilare questo esempio, è necessario includere un riferimento a `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="ab974-125">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="ab974-126">Includere gli spazi dei nomi seguenti: <xref:System.Xml>, <xref:System.Security.Cryptography> e <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="ab974-126">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ab974-127">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ab974-127">.NET Framework Security</span></span>  
 <span data-ttu-id="ab974-128">Non archiviare né trasferire mai in testo non crittografato la chiave privata di una coppia di chiavi asimmetriche.</span><span class="sxs-lookup"><span data-stu-id="ab974-128">Never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="ab974-129">Per ulteriori informazioni sulle chiavi crittografiche simmetriche e asimmetriche, vedere [generazione di chiavi per crittografia e decrittografia](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="ab974-129">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="ab974-130">Non incorporare mai una chiave privata direttamente nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="ab974-130">Never embed a private key directly into your source code.</span></span>  <span data-ttu-id="ab974-131">Le chiavi incorporate possono essere lette facilmente da un assembly tramite [Ildasm. exe (DISASSEMBLER il)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) oppure aprendo l'assembly in un editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="ab974-131">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab974-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab974-132">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="ab974-133">Procedura: Firmare documenti XML con firme digitali</span><span class="sxs-lookup"><span data-stu-id="ab974-133">How to: Sign XML Documents with Digital Signatures</span></span>](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md)

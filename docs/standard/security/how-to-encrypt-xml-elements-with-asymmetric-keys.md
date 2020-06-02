---
title: 'Procedura: crittografare gli elementi XML con chiavi asimmetriche'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET Framework], asymmetric keys
- AES algorithm
- System.Security.Cryptography.RSACryptoServiceProvider class
- asymmetric keys [.NET Framework]
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- key containers
- Advanced Encryption Standard algorithm
- Rijndael
- encryption [.NET Framework], asymmetric keys
ms.assetid: a164ba4f-e596-4bbe-a9ca-f214fe89ed48
ms.openlocfilehash: 475446f6206676e93ea72d16e01bcf1067c24e86
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277375"
---
# <a name="how-to-encrypt-xml-elements-with-asymmetric-keys"></a><span data-ttu-id="60ccd-102">Procedura: crittografare gli elementi XML con chiavi asimmetriche</span><span class="sxs-lookup"><span data-stu-id="60ccd-102">How to: Encrypt XML Elements with Asymmetric Keys</span></span>
<span data-ttu-id="60ccd-103">È possibile usare le classi dello spazio dei nomi <xref:System.Security.Cryptography.Xml> per crittografare un elemento all'interno di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="60ccd-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="60ccd-104">La crittografia XML consente di scambiare o archiviare dati XML crittografati in modo standard, garantendo un'adeguata protezione dei dati da letture non autorizzate.</span><span class="sxs-lookup"><span data-stu-id="60ccd-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="60ccd-105">Per ulteriori informazioni sullo standard di crittografia XML, vedere la specifica World Wide Web Consortium (W3C) per la crittografia XML disponibile all'indirizzo <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="60ccd-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="60ccd-106">È possibile usare la crittografia XML per sostituire qualsiasi elemento o documento XML con un elemento <`EncryptedData`> contenente i dati XML crittografati.</span><span class="sxs-lookup"><span data-stu-id="60ccd-106">You can use XML Encryption to replace any XML element or document with an <`EncryptedData`> element that contains the encrypted XML data.</span></span>  <span data-ttu-id="60ccd-107">L' `EncryptedData` elemento <> può inoltre contenere sottoelementi che includono informazioni sulle chiavi e sui processi utilizzati durante la crittografia.</span><span class="sxs-lookup"><span data-stu-id="60ccd-107">The <`EncryptedData`> element can also contain sub elements that include information about the keys and processes used during encryption.</span></span>  <span data-ttu-id="60ccd-108">La crittografia XML consente a un documento di contenere più elementi crittografati e consente a un elemento di essere crittografato più volte.</span><span class="sxs-lookup"><span data-stu-id="60ccd-108">XML Encryption allows a document to contain multiple encrypted elements and allows an element to be encrypted multiple times.</span></span>  <span data-ttu-id="60ccd-109">Nell'esempio di codice riportato in questa procedura viene illustrato come creare un <`EncryptedData`> elemento insieme a diversi altri sottoelementi che è possibile utilizzare in seguito durante la decrittografia.</span><span class="sxs-lookup"><span data-stu-id="60ccd-109">The code example in this procedure shows how to create an <`EncryptedData`> element along with several other sub elements that you can use later during decryption.</span></span>  
  
 <span data-ttu-id="60ccd-110">Questo esempio crittografa un elemento XML mediante due chiavi.</span><span class="sxs-lookup"><span data-stu-id="60ccd-110">This example encrypts an XML element using two keys.</span></span>  <span data-ttu-id="60ccd-111">L'esempio genera una coppia di chiavi pubblica/privata RSA e salva la coppia di chiavi in un contenitore di chiavi protetto.</span><span class="sxs-lookup"><span data-stu-id="60ccd-111">It generates an RSA public/private key pair and saves the key pair to a secure key container.</span></span>  <span data-ttu-id="60ccd-112">L'esempio crea quindi una chiave di sessione separata usando l'algoritmo AES (Advanced Encryption Standard), definito anche algoritmo Rijndael.</span><span class="sxs-lookup"><span data-stu-id="60ccd-112">The example then creates a separate session key using the Advanced Encryption Standard (AES) algorithm, also called the Rijndael algorithm.</span></span>  <span data-ttu-id="60ccd-113">La chiave di sessione AES viene usata dall'esempio per crittografare il documento XML e la chiave pubblica RSA viene usata per crittografare la chiave di sessione AES.</span><span class="sxs-lookup"><span data-stu-id="60ccd-113">The example uses the AES session key to encrypt the XML document and then uses the RSA public key to encrypt the AES session key.</span></span>  <span data-ttu-id="60ccd-114">Infine, l'esempio salva la chiave della sessione AES crittografata e i dati XML crittografati nel documento XML all'interno di un nuovo `EncryptedData` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="60ccd-114">Finally, the example saves the encrypted AES session key and the encrypted XML data to the XML document within a new <`EncryptedData`> element.</span></span>  
  
 <span data-ttu-id="60ccd-115">Per decrittografare l'elemento XML, recuperare la chiave privata RSA dal contenitore di chiavi, usarla per decrittografare la chiave di sessione e quindi usare la chiave di sessione per decrittografare il documento.</span><span class="sxs-lookup"><span data-stu-id="60ccd-115">To decrypt the XML element, you retrieve the RSA private key from the key container, use it to decrypt the session key, and then use the session key to decrypt the document.</span></span>  <span data-ttu-id="60ccd-116">Per ulteriori informazioni su come decrittografare un elemento XML crittografato mediante questa procedura, vedere [procedura: decrittografare gli elementi XML con chiavi asimmetriche](how-to-decrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="60ccd-116">For more information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with Asymmetric Keys](how-to-decrypt-xml-elements-with-asymmetric-keys.md).</span></span>  
  
 <span data-ttu-id="60ccd-117">Questo esempio è adatto per situazioni in cui più applicazioni devono condividere dati crittografati o in cui un'applicazione deve salvare dati crittografati tra un'esecuzione e l'altra.</span><span class="sxs-lookup"><span data-stu-id="60ccd-117">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-an-asymmetric-key"></a><span data-ttu-id="60ccd-118">Per crittografare un elemento XML con una chiave asimmetrica</span><span class="sxs-lookup"><span data-stu-id="60ccd-118">To encrypt an XML element with an asymmetric key</span></span>  
  
1. <span data-ttu-id="60ccd-119">Creare un oggetto <xref:System.Security.Cryptography.CspParameters> e specificare il nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="60ccd-119">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="60ccd-120">Generare una chiave simmetrica usando la classe <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="60ccd-120">Generate a symmetric key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="60ccd-121">La chiave viene salvata automaticamente nel contenitore di chiavi quando si passa l'oggetto <xref:System.Security.Cryptography.CspParameters> al costruttore della classe <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="60ccd-121">The key is automatically saved to the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="60ccd-122">Questa chiave verrà usata per crittografare la chiave di sessione AES e può essere recuperata in un secondo momento per decrittografarla.</span><span class="sxs-lookup"><span data-stu-id="60ccd-122">This key will be used to encrypt the AES session key and can be retrieved later to decrypt it.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="60ccd-123">Creare un oggetto <xref:System.Xml.XmlDocument> caricando un file XML dal disco.</span><span class="sxs-lookup"><span data-stu-id="60ccd-123">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="60ccd-124">L'oggetto <xref:System.Xml.XmlDocument> contiene l'elemento XML da crittografare.</span><span class="sxs-lookup"><span data-stu-id="60ccd-124">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#4)]  
  
4. <span data-ttu-id="60ccd-125">Individuare l'elemento specificato nell'oggetto <xref:System.Xml.XmlDocument> e creare un nuovo oggetto <xref:System.Xml.XmlElement> per rappresentare l'elemento che si vuole crittografare.</span><span class="sxs-lookup"><span data-stu-id="60ccd-125">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span> <span data-ttu-id="60ccd-126">In questo esempio l'elemento `"creditcard"` è crittografato.</span><span class="sxs-lookup"><span data-stu-id="60ccd-126">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
5. <span data-ttu-id="60ccd-127">Creare una nuova chiave di sessione usando la classe <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="60ccd-127">Create a new session key using the <xref:System.Security.Cryptography.RijndaelManaged> class.</span></span>  <span data-ttu-id="60ccd-128">Questa chiave crittograferà l'elemento XML e quindi verrà crittografata a sua volta e inserita nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="60ccd-128">This key will encrypt the XML element, and then be encrypted itself and placed in the XML document.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
6. <span data-ttu-id="60ccd-129">Creare una nuova istanza della classe <xref:System.Security.Cryptography.Xml.EncryptedXml> e usarla per crittografare l'elemento specificato mediante la chiave di sessione.</span><span class="sxs-lookup"><span data-stu-id="60ccd-129">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the specified element using the session key.</span></span>  <span data-ttu-id="60ccd-130">Il metodo <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> restituisce l'elemento crittografato come una matrice di byte crittografati.</span><span class="sxs-lookup"><span data-stu-id="60ccd-130">The <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> method returns the encrypted element as an array of encrypted bytes.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
7. <span data-ttu-id="60ccd-131">Costruire un oggetto <xref:System.Security.Cryptography.Xml.EncryptedData> e popolarlo con l'identificatore dell'URL dell'elemento XML crittografato.</span><span class="sxs-lookup"><span data-stu-id="60ccd-131">Construct an <xref:System.Security.Cryptography.Xml.EncryptedData> object and populate it with the URL identifier of the encrypted XML element.</span></span>  <span data-ttu-id="60ccd-132">Questo identificatore dell'URL comunica a chi esegue la decrittografia che l'elemento XML contiene un elemento crittografato.</span><span class="sxs-lookup"><span data-stu-id="60ccd-132">This URL identifier lets a decrypting party know that the XML contains an encrypted element.</span></span>  <span data-ttu-id="60ccd-133">È possibile usare il campo <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl> per specificare l'identificatore dell'URL.</span><span class="sxs-lookup"><span data-stu-id="60ccd-133">You can use the <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl> field to specify the URL identifier.</span></span>  <span data-ttu-id="60ccd-134">L'elemento XML di testo non crittografato verrà sostituito da un <`EncryptedData` elemento> incapsulato da questo <xref:System.Security.Cryptography.Xml.EncryptedData> oggetto.</span><span class="sxs-lookup"><span data-stu-id="60ccd-134">The plaintext XML element will be replaced by an <`EncryptedData`> element encapsulated by this <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
8. <span data-ttu-id="60ccd-135">Creare un oggetto <xref:System.Security.Cryptography.Xml.EncryptionMethod> inizializzato sull'identificatore dell'URL dell'algoritmo di crittografia usato per generare la chiave di sessione.</span><span class="sxs-lookup"><span data-stu-id="60ccd-135">Create an <xref:System.Security.Cryptography.Xml.EncryptionMethod> object that is initialized to the URL identifier of the cryptographic algorithm used to generate the session key.</span></span>  <span data-ttu-id="60ccd-136">Passare l'oggetto <xref:System.Security.Cryptography.Xml.EncryptionMethod> alla proprietà <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A>.</span><span class="sxs-lookup"><span data-stu-id="60ccd-136">Pass the <xref:System.Security.Cryptography.Xml.EncryptionMethod> object to the <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A> property.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#9)]  
  
9. <span data-ttu-id="60ccd-137">Creare un oggetto <xref:System.Security.Cryptography.Xml.EncryptedKey> in cui includere la chiave di sessione crittografata.</span><span class="sxs-lookup"><span data-stu-id="60ccd-137">Create an <xref:System.Security.Cryptography.Xml.EncryptedKey> object to contain the encrypted session key.</span></span>  <span data-ttu-id="60ccd-138">Crittografare la chiave di sessione, aggiungerla all'oggetto <xref:System.Security.Cryptography.Xml.EncryptedKey> e immettere un nome di chiave di sessione e l'URL dell'identificatore della chiave.</span><span class="sxs-lookup"><span data-stu-id="60ccd-138">Encrypt the session key, add it to the <xref:System.Security.Cryptography.Xml.EncryptedKey> object, and enter a session key name and key identifier URL.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#10)]  
  
10. <span data-ttu-id="60ccd-139">Creare un nuovo oggetto <xref:System.Security.Cryptography.Xml.DataReference> che esegue il mapping dei dati crittografati a una chiave di sessione specifica.</span><span class="sxs-lookup"><span data-stu-id="60ccd-139">Create a new <xref:System.Security.Cryptography.Xml.DataReference> object that maps the encrypted data to a particular session key.</span></span>  <span data-ttu-id="60ccd-140">Questo passaggio facoltativo permette di specificare con facilità che più parti di un documento XML sono state crittografate da una singola chiave.</span><span class="sxs-lookup"><span data-stu-id="60ccd-140">This optional step allows you to easily specify that multiple parts of an XML document were encrypted by a single key.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#11)]  
  
11. <span data-ttu-id="60ccd-141">Aggiungere la chiave crittografata all'oggetto <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="60ccd-141">Add the encrypted key to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#12)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#12)]  
  
12. <span data-ttu-id="60ccd-142">Creare un nuovo oggetto <xref:System.Security.Cryptography.Xml.KeyInfo> per specificare il nome della chiave RSA.</span><span class="sxs-lookup"><span data-stu-id="60ccd-142">Create a new <xref:System.Security.Cryptography.Xml.KeyInfo> object to specify the name of the RSA key.</span></span>  <span data-ttu-id="60ccd-143">Aggiungerlo all'oggetto <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="60ccd-143">Add it to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span> <span data-ttu-id="60ccd-144">Ciò permette a chi esegue la crittografia di identificare la chiave asimmetrica corretta da usare per decrittografare la chiave di sessione.</span><span class="sxs-lookup"><span data-stu-id="60ccd-144">This helps the decrypting party identify the correct asymmetric key to use when decrypting the session key.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#13)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#13)]  
  
13. <span data-ttu-id="60ccd-145">Aggiungere i dati dell'elemento crittografato all'oggetto <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="60ccd-145">Add the encrypted element data to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#14](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#14)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#14)]  
  
14. <span data-ttu-id="60ccd-146">Sostituire l'elemento dall'oggetto <xref:System.Xml.XmlDocument> originale con l'elemento <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="60ccd-146">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#15](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#15)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#15)]  
  
15. <span data-ttu-id="60ccd-147">Salvare l'oggetto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="60ccd-147">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#16](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#16)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#16)]  
  
## <a name="example"></a><span data-ttu-id="60ccd-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="60ccd-148">Example</span></span>  
 <span data-ttu-id="60ccd-149">Questo esempio presuppone che sia presente un file denominato `"test.xml"` nella stessa directory del programma compilato</span><span class="sxs-lookup"><span data-stu-id="60ccd-149">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="60ccd-150">e che `"test.xml"` contenga un elemento `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="60ccd-150">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="60ccd-151">È possibile inserire il codice XML seguente in un file denominato `test.xml` e usarlo con questo esempio.</span><span class="sxs-lookup"><span data-stu-id="60ccd-151">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="60ccd-152">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="60ccd-152">Compiling the Code</span></span>  
  
- <span data-ttu-id="60ccd-153">Per compilare questo esempio, è necessario includere un riferimento a `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="60ccd-153">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="60ccd-154">Includere gli spazi dei nomi seguenti: <xref:System.Xml>, <xref:System.Security.Cryptography> e <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="60ccd-154">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="60ccd-155">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="60ccd-155">.NET Framework Security</span></span>  
 <span data-ttu-id="60ccd-156">Non archiviare mai una chiave crittografica in testo non crittografato e non trasferire mai in testo non crittografato una chiave simmetrica tra computer.</span><span class="sxs-lookup"><span data-stu-id="60ccd-156">Never store a symmetric cryptographic key in plaintext or transfer a symmetric key between machines in plaintext.</span></span>  <span data-ttu-id="60ccd-157">Non archiviare né trasferire mai in testo non crittografato, inoltre, la chiave privata di una coppia di chiavi asimmetriche.</span><span class="sxs-lookup"><span data-stu-id="60ccd-157">Additionally, never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="60ccd-158">Per ulteriori informazioni sulle chiavi crittografiche simmetriche e asimmetriche, vedere [generazione di chiavi per crittografia e decrittografia](generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="60ccd-158">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="60ccd-159">Non incorporare mai una chiave direttamente nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="60ccd-159">Never embed a key directly into your source code.</span></span>  <span data-ttu-id="60ccd-160">Le chiavi incorporate possono essere lette facilmente da un assembly tramite [Ildasm. exe (DISASSEMBLER il)](../../framework/tools/ildasm-exe-il-disassembler.md) oppure aprendo l'assembly in un editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="60ccd-160">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
 <span data-ttu-id="60ccd-161">Dopo avere usato una chiave crittografica, cancellarla dalla memoria impostando ogni byte su zero oppure chiamando il metodo <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> della classe di crittografia gestita.</span><span class="sxs-lookup"><span data-stu-id="60ccd-161">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  <span data-ttu-id="60ccd-162">Le chiavi crittografiche possono essere a volte lette dalla memoria da un debugger oppure possono essere lette da un disco rigido, se viene eseguito il paging su disco della posizione di memoria.</span><span class="sxs-lookup"><span data-stu-id="60ccd-162">Cryptographic keys can sometimes be read from memory by a debugger or read from a hard drive if the memory location is paged to disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60ccd-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60ccd-163">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="60ccd-164">Procedura: decrittografare gli elementi XML con chiavi asimmetriche</span><span class="sxs-lookup"><span data-stu-id="60ccd-164">How to: Decrypt XML Elements with Asymmetric Keys</span></span>](how-to-decrypt-xml-elements-with-asymmetric-keys.md)

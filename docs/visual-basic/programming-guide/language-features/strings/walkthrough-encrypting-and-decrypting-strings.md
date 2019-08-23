---
title: Crittografia e decrittografia di stringhe in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: ee8691fedb537d1aa588eaac61624b445da64d1f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944422"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="2224b-102">Procedura dettagliata: Crittografia e decrittografia di stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2224b-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="2224b-103">Questa procedura dettagliata illustra come usare la <xref:System.Security.Cryptography.DESCryptoServiceProvider> classe per crittografare e decrittografare le stringhe usando la versione del provider del servizio di crittografia (CSP) dell'algoritmo Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>).</span><span class="sxs-lookup"><span data-stu-id="2224b-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="2224b-104">Il primo passaggio consiste nel creare una semplice classe wrapper che incapsula l'algoritmo 3DES e archivia i dati crittografati come stringa con codifica base 64.</span><span class="sxs-lookup"><span data-stu-id="2224b-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="2224b-105">Il wrapper viene quindi usato per archiviare in modo sicuro i dati utente privati in un file di testo accessibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="2224b-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="2224b-106">È possibile usare la crittografia per proteggere i segreti utente, ad esempio le password, e rendere illeggibili le credenziali da parte di utenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="2224b-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="2224b-107">Ciò può impedire che l'identità di un utente autorizzato venga rubata, che protegge le risorse dell'utente e fornisce il non ripudio.</span><span class="sxs-lookup"><span data-stu-id="2224b-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="2224b-108">La crittografia consente inoltre di proteggere i dati di un utente dall'accesso da parte di utenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="2224b-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="2224b-109">Per altre informazioni, vedere [Servizi di crittografia](../../../../standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="2224b-109">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2224b-110">Gli algoritmi Rijndael (ora definiti Advanced Encryption Standard [AES]) e triple Data Encryption Standard (3DES) forniscono una maggiore sicurezza rispetto a DES perché sono più impegnati a livello di calcolo.</span><span class="sxs-lookup"><span data-stu-id="2224b-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="2224b-111">Per altre informazioni, vedere <xref:System.Security.Cryptography.DES> e <xref:System.Security.Cryptography.Rijndael>.</span><span class="sxs-lookup"><span data-stu-id="2224b-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="2224b-112">Per creare il wrapper di crittografia</span><span class="sxs-lookup"><span data-stu-id="2224b-112">To create the encryption wrapper</span></span>  
  
1. <span data-ttu-id="2224b-113">Creare la `Simple3Des` classe per incapsulare i metodi di crittografia e decrittografia.</span><span class="sxs-lookup"><span data-stu-id="2224b-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2. <span data-ttu-id="2224b-114">Aggiungere un'importazione dello spazio dei nomi Cryptography all'inizio del file che contiene la `Simple3Des` classe.</span><span class="sxs-lookup"><span data-stu-id="2224b-114">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3. <span data-ttu-id="2224b-115">`Simple3Des` Nella classe aggiungere un campo privato per archiviare il provider del servizio di crittografia 3DES.</span><span class="sxs-lookup"><span data-stu-id="2224b-115">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4. <span data-ttu-id="2224b-116">Aggiungere un metodo privato che crea una matrice di byte di una lunghezza specificata dall'hash della chiave specificata.</span><span class="sxs-lookup"><span data-stu-id="2224b-116">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5. <span data-ttu-id="2224b-117">Aggiungere un costruttore per inizializzare il provider del servizio di crittografia 3DES.</span><span class="sxs-lookup"><span data-stu-id="2224b-117">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="2224b-118">Il `key` parametro controlla i `EncryptData` metodi `DecryptData` e.</span><span class="sxs-lookup"><span data-stu-id="2224b-118">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6. <span data-ttu-id="2224b-119">Aggiungere un metodo pubblico per la crittografia di una stringa.</span><span class="sxs-lookup"><span data-stu-id="2224b-119">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7. <span data-ttu-id="2224b-120">Aggiungere un metodo pubblico per la decrittografia di una stringa.</span><span class="sxs-lookup"><span data-stu-id="2224b-120">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     <span data-ttu-id="2224b-121">È ora possibile usare la classe wrapper per proteggere gli asset utente.</span><span class="sxs-lookup"><span data-stu-id="2224b-121">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="2224b-122">In questo esempio viene usato per archiviare in modo sicuro i dati utente privati in un file di testo accessibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="2224b-122">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="2224b-123">Per testare il wrapper di crittografia</span><span class="sxs-lookup"><span data-stu-id="2224b-123">To test the encryption wrapper</span></span>  
  
1. <span data-ttu-id="2224b-124">In una classe separata aggiungere un metodo che usa il `EncryptData` metodo del wrapper per crittografare una stringa e scriverla nella cartella documenti dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2224b-124">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2. <span data-ttu-id="2224b-125">Aggiungere un metodo che legga la stringa crittografata dalla cartella documenti dell'utente e decrittografa la stringa con il `DecryptData` metodo del wrapper.</span><span class="sxs-lookup"><span data-stu-id="2224b-125">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3. <span data-ttu-id="2224b-126">Aggiungere il codice dell'interfaccia utente per `TestEncoding` chiamare `TestDecoding` i metodi e.</span><span class="sxs-lookup"><span data-stu-id="2224b-126">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4. <span data-ttu-id="2224b-127">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2224b-127">Run the application.</span></span>  
  
     <span data-ttu-id="2224b-128">Quando si esegue il test dell'applicazione, si noti che i dati non vengono decrittografati se si specifica una password errata.</span><span class="sxs-lookup"><span data-stu-id="2224b-128">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2224b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2224b-129">See also</span></span>

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [<span data-ttu-id="2224b-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="2224b-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)

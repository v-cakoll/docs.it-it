---
title: La crittografia e decrittografia di stringhe in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: 96e56ab315a739fef9d5499b076a077f5294f39e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651223"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="0ad82-102">Procedura dettagliata: crittografia e decrittografia di stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0ad82-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="0ad82-103">Questa procedura dettagliata viene illustrato come utilizzare il <xref:System.Security.Cryptography.DESCryptoServiceProvider> classe per crittografare e decrittografare le stringhe utilizzando la versione del provider (CSP) del servizio di crittografia di Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algoritmo.</span><span class="sxs-lookup"><span data-stu-id="0ad82-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="0ad82-104">Il primo passaggio consiste nel creare una semplice classe wrapper che incapsula l'algoritmo 3DES e archivia i dati crittografati come stringa con codifica base 64.</span><span class="sxs-lookup"><span data-stu-id="0ad82-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="0ad82-105">Quindi, il wrapper viene utilizzato per archiviare i dati personali dell'utente in modo sicuro in un file di testo accessibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="0ad82-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="0ad82-106">È possibile utilizzare la crittografia per proteggere informazioni riservate dell'utente (ad esempio, le password) e per rendere illeggibile le credenziali di utenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="0ad82-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="0ad82-107">È possibile impedire identità di un utente autorizzato furto, che protegge le risorse dell'utente e consente di non ripudio.</span><span class="sxs-lookup"><span data-stu-id="0ad82-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="0ad82-108">Crittografia possa anche proteggere i dati di un utente dall'accesso di utenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="0ad82-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="0ad82-109">Per altre informazioni, vedere [Servizi di crittografia](../../../../standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="0ad82-109">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0ad82-110">Gli algoritmi Triple Data Encryption Standard (3DES) e il Rijndael (ora denominato Advanced Encryption Standard [AES) garantiscono maggiore sicurezza rispetto a DES, perché sono più complesse.</span><span class="sxs-lookup"><span data-stu-id="0ad82-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="0ad82-111">Per altre informazioni, vedere <xref:System.Security.Cryptography.DES> e <xref:System.Security.Cryptography.Rijndael>.</span><span class="sxs-lookup"><span data-stu-id="0ad82-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="0ad82-112">Per creare il wrapper di crittografia</span><span class="sxs-lookup"><span data-stu-id="0ad82-112">To create the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="0ad82-113">Creare la `Simple3Des` classe per incapsulare i metodi di crittografia e decrittografia.</span><span class="sxs-lookup"><span data-stu-id="0ad82-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  <span data-ttu-id="0ad82-114">Aggiungere un'importazione dello spazio dei nomi di crittografia all'inizio del file che contiene la `Simple3Des` classe.</span><span class="sxs-lookup"><span data-stu-id="0ad82-114">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  <span data-ttu-id="0ad82-115">Nel `Simple3Des` classe, aggiungere un campo privato per archiviare il provider del servizio di crittografia 3DES.</span><span class="sxs-lookup"><span data-stu-id="0ad82-115">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  <span data-ttu-id="0ad82-116">Aggiungere un metodo privato che crea una matrice di byte di lunghezza specificata dall'hash della chiave specificata.</span><span class="sxs-lookup"><span data-stu-id="0ad82-116">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  <span data-ttu-id="0ad82-117">Aggiungere un costruttore per inizializzare il provider del servizio di crittografia 3DES.</span><span class="sxs-lookup"><span data-stu-id="0ad82-117">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="0ad82-118">Il `key` parametro controlla il `EncryptData` e `DecryptData` metodi.</span><span class="sxs-lookup"><span data-stu-id="0ad82-118">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  <span data-ttu-id="0ad82-119">Aggiungere un metodo pubblico che crittografa una stringa.</span><span class="sxs-lookup"><span data-stu-id="0ad82-119">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  <span data-ttu-id="0ad82-120">Aggiungere un metodo pubblico che consente di decrittografare una stringa.</span><span class="sxs-lookup"><span data-stu-id="0ad82-120">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     <span data-ttu-id="0ad82-121">La classe wrapper ora utilizzabile per proteggere le risorse utente.</span><span class="sxs-lookup"><span data-stu-id="0ad82-121">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="0ad82-122">In questo esempio, è possibile archiviare in modo sicuro i dati personali dell'utente in un file di testo accessibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="0ad82-122">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="0ad82-123">Per testare il wrapper di crittografia</span><span class="sxs-lookup"><span data-stu-id="0ad82-123">To test the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="0ad82-124">In una classe separata, aggiungere un metodo che usa il wrapper `EncryptData` per crittografare una stringa e scriverlo all'utente della cartella documenti.</span><span class="sxs-lookup"><span data-stu-id="0ad82-124">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  <span data-ttu-id="0ad82-125">Aggiungere un metodo che legge la stringa crittografata da parte dell'utente della cartella documenti e consente di decrittografare la stringa con il wrapper `DecryptData` metodo.</span><span class="sxs-lookup"><span data-stu-id="0ad82-125">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  <span data-ttu-id="0ad82-126">Aggiungere il codice dell'interfaccia utente per chiamare il `TestEncoding` e `TestDecoding` metodi.</span><span class="sxs-lookup"><span data-stu-id="0ad82-126">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4.  <span data-ttu-id="0ad82-127">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0ad82-127">Run the application.</span></span>  
  
     <span data-ttu-id="0ad82-128">Quando si testa l'applicazione, si noti che non è possibile decrittografare i dati se si specifica la password errata.</span><span class="sxs-lookup"><span data-stu-id="0ad82-128">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad82-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ad82-129">See Also</span></span>  
 <xref:System.Security.Cryptography>  
 <xref:System.Security.Cryptography.DESCryptoServiceProvider>  
 <xref:System.Security.Cryptography.DES>  
 <xref:System.Security.Cryptography.TripleDES>  
 <xref:System.Security.Cryptography.Rijndael>  
 [<span data-ttu-id="0ad82-130">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="0ad82-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)

---
title: La crittografia e decrittografia di stringhe in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: aaf8238a330ceb9e1cf4f9ff5892d1db1d951faa
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826795"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="91b5b-102">Procedura dettagliata: La crittografia e decrittografia di stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="91b5b-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="91b5b-103">Questa procedura dettagliata illustra come usare il <xref:System.Security.Cryptography.DESCryptoServiceProvider> classe per crittografare e decrittografare le stringhe con la versione del provider (CSP) del servizio di crittografia di Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algoritmo.</span><span class="sxs-lookup"><span data-stu-id="91b5b-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="91b5b-104">Il primo passaggio consiste nel creare una semplice classe wrapper che incapsula l'algoritmo 3DES e archivia i dati crittografati come stringa con codifica base 64.</span><span class="sxs-lookup"><span data-stu-id="91b5b-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="91b5b-105">Quindi, il wrapper viene utilizzato per archiviare in modo sicuro i dati personali dell'utente in un file di testo accessibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="91b5b-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="91b5b-106">È possibile usare la crittografia per proteggere i segreti utente (ad esempio password) e per rendere le credenziali non leggibile dagli utenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="91b5b-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="91b5b-107">Questo può proteggere l'identità di un utente autorizzato prevenirne il furto, che protegge le risorse dell'utente e consente di non ripudio.</span><span class="sxs-lookup"><span data-stu-id="91b5b-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="91b5b-108">La crittografia può anche proteggere i dati di un utente nel caso in cui gli utenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="91b5b-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="91b5b-109">Per altre informazioni, vedere [Servizi di crittografia](../../../../standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="91b5b-109">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="91b5b-110">Gli algoritmi Triple Data Encryption Standard (3DES) e Rijndael (ora denominato Advanced Encryption Standard [AES) garantiscono maggiore sicurezza rispetto a DES perché sono molto più complesse.</span><span class="sxs-lookup"><span data-stu-id="91b5b-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="91b5b-111">Per altre informazioni, vedere <xref:System.Security.Cryptography.DES> e <xref:System.Security.Cryptography.Rijndael>.</span><span class="sxs-lookup"><span data-stu-id="91b5b-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="91b5b-112">Per creare il wrapper di crittografia</span><span class="sxs-lookup"><span data-stu-id="91b5b-112">To create the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="91b5b-113">Creare il `Simple3Des` classe per incapsulare i metodi di crittografia e decrittografia.</span><span class="sxs-lookup"><span data-stu-id="91b5b-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2.  <span data-ttu-id="91b5b-114">Aggiungere un'importazione dello spazio dei nomi cryptography all'inizio del file che contiene il `Simple3Des` classe.</span><span class="sxs-lookup"><span data-stu-id="91b5b-114">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3.  <span data-ttu-id="91b5b-115">Nel `Simple3Des` classe, aggiungere un campo privato per archiviare il provider del servizio di crittografia 3DES.</span><span class="sxs-lookup"><span data-stu-id="91b5b-115">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4.  <span data-ttu-id="91b5b-116">Aggiungere un metodo privato che crea una matrice di byte di lunghezza specificata dall'hash della chiave specificata.</span><span class="sxs-lookup"><span data-stu-id="91b5b-116">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5.  <span data-ttu-id="91b5b-117">Aggiungere un costruttore per inizializzare il provider del servizio di crittografia 3DES.</span><span class="sxs-lookup"><span data-stu-id="91b5b-117">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="91b5b-118">Il `key` parametro determina il `EncryptData` e `DecryptData` metodi.</span><span class="sxs-lookup"><span data-stu-id="91b5b-118">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6.  <span data-ttu-id="91b5b-119">Aggiungere un metodo pubblico che consente di crittografare una stringa.</span><span class="sxs-lookup"><span data-stu-id="91b5b-119">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7.  <span data-ttu-id="91b5b-120">Aggiungere un metodo pubblico per la decrittografia della stringa.</span><span class="sxs-lookup"><span data-stu-id="91b5b-120">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     <span data-ttu-id="91b5b-121">La classe wrapper è ora utilizzabile per proteggere gli asset utente.</span><span class="sxs-lookup"><span data-stu-id="91b5b-121">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="91b5b-122">In questo esempio viene utilizzato per archiviare in modo sicuro i dati personali dell'utente in un file di testo accessibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="91b5b-122">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="91b5b-123">Per testare il wrapper di crittografia</span><span class="sxs-lookup"><span data-stu-id="91b5b-123">To test the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="91b5b-124">In una classe separata, aggiungere un metodo che utilizza il wrapper `EncryptData` cartella documenti del metodo per crittografare una stringa e scriverli all'utente.</span><span class="sxs-lookup"><span data-stu-id="91b5b-124">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2.  <span data-ttu-id="91b5b-125">Aggiungere un metodo che legge la stringa crittografata da parte dell'utente della cartella documenti e consente di decrittografare la stringa con il wrapper `DecryptData` (metodo).</span><span class="sxs-lookup"><span data-stu-id="91b5b-125">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3.  <span data-ttu-id="91b5b-126">Aggiungere il codice dell'interfaccia utente per chiamare il `TestEncoding` e `TestDecoding` metodi.</span><span class="sxs-lookup"><span data-stu-id="91b5b-126">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4.  <span data-ttu-id="91b5b-127">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="91b5b-127">Run the application.</span></span>  
  
     <span data-ttu-id="91b5b-128">Quando si testa l'applicazione, si noti che non è possibile decrittografare i dati se si specifica una password errata.</span><span class="sxs-lookup"><span data-stu-id="91b5b-128">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91b5b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91b5b-129">See also</span></span>

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [<span data-ttu-id="91b5b-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="91b5b-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)

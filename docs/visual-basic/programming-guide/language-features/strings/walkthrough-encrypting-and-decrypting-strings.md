---
title: La crittografia e decrittografia di stringhe in Visual Basic | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- encryption, strings
- strings [Visual Basic], encrypting
- decryption, strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 460b0e6e84f5be23f0c811e48daf36d3d4af3d23
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="2eb15-102">Procedura dettagliata: crittografia e decrittografia di stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2eb15-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="2eb15-103">Questa procedura dettagliata viene illustrato come utilizzare il <xref:System.Security.Cryptography.DESCryptoServiceProvider>(classe) per crittografare e decrittografare le stringhe utilizzando la versione del provider (CSP) del servizio di crittografia di Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algoritmo.</xref:System.Security.Cryptography.TripleDES> </xref:System.Security.Cryptography.DESCryptoServiceProvider></span><span class="sxs-lookup"><span data-stu-id="2eb15-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="2eb15-104">Il primo passaggio consiste nel creare una semplice classe wrapper che incapsula l'algoritmo 3DES e archivia i dati crittografati come una stringa con codifica base 64.</span><span class="sxs-lookup"><span data-stu-id="2eb15-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="2eb15-105">Il wrapper viene quindi utilizzato per archiviare in modo sicuro i dati personali dell'utente in un file di testo accessibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="2eb15-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="2eb15-106">È possibile utilizzare la crittografia per proteggere informazioni riservate dell'utente (ad esempio, le password) e per rendere illeggibile le credenziali di utenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="2eb15-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="2eb15-107">È possibile impedire identità di un utente autorizzato da rubati, che consente di proteggere le risorse dell'utente e consente di non ripudio.</span><span class="sxs-lookup"><span data-stu-id="2eb15-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="2eb15-108">La crittografia può inoltre proteggere i dati dell'utente da cui si accede da utenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="2eb15-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="2eb15-109">Per ulteriori informazioni, vedere [servizi di crittografia](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8).</span><span class="sxs-lookup"><span data-stu-id="2eb15-109">For more information, see [Cryptographic Services](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2eb15-110">Gli algoritmi Triple Data Encryption Standard (3DES) e Rijndael (ora denominato Advanced Encryption Standard [AES]) garantiscono maggiore sicurezza rispetto a DES in quanto più complesse.</span><span class="sxs-lookup"><span data-stu-id="2eb15-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="2eb15-111">Per ulteriori informazioni, vedere <xref:System.Security.Cryptography.DES>e <xref:System.Security.Cryptography.Rijndael>.</xref:System.Security.Cryptography.Rijndael> </xref:System.Security.Cryptography.DES></span><span class="sxs-lookup"><span data-stu-id="2eb15-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="2eb15-112">Per creare il wrapper di crittografia</span><span class="sxs-lookup"><span data-stu-id="2eb15-112">To create the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="2eb15-113">Creare la `Simple3Des` classe per incapsulare i metodi di crittografia e decrittografia.</span><span class="sxs-lookup"><span data-stu-id="2eb15-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     <span data-ttu-id="2eb15-114">[!code-vb[VbVbalrStrings&#38;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2eb15-114">[!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]</span></span>  
  
2.  <span data-ttu-id="2eb15-115">Aggiungere un'importazione dello spazio dei nomi cryptography all'inizio del file che contiene la `Simple3Des` classe.</span><span class="sxs-lookup"><span data-stu-id="2eb15-115">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     <span data-ttu-id="2eb15-116">[!code-vb[&#77; VbVbalrStrings](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2eb15-116">[!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]</span></span>  
  
3.  <span data-ttu-id="2eb15-117">Nella `Simple3Des` classe, aggiungere un campo privato per archiviare il provider del servizio di crittografia 3DES.</span><span class="sxs-lookup"><span data-stu-id="2eb15-117">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="2eb15-118">[!code-vb[VbVbalrStrings&#39;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="2eb15-118">[!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]</span></span>  
  
4.  <span data-ttu-id="2eb15-119">Aggiungere un metodo privato che crea una matrice di byte di lunghezza specificata dall'hash della chiave specificata.</span><span class="sxs-lookup"><span data-stu-id="2eb15-119">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     <span data-ttu-id="2eb15-120">[!code-vb[VbVbalrStrings n.&41;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="2eb15-120">[!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]</span></span>  
  
5.  <span data-ttu-id="2eb15-121">Aggiungere un costruttore per inizializzare il provider del servizio di crittografia 3DES.</span><span class="sxs-lookup"><span data-stu-id="2eb15-121">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="2eb15-122">Il `key` parametro controlla il `EncryptData` e `DecryptData` metodi.</span><span class="sxs-lookup"><span data-stu-id="2eb15-122">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     <span data-ttu-id="2eb15-123">[!code-vb[&#40; VbVbalrStrings](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="2eb15-123">[!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]</span></span>  
  
6.  <span data-ttu-id="2eb15-124">Aggiungere un metodo pubblico che consente di crittografare una stringa.</span><span class="sxs-lookup"><span data-stu-id="2eb15-124">Add a public method that encrypts a string.</span></span>  
  
     <span data-ttu-id="2eb15-125">[!code-vb[VbVbalrStrings&#42;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="2eb15-125">[!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]</span></span>  
  
7.  <span data-ttu-id="2eb15-126">Aggiungere un metodo pubblico che consente di decrittografare una stringa.</span><span class="sxs-lookup"><span data-stu-id="2eb15-126">Add a public method that decrypts a string.</span></span>  
  
     <span data-ttu-id="2eb15-127">[!code-vb[VbVbalrStrings&#43;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="2eb15-127">[!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]</span></span>  
  
     <span data-ttu-id="2eb15-128">La classe wrapper ora può essere utilizzata per proteggere risorse utente.</span><span class="sxs-lookup"><span data-stu-id="2eb15-128">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="2eb15-129">In questo esempio, consente di archiviare in modo sicuro i dati personali dell'utente in un file di testo accessibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="2eb15-129">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="2eb15-130">Per testare il wrapper di crittografia</span><span class="sxs-lookup"><span data-stu-id="2eb15-130">To test the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="2eb15-131">In una classe separata, aggiungere un metodo che usa il wrapper `EncryptData` per crittografare una stringa e scriverli all'utente della cartella documenti.</span><span class="sxs-lookup"><span data-stu-id="2eb15-131">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     <span data-ttu-id="2eb15-132">[!code-vb[VbVbalrStrings&#78;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="2eb15-132">[!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]</span></span>  
  
2.  <span data-ttu-id="2eb15-133">Aggiungere un metodo che legge la stringa crittografata da parte dell'utente della cartella documenti e consente di decrittografare la stringa con il wrapper `DecryptData` metodo.</span><span class="sxs-lookup"><span data-stu-id="2eb15-133">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     <span data-ttu-id="2eb15-134">[!code-vb[VbVbalrStrings&#79;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="2eb15-134">[!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]</span></span>  
  
3.  <span data-ttu-id="2eb15-135">Aggiungere il codice dell'interfaccia utente di chiamare il `TestEncoding` e `TestDecoding` metodi.</span><span class="sxs-lookup"><span data-stu-id="2eb15-135">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4.  <span data-ttu-id="2eb15-136">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2eb15-136">Run the application.</span></span>  
  
     <span data-ttu-id="2eb15-137">Quando si testa l'applicazione, si noti che non è possibile decrittografare i dati se si specifica la password errata.</span><span class="sxs-lookup"><span data-stu-id="2eb15-137">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eb15-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2eb15-138">See Also</span></span>  
 <span data-ttu-id="2eb15-139"><xref:System.Security.Cryptography></xref:System.Security.Cryptography></span><span class="sxs-lookup"><span data-stu-id="2eb15-139"><xref:System.Security.Cryptography></span></span>   
 <span data-ttu-id="2eb15-140"><xref:System.Security.Cryptography.DESCryptoServiceProvider></xref:System.Security.Cryptography.DESCryptoServiceProvider></span><span class="sxs-lookup"><span data-stu-id="2eb15-140"><xref:System.Security.Cryptography.DESCryptoServiceProvider></span></span>   
 <span data-ttu-id="2eb15-141"><xref:System.Security.Cryptography.DES></xref:System.Security.Cryptography.DES></span><span class="sxs-lookup"><span data-stu-id="2eb15-141"><xref:System.Security.Cryptography.DES></span></span>   
 <span data-ttu-id="2eb15-142"><xref:System.Security.Cryptography.TripleDES></xref:System.Security.Cryptography.TripleDES></span><span class="sxs-lookup"><span data-stu-id="2eb15-142"><xref:System.Security.Cryptography.TripleDES></span></span>   
 <span data-ttu-id="2eb15-143"><xref:System.Security.Cryptography.Rijndael></xref:System.Security.Cryptography.Rijndael></span><span class="sxs-lookup"><span data-stu-id="2eb15-143"><xref:System.Security.Cryptography.Rijndael></span></span>   
<span data-ttu-id="2eb15-144"> [Servizi di crittografia](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8)</span><span class="sxs-lookup"><span data-stu-id="2eb15-144"> [Cryptographic Services](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8)</span></span>

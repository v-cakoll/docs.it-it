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
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>Procedura dettagliata: crittografia e decrittografia di stringhe in Visual Basic
Questa procedura dettagliata viene illustrato come utilizzare il <xref:System.Security.Cryptography.DESCryptoServiceProvider> classe per crittografare e decrittografare le stringhe utilizzando la versione del provider (CSP) del servizio di crittografia di Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algoritmo. Il primo passaggio consiste nel creare una semplice classe wrapper che incapsula l'algoritmo 3DES e archivia i dati crittografati come stringa con codifica base 64. Quindi, il wrapper viene utilizzato per archiviare i dati personali dell'utente in modo sicuro in un file di testo accessibile pubblicamente.  
  
 È possibile utilizzare la crittografia per proteggere informazioni riservate dell'utente (ad esempio, le password) e per rendere illeggibile le credenziali di utenti non autorizzati. È possibile impedire identità di un utente autorizzato furto, che protegge le risorse dell'utente e consente di non ripudio. Crittografia possa anche proteggere i dati di un utente dall'accesso di utenti non autorizzati.  
  
 Per altre informazioni, vedere [Servizi di crittografia](../../../../standard/security/cryptographic-services.md).  
  
> [!IMPORTANT]
>  Gli algoritmi Triple Data Encryption Standard (3DES) e il Rijndael (ora denominato Advanced Encryption Standard [AES) garantiscono maggiore sicurezza rispetto a DES, perché sono più complesse. Per altre informazioni, vedere <xref:System.Security.Cryptography.DES> e <xref:System.Security.Cryptography.Rijndael>.  
  
### <a name="to-create-the-encryption-wrapper"></a>Per creare il wrapper di crittografia  
  
1.  Creare la `Simple3Des` classe per incapsulare i metodi di crittografia e decrittografia.  
  
     [!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  Aggiungere un'importazione dello spazio dei nomi di crittografia all'inizio del file che contiene la `Simple3Des` classe.  
  
     [!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  Nel `Simple3Des` classe, aggiungere un campo privato per archiviare il provider del servizio di crittografia 3DES.  
  
     [!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  Aggiungere un metodo privato che crea una matrice di byte di lunghezza specificata dall'hash della chiave specificata.  
  
     [!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  Aggiungere un costruttore per inizializzare il provider del servizio di crittografia 3DES.  
  
     Il `key` parametro controlla il `EncryptData` e `DecryptData` metodi.  
  
     [!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  Aggiungere un metodo pubblico che crittografa una stringa.  
  
     [!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  Aggiungere un metodo pubblico che consente di decrittografare una stringa.  
  
     [!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     La classe wrapper ora utilizzabile per proteggere le risorse utente. In questo esempio, è possibile archiviare in modo sicuro i dati personali dell'utente in un file di testo accessibile pubblicamente.  
  
### <a name="to-test-the-encryption-wrapper"></a>Per testare il wrapper di crittografia  
  
1.  In una classe separata, aggiungere un metodo che usa il wrapper `EncryptData` per crittografare una stringa e scriverlo all'utente della cartella documenti.  
  
     [!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  Aggiungere un metodo che legge la stringa crittografata da parte dell'utente della cartella documenti e consente di decrittografare la stringa con il wrapper `DecryptData` metodo.  
  
     [!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  Aggiungere il codice dell'interfaccia utente per chiamare il `TestEncoding` e `TestDecoding` metodi.  
  
4.  Eseguire l'applicazione.  
  
     Quando si testa l'applicazione, si noti che non è possibile decrittografare i dati se si specifica la password errata.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Security.Cryptography>  
 <xref:System.Security.Cryptography.DESCryptoServiceProvider>  
 <xref:System.Security.Cryptography.DES>  
 <xref:System.Security.Cryptography.TripleDES>  
 <xref:System.Security.Cryptography.Rijndael>  
 [Servizi di crittografia](../../../../standard/security/cryptographic-services.md)

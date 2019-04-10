---
title: La crittografia e decrittografia di stringhe in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: 1d003df87327e14a6cbd65222f86c3dc4df169ff
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59334042"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>Procedura dettagliata: La crittografia e decrittografia di stringhe in Visual Basic
Questa procedura dettagliata illustra come usare il <xref:System.Security.Cryptography.DESCryptoServiceProvider> classe per crittografare e decrittografare le stringhe con la versione del provider (CSP) del servizio di crittografia di Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algoritmo. Il primo passaggio consiste nel creare una semplice classe wrapper che incapsula l'algoritmo 3DES e archivia i dati crittografati come stringa con codifica base 64. Quindi, il wrapper viene utilizzato per archiviare in modo sicuro i dati personali dell'utente in un file di testo accessibile pubblicamente.  
  
 È possibile usare la crittografia per proteggere i segreti utente (ad esempio password) e per rendere le credenziali non leggibile dagli utenti non autorizzati. Questo può proteggere l'identità di un utente autorizzato prevenirne il furto, che protegge le risorse dell'utente e consente di non ripudio. La crittografia può anche proteggere i dati di un utente nel caso in cui gli utenti non autorizzati.  
  
 Per altre informazioni, vedere [Servizi di crittografia](../../../../standard/security/cryptographic-services.md).  
  
> [!IMPORTANT]
>  Gli algoritmi Triple Data Encryption Standard (3DES) e Rijndael (ora denominato Advanced Encryption Standard [AES) garantiscono maggiore sicurezza rispetto a DES perché sono molto più complesse. Per altre informazioni, vedere <xref:System.Security.Cryptography.DES> e <xref:System.Security.Cryptography.Rijndael>.  
  
### <a name="to-create-the-encryption-wrapper"></a>Per creare il wrapper di crittografia  
  
1. Creare il `Simple3Des` classe per incapsulare i metodi di crittografia e decrittografia.  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2. Aggiungere un'importazione dello spazio dei nomi cryptography all'inizio del file che contiene il `Simple3Des` classe.  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3. Nel `Simple3Des` classe, aggiungere un campo privato per archiviare il provider del servizio di crittografia 3DES.  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4. Aggiungere un metodo privato che crea una matrice di byte di lunghezza specificata dall'hash della chiave specificata.  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5. Aggiungere un costruttore per inizializzare il provider del servizio di crittografia 3DES.  
  
     Il `key` parametro determina il `EncryptData` e `DecryptData` metodi.  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6. Aggiungere un metodo pubblico che consente di crittografare una stringa.  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7. Aggiungere un metodo pubblico per la decrittografia della stringa.  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     La classe wrapper è ora utilizzabile per proteggere gli asset utente. In questo esempio viene utilizzato per archiviare in modo sicuro i dati personali dell'utente in un file di testo accessibile pubblicamente.  
  
### <a name="to-test-the-encryption-wrapper"></a>Per testare il wrapper di crittografia  
  
1. In una classe separata, aggiungere un metodo che utilizza il wrapper `EncryptData` cartella documenti del metodo per crittografare una stringa e scriverli all'utente.  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2. Aggiungere un metodo che legge la stringa crittografata da parte dell'utente della cartella documenti e consente di decrittografare la stringa con il wrapper `DecryptData` (metodo).  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3. Aggiungere il codice dell'interfaccia utente per chiamare il `TestEncoding` e `TestDecoding` metodi.  
  
4. Eseguire l'applicazione.  
  
     Quando si testa l'applicazione, si noti che non è possibile decrittografare i dati se si specifica una password errata.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [servizi crittografici](../../../../standard/security/cryptographic-services.md)

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
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>Procedura dettagliata: Crittografia e decrittografia di stringhe in Visual Basic
Questa procedura dettagliata illustra come usare la <xref:System.Security.Cryptography.DESCryptoServiceProvider> classe per crittografare e decrittografare le stringhe usando la versione del provider del servizio di crittografia (CSP) dell'algoritmo Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>). Il primo passaggio consiste nel creare una semplice classe wrapper che incapsula l'algoritmo 3DES e archivia i dati crittografati come stringa con codifica base 64. Il wrapper viene quindi usato per archiviare in modo sicuro i dati utente privati in un file di testo accessibile pubblicamente.  
  
 È possibile usare la crittografia per proteggere i segreti utente, ad esempio le password, e rendere illeggibili le credenziali da parte di utenti non autorizzati. Ciò può impedire che l'identità di un utente autorizzato venga rubata, che protegge le risorse dell'utente e fornisce il non ripudio. La crittografia consente inoltre di proteggere i dati di un utente dall'accesso da parte di utenti non autorizzati.  
  
 Per altre informazioni, vedere [Servizi di crittografia](../../../../standard/security/cryptographic-services.md).  
  
> [!IMPORTANT]
> Gli algoritmi Rijndael (ora definiti Advanced Encryption Standard [AES]) e triple Data Encryption Standard (3DES) forniscono una maggiore sicurezza rispetto a DES perché sono più impegnati a livello di calcolo. Per altre informazioni, vedere <xref:System.Security.Cryptography.DES> e <xref:System.Security.Cryptography.Rijndael>.  
  
### <a name="to-create-the-encryption-wrapper"></a>Per creare il wrapper di crittografia  
  
1. Creare la `Simple3Des` classe per incapsulare i metodi di crittografia e decrittografia.  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2. Aggiungere un'importazione dello spazio dei nomi Cryptography all'inizio del file che contiene la `Simple3Des` classe.  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3. `Simple3Des` Nella classe aggiungere un campo privato per archiviare il provider del servizio di crittografia 3DES.  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4. Aggiungere un metodo privato che crea una matrice di byte di una lunghezza specificata dall'hash della chiave specificata.  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5. Aggiungere un costruttore per inizializzare il provider del servizio di crittografia 3DES.  
  
     Il `key` parametro controlla i `EncryptData` metodi `DecryptData` e.  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6. Aggiungere un metodo pubblico per la crittografia di una stringa.  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7. Aggiungere un metodo pubblico per la decrittografia di una stringa.  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     È ora possibile usare la classe wrapper per proteggere gli asset utente. In questo esempio viene usato per archiviare in modo sicuro i dati utente privati in un file di testo accessibile pubblicamente.  
  
### <a name="to-test-the-encryption-wrapper"></a>Per testare il wrapper di crittografia  
  
1. In una classe separata aggiungere un metodo che usa il `EncryptData` metodo del wrapper per crittografare una stringa e scriverla nella cartella documenti dell'utente.  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2. Aggiungere un metodo che legga la stringa crittografata dalla cartella documenti dell'utente e decrittografa la stringa con il `DecryptData` metodo del wrapper.  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3. Aggiungere il codice dell'interfaccia utente per `TestEncoding` chiamare `TestDecoding` i metodi e.  
  
4. Eseguire l'applicazione.  
  
     Quando si esegue il test dell'applicazione, si noti che i dati non vengono decrittografati se si specifica una password errata.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [Cryptographic Services](../../../../standard/security/cryptographic-services.md)

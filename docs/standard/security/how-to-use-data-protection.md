---
title: 'Procedura: utilizzare la protezione dati'
description: Informazioni su come usare la protezione dei dati tramite l'accesso a Data Protection API (DPAPI) in .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET Framework], data protection API
- data [.NET Framework], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET Framework], data protection API
- data protection API [.NET Framework]
- decryption
- data [.NET Framework], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: c7f88105727dfd33c87a815054aa317ac2052e83
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598593"
---
# <a name="how-to-use-data-protection"></a>Procedura: utilizzare la protezione dati
.NET Framework fornisce l'accesso a Data Protection API (DPAPI), che permette di crittografare dati usando informazioni dell'account utente o del computer corrente.  L'uso di DPAPI permette di attenuare il problema complesso correlato alla generazione e all'archiviazione esplicite di una chiave crittografica.  
  
 Usare la classe <xref:System.Security.Cryptography.ProtectedMemory> per crittografare una matrice di byte in memoria.  Questa funzionalità è disponibile nei sistemi operativi Microsoft Windows XP e versioni successive.  È possibile specificare che la memoria crittografata dal processo corrente può essere decrittografata solo dal processo corrente stesso, da tutti i processi o dallo stesso contesto utente.  Vedere l'enumerazione <xref:System.Security.Cryptography.MemoryProtectionScope> per una descrizione dettagliata delle opzioni di <xref:System.Security.Cryptography.ProtectedMemory>.  
  
 Usare la classe <xref:System.Security.Cryptography.ProtectedData> per crittografare una copia di una matrice di byte. Questa funzionalità è disponibile nei sistemi operativi Microsoft Windows 2000 e versioni successive.  È possibile specificare che i dati crittografati dall'account utente corrente possono essere decrittografati solo dallo stesso account utente oppure da qualsiasi account nel computer.  Vedere l'enumerazione <xref:System.Security.Cryptography.DataProtectionScope> per una descrizione dettagliata delle opzioni di <xref:System.Security.Cryptography.ProtectedData>.  
  
### <a name="to-encrypt-in-memory-data-using-data-protection"></a>Per crittografare i dati in memoria mediante la protezione dei dati  
  
1. Chiamare il metodo <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> statico durante il passaggio di una matrice di byte da crittografare, l'entropia e l'ambito di protezione della memoria.  
  
### <a name="to-decrypt-in-memory-data-using-data-protection"></a>Per decrittografare i dati in memoria mediante la protezione dei dati  
  
1. Chiamare il metodo <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> statico durante il passaggio di una matrice di byte da decrittografare e l'ambito di protezione della memoria.  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a>Per crittografare dati in un file o un flusso mediante la protezione dei dati  
  
1. Creare l'entropia casuale.  
  
2. Chiamare il metodo <xref:System.Security.Cryptography.ProtectedData.Protect%2A> statico durante il passaggio di una matrice di byte da crittografare, l'entropia e l'ambito di protezione dei dati.  
  
3. Scrivere i dati crittografati in un file o un flusso.  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a>Per decrittografare i dati da un file o un flusso mediante la protezione dati  
  
1. Leggere i dati crittografati da un file o un flusso.  
  
2. Chiamare il metodo <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> statico durante il passaggio di una matrice di byte da decrittografare e l'ambito di protezione dei dati.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente mostra le due forme di crittografia e decrittografia.  Prima di tutto, l'esempio di codice crittografa e quindi decrittografa una matrice in memoria di byte.  Quindi, l'esempio di codice crittografa una copia di una matrice di byte, la salva in un file, carica i dati di nuovo dal file e quindi li decrittografa.  L'esempio mostra i dati originali, i dati crittografati e i dati decrittografati.  
  
 [!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
 [!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Includere un riferimento a `System.Security.dll`.  
  
- Includere gli spazi dei nomi <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> e <xref:System.Text>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>

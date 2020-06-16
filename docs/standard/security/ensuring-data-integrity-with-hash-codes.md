---
title: Integrità dei dati con codici hash
description: Informazioni su come garantire l'integrità dei dati usando i codici hash in .NET. Un valore hash è un valore numerico di lunghezza fissa che identifica in modo univoco i dati.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generating hash
- verifying hash codes
- cryptography [.NET Framework], hash
- data integrity
- checking hash codes
- encryption [.NET Framework], hash
- hash
ms.assetid: 33660f33-b70f-4dca-8c87-ab35cfc2961a
ms.openlocfilehash: ffc5e78228f4e7c56febdc0872a0bc0fc581f162
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769054"
---
# <a name="ensuring-data-integrity-with-hash-codes"></a>Integrità dei dati con codici hash
Un valore hash è un valore numerico di lunghezza fissa che identifica in modo univoco i dati. I valori hash rappresentano grandi quantità di dati sotto forma di valori numerici molto più piccoli, pertanto vengono usati con le firme digitali. È possibile firmare un valore hash in modo più efficiente rispetto alla firma di un valore più grande. I valori hash sono anche utili per verificare l'integrità dei dati inviati attraverso canali non sicuri. Il valore hash dei dati ricevuti può essere confrontato con il valore hash dei dati inviati per determinare se i dati sono stati modificati.  
  
 Questo argomento descrive come generare e verificare codici hash usando le classi nello spazio dei nomi <xref:System.Security.Cryptography?displayProperty=nameWithType>.  
  
## <a name="generating-a-hash"></a>Generazione di un hash  
 Le classi hash gestite possono eseguire l'hashing di una matrice di byte o di un oggetto flusso gestito. L'esempio seguente usa l'algoritmo hash SHA1 per creare un valore hash per una stringa. L'esempio usa la classe <xref:System.Text.UnicodeEncoding> per convertire la stringa in una matrice di byte sottoposti ad hashing tramite la classe <xref:System.Security.Cryptography.SHA1Managed>. Il valore hash viene quindi visualizzato nella console.  

 A causa di problemi di collisione con SHA1, Microsoft consiglia di SHA256 o meglio.
  
 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 Questo codice visualizza la stringa seguente nella console:  
  
 `59 4 248 102 77 97 142 201 210 12 224 93 25 41 100 197 213 134 130 135`  
  
## <a name="verifying-a-hash"></a>Verifica di un hash  
 I dati possono essere confrontati con un valore hash per determinarne l'integrità. In genere, viene eseguito l'hashing dei dati in un determinato momento e il valore hash viene protetto in un determinato modo. Successivamente, i dati possono essere sottoposti di nuovo a hashing e confrontati con il valore protetto. Se i valori hash corrispondono, i dati non sono stati modificati. Se i valori hash non corrispondono, i dati sono stati danneggiati. Affinché questo sistema funzioni, l'hash protetto deve essere crittografato o mantenuto segreto a tutte le parti non attendibili.  
  
 L'esempio seguente confronta il valore hash precedente di una stringa con un nuovo valore hash. L'esempio analizza in ciclo ogni byte dei valori hash ed effettua un confronto.  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 Se i due valori hash corrispondono, il codice visualizza quanto segue nella console:  
  
```console  
The hash codes match.  
```  
  
 Se non corrispondono, il codice visualizza quanto segue:  
  
```console  
The hash codes do not match.  
```  
  
## <a name="see-also"></a>Vedere anche

- [Servizi di crittografia](cryptographic-services.md)

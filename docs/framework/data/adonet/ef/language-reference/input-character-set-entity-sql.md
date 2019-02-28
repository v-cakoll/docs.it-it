---
title: Set di caratteri di input (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
ms.openlocfilehash: 7bed10f6e4a9fb01abe825e5eb798da2d866ca84
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976759"
---
# <a name="input-character-set-entity-sql"></a>Set di caratteri di input (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] accetta i caratteri Unicode con codifica UTF-16.  
  
 I valori letterali stringa possono contenere qualsiasi carattere UTF-16 racchiuso tra virgolette singole. Ad esempio, N'文字列リテラル'. Quando i valori letterali stringa vengono confrontati, vengono usati i valori UTF-16 originali. N'ABC, ad esempio, è diverso nelle tabelle codici giapponese e latina.  
  
 I commenti possono contenere qualsiasi carattere UTF-16.  
  
 Gli identificatori preceduti da un carattere di escape possono contenere qualsiasi carattere UTF-16 racchiuso tra parentesi quadre, Ad esempio, [エスケープされた識別子]. Il confronto di identificatori UTF-16 che usano caratteri di escape è senza distinzione tra maiuscole e minuscole. In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] le versioni delle lettere che hanno lo stesso aspetto ma che provengono da tabelle codici diverse vengono gestite come caratteri differenti. Le lettere [ABC], ad esempio, equivalgono alle lettere [abc] se i caratteri corrispondenti appartengono alla stessa tabella codici. Se, tuttavia, gli stessi due identificatori appartengono a tabelle codici differenti, non sono equivalenti.  
  
 Lo spazio vuoto è qualsiasi carattere di spazio vuoto UTF-16.  
  
 Una nuova riga è qualsiasi carattere di nuova riga UTF-16 normalizzato. '\n' e '\r\n' sono ad esempio considerati caratteri di nuova riga, mentre '\r' no.  
  
 Le parole chiave, le espressioni e la punteggiatura possono essere qualsiasi carattere UTF-16 normalizzato in latino. SELECT in una tabella codici giapponese è, ad esempio, una parola chiave valida.  
  
 Le parole chiave, le espressioni e la punteggiatura possono essere solo caratteri latini. `SELECT` in una tabella codici giapponese non è una parola chiave. +,-, \*, /, =, (,), ', [,] e qualsiasi altro costrutto di linguaggio non citato può essere solo caratteri latini.  
  
 Gli identificatori semplici possono essere solo caratteri latini. Questo consente di evitare l'ambiguità durante il confronto, poiché vengono confrontati i valori originali. Ad esempio, ABC sarebbe diverso nelle tabelle codici giapponese e latina.  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)

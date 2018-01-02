---
title: Set di caratteri di input (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 1a830d9df1f94bd21689cba9a9893cb9c344dfdb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="input-character-set-entity-sql"></a>Set di caratteri di input (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] accetta i caratteri Unicode con codifica UTF-16.  
  
 I valori letterali stringa possono contenere qualsiasi carattere UTF-16 racchiuso tra virgolette singole. Ad esempio, N'文字列リテラル'. Quando i valori letterali stringa vengono confrontati, vengono usati i valori UTF-16 originali. N'ABC, ad esempio, è diverso nelle tabelle codici giapponese e latina.  
  
 I commenti possono contenere qualsiasi carattere UTF-16.  
  
 Gli identificatori preceduti da un carattere di escape possono contenere qualsiasi carattere UTF-16 racchiuso tra parentesi quadre, Ad esempio, [エスケープされた識別子]. Il confronto di identificatori UTF-16 che usano caratteri di escape è senza distinzione tra maiuscole e minuscole. In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] le versioni delle lettere che hanno lo stesso aspetto ma che provengono da tabelle codici diverse vengono gestite come caratteri differenti. Le lettere [ABC], ad esempio, equivalgono alle lettere [abc] se i caratteri corrispondenti appartengono alla stessa tabella codici. Se, tuttavia, gli stessi due identificatori appartengono a tabelle codici differenti, non sono equivalenti.  
  
 Lo spazio vuoto è qualsiasi carattere di spazio vuoto UTF-16.  
  
 Una nuova riga è qualsiasi carattere di nuova riga UTF-16 normalizzato. '\n' e '\r\n' sono ad esempio considerati caratteri di nuova riga, mentre '\r' no.  
  
 Le parole chiave, le espressioni e la punteggiatura possono essere qualsiasi carattere UTF-16 normalizzato in latino. SELECT in una tabella codici giapponese è, ad esempio, una parola chiave valida.  
  
 Le parole chiave, le espressioni e la punteggiatura possono essere solo caratteri latini. `SELECT` in una tabella codici giapponese non è una parola chiave. +, -, *, /, =, () ', [,] e qualsiasi altro costrutto di linguaggio non citato possono essere solo caratteri latini.  
  
 Gli identificatori semplici possono essere solo caratteri latini. Questo consente di evitare l'ambiguità durante il confronto, poiché vengono confrontati i valori originali. ABC sarebbe ad esempio diverso nelle tabelle codici giapponese e latina.  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)

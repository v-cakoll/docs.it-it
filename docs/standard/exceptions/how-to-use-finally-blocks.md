---
title: 'Procedura: utilizzare blocchi Finally'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- exceptions, finally blocks
- try/catch blocks
- finally blocks
- ArgumentOutOfRangeException class
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b303582a62f211091b1ebee0e88cf380da8b03d9
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2017
---
# <a name="how-to-use-finally-blocks"></a>Come usare i blocchi finally

Quando si verifica un'eccezione, l'esecuzione viene arrestata e il controllo viene assegnato al gestore di eccezioni appropriato. Spesso questo significa che le righe di codice che si prevede di eseguire vengono ignorate. La pulizia di alcune risorse, ad esempio la chiusura di un file, deve essere eseguita anche se viene generata un'eccezione. A tale scopo è possibile usare un blocco `finally`. Un blocco `finally` viene sempre eseguito, indipendentemente dalla generazione di un'eccezione.

L'esempio di codice seguente usa un blocco `try`/`catch` per rilevare <xref:System.ArgumentOutOfRangeException>. Il metodo `Main` crea due matrici e tenta di copiarle una sull'altra. L'azione genera un'eccezione <xref:System.ArgumentOutOfRangeException> e l'errore viene scritto nella console. Il blocco `finally` viene eseguito indipendentemente dal risultato dell'azione di copia.

[!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
[!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
[!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  

## <a name="see-also"></a>Vedere anche  
[Eccezioni](index.md)   

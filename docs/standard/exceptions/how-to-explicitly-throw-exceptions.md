---
title: 'Procedura: generare eccezioni in modo esplicito'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- FileNotFoundException class
- try/catch blocks
- exceptions, throwing
- implicitly throwing exceptions
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
ms.openlocfilehash: 750da20b8c1c40901cc363ac0eff8af888821ce9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708862"
---
# <a name="how-to-explicitly-throw-exceptions"></a>Come generare in modo esplicito le eccezioni

È possibile generare in modo [`throw`](../../csharp/language-reference/keywords/throw.md) esplicito [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) un'eccezione utilizzando il linguaggio C o l'istruzione di Visual Basic. È anche possibile generare di nuovo un'eccezione rilevata usando l'istruzione `throw`. Si consiglia di aggiungere informazioni a un'eccezione generata di nuovo per offrire ulteriori informazioni durante il debug.

L'esempio di codice seguente usa un blocco `try`/`catch` per rilevare una possibile eccezione <xref:System.IO.FileNotFoundException>. Il blocco `try` è seguito da un blocco `catch` che rileva <xref:System.IO.FileNotFoundException> e scrive un messaggio nella console se il file di dati non viene trovato. L'istruzione successiva è l'istruzione `throw` che genera una nuova eccezione <xref:System.IO.FileNotFoundException> e aggiunge informazioni di testo all'eccezione.

[!code-csharp[Exception.Throwing#1](~/samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a>Vedere anche

- [Eccezioni](index.md)

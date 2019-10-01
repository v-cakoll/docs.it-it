---
title: 'Procedura: Generare in modo esplicito le eccezioni'
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a71cefc0a6483dbbe6513a64d8111a07a2e5af42
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696734"
---
# <a name="how-to-explicitly-throw-exceptions"></a>Come generare in modo esplicito le eccezioni

È possibile generare in modo esplicito un'eccezione C# usando l'istruzione [`throw`](../../csharp/language-reference/keywords/throw.md) o Visual Basic [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) . È anche possibile generare di nuovo un'eccezione rilevata usando l'istruzione `throw`. Si consiglia di aggiungere informazioni a un'eccezione generata di nuovo per offrire ulteriori informazioni durante il debug.

L'esempio di codice seguente usa un blocco `try`/`catch` per rilevare una possibile eccezione <xref:System.IO.FileNotFoundException>. Il blocco `try` è seguito da un blocco `catch` che rileva <xref:System.IO.FileNotFoundException> e scrive un messaggio nella console se il file di dati non viene trovato. L'istruzione successiva è l'istruzione `throw` che genera una nuova eccezione <xref:System.IO.FileNotFoundException> e aggiunge informazioni di testo all'eccezione.

[!code-csharp[Exception.Throwing#1](~/samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a>Vedere anche

- [Eccezioni](index.md)

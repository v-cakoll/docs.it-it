---
title: 'Procedura: Usare il blocco try/catch per intercettare le eccezioni'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 852df5cb3eeea2ee5fa44ddce2f97e9c4f8d8b5a
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48842385"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a>Come usare il blocco try/catch per rilevare le eccezioni

Inserire le sezioni di codice che potrebbero generare eccezioni in un blocco `try` e il codice che gestisce le eccezioni in un blocco `catch`. Il blocco `catch` è una serie di istruzioni che iniziano con la parola chiave `catch`, seguita da un tipo di eccezione e un'azione da eseguire.

L'esempio di codice seguente usa un blocco `try`/`catch` per rilevare una possibile eccezione. Il metodo `Main` contiene un blocco `try` con un'istruzione <xref:System.IO.StreamReader> che apre un file di dati denominato `data.txt` e scrive una stringa del file. Il blocco `try` è seguito da un blocco `catch` che rileva qualsiasi eccezione del blocco `try`.

 [!code-cpp[CatchException#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception2.cpp#3)]
 [!code-csharp[CatchException#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
 [!code-vb[CatchException#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]  

Common Language Runtime rileva le eccezioni non rilevate da un blocco catch. A seconda della configurazione del runtime, viene visualizzata una finestra di dialogo di debug, viene interrotta l'esecuzione del programma e viene visualizzata una finestra di dialogo con le informazioni sull'eccezione o viene stampato un errore in STDERR.

> [!NOTE] 
> Quasi tutte le righe di codice possono causare un'eccezione, in particolare eccezioni generate da Common Language Runtime, ad esempio <xref:System.OutOfMemoryException>. Sebbene nella maggior parte delle applicazioni non sia necessario gestire queste eccezioni, considerare questa eventualità quando si creano librerie che devono essere usate da altri utenti. Per suggerimenti su quando impostare il codice di un blocco Try, vedere [Procedure consigliate per le eccezioni](best-practices-for-exceptions.md).

## <a name="see-also"></a>Vedere anche

- [Eccezioni](index.md)

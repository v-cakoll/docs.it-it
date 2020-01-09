---
title: 'Procedura: Usare il blocco try/catch per intercettare le eccezioni'
ms.date: 02/06/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
ms.openlocfilehash: 5a9218d394b76e897f4263708a10f1bc895ad4e1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708466"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a>Come usare il blocco try/catch per rilevare le eccezioni

Inserire le istruzioni di codice che possono generare un'eccezione in un blocco `try` e inserire le istruzioni usate per gestire l'eccezione o le eccezioni in uno o più blocchi `catch` sotto il blocco `try`. Ogni blocco `catch` include il tipo di eccezione e può contenere istruzioni aggiuntive necessarie per gestire quel tipo di eccezione.

Nell'esempio seguente un oggetto <xref:System.IO.StreamReader> apre un file chiamato *data.txt* e recupera una riga dal file. Dato che il codice può generare una qualsiasi delle tre eccezioni disponibili, viene inserito in un blocco `try`. Tre blocchi `catch` intercettano le eccezioni e le gestiscono mediante la visualizzazione dei risultati nella console.

[!code-csharp[CatchException#3](~/samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
[!code-vb[CatchException#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]

Common Language Runtime (CLR) rileva le eccezioni non gestite dai blocchi `catch`. Se un'eccezione viene rilevata da CLR, a seconda della configurazione di CLR può verificarsi uno dei risultati seguenti:

- Viene visualizzata la finestra di dialogo **Debug**.
- Il programma interrompe l'esecuzione e viene visualizzata una finestra di dialogo con informazioni sull'eccezione.
- Viene visualizzato un errore nel [flusso di output degli errori standard](xref:System.Console.Error).

> [!NOTE]
> La maggior parte del codice può generare un'eccezione. Alcune eccezioni, ad esempio <xref:System.OutOfMemoryException>, possono essere generate da CLR in qualsiasi momento. Le applicazioni non sono necessarie per gestire queste eccezioni, ma tenere presente questa possibilità quando si creano librerie che devono essere usate da altri utenti. Per suggerimenti su quando impostare il codice di un blocco `try`, vedere [Procedure consigliate per le eccezioni](best-practices-for-exceptions.md).

## <a name="see-also"></a>Vedere anche

- [Eccezioni](index.md)
- [Gestione degli errori di I/O in .NET](../io/handling-io-errors.md)

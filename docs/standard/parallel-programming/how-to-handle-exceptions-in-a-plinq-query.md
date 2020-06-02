---
title: 'Procedura: Gestire le eccezioni in una query PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
ms.openlocfilehash: 4097d222b5fa51cc638a2d07d3fd2eddf5d9859c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84278649"
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a>Procedura: Gestire le eccezioni in una query PLINQ

Il primo esempio in questo argomento mostra come gestire l'oggetto <xref:System.AggregateException?displayProperty=nameWithType>, che può essere generato da una query PLINQ in fase di esecuzione. Il secondo esempio mostra come inserire blocchi Try-Catch all'interno di delegati, il più vicino possibile al punto in cui verrà generata l'eccezione. In questo modo, è possibile intercettare le eccezioni non appena si verificano, per poter proseguire con l'esecuzione della query. Quando alle eccezioni è consentita la propagazione fino al thread di unione, è possibile che una query continui a elaborare alcuni elementi dopo la generazione dell'eccezione.

In alcuni casi, quando PLINQ passa all'esecuzione sequenziale e viene generata un'eccezione, l'eccezione può essere propagata direttamente, senza eseguirne il wrapping in un oggetto <xref:System.AggregateException>. Inoltre, gli oggetti <xref:System.Threading.ThreadAbortException> vengono sempre propagati direttamente.

> [!NOTE]
> Quando è abilitato "Just My Code", Visual Studio si interrompe in corrispondenza della riga che genera l'eccezione e visualizza un messaggio di errore che indica che l'eccezione non è stata gestita dal codice utente. Questo errore non è grave. È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti. Per impedire l'interruzione di Visual Studio al primo errore, deselezionare semplicemente la casella di controllo "Just My Code" in **Strumenti, Opzioni, Debug, Generale**.
>
> Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente. Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](understanding-speedup-in-plinq.md).

## <a name="example"></a>Esempio

Questo esempio mostra come inserire blocchi Try-Catch intorno al codice che esegue la query per recuperare qualsiasi eccezione <xref:System.AggregateException?displayProperty=nameWithType> generata.

[!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
[!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]

In questo esempio la query non può continuare dopo la generazione dell'eccezione. Nel momento in cui il codice dell'applicazione intercetta l'eccezione, PLINQ ha già arrestato la query in tutti i thread.

## <a name="example"></a>Esempio

L'esempio seguente mostra come inserire un blocco Try-Catch in un delegato per permettere di intercettare un'eccezione e proseguire con l'esecuzione della query.

[!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
[!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]

## <a name="compiling-the-code"></a>Compilazione del codice

- Per compilare ed eseguire questi esempi, copiarli nel progetto PLINQ Data Sample e chiamare il metodo da Main.

## <a name="robust-programming"></a>Programmazione efficiente

Non intercettare un'eccezione se non si è in grado di gestirla, in modo da non danneggiare lo stato del programma.

## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.ParallelEnumerable>
- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)

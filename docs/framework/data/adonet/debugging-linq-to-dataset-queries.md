---
title: Debug di query di LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
ms.openlocfilehash: a82fd3e99a556daf40e5c65a16cf20278f38ea26
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785205"
---
# <a name="debugging-linq-to-dataset-queries"></a>Debug di query di LINQ to DataSet

Visual Studio supporta il debug del codice LINQ to DataSet. Esistono tuttavia alcune differenze tra il debug del codice LINQ to DataSet e il codice non LINQ to DataSet gestito. La maggior parte delle funzionalità di debug è compatibile con LINQ to DataSet istruzioni, inclusi l'esecuzione di istruzioni, l'impostazione di punti di interruzione e la visualizzazione dei risultati visualizzati nelle finestre del debugger. Tuttavia, l'esecuzione posticipata delle query in ha alcuni effetti collaterali da considerare durante il debug LINQ to DataSet codice e vi sono alcune limitazioni all'uso di modifica e continuazione. In questo argomento vengono illustrati gli aspetti del debug che sono univoci per LINQ to DataSet rispetto al codice non LINQ to DataSet gestito.  
  
## <a name="viewing-results"></a>Visualizzazione dei risultati  
 È possibile visualizzare il risultato di un'istruzione LINQ to DataSet usando i suggerimenti dati, il finestra Espressioni di controllo e la finestra di dialogo controllo immediato. Quando si usa una finestra di origine, passare con il puntatore su una query nella finestra di origine per visualizzare un suggerimento dati. È possibile copiare una variabile di LINQ to DataSet e incollarla nella finestra di dialogo finestra Espressioni di controllo o controllo immediato. In LINQ to DataSet, una query non viene valutata quando viene creata o dichiarata, ma solo quando la query viene eseguita. Questa operazione è denominata *esecuzione posticipata*. La variabile della query non dispone pertanto di un valore fino a quando non viene valutata. Per ulteriori informazioni, vedere [query in LINQ to DataSet](queries-in-linq-to-dataset.md).  
  
 Per visualizzare i risultati della query, è necessario che la query venga valutata dal debugger. Questa valutazione implicita viene eseguita quando si visualizza un LINQ to DataSet risultati della query nel debugger e presenta alcuni effetti che è opportuno prendere in considerazione. La singola valutazione della query e l'espansione del nodo dei risultati richiedono tempo. La valutazione ripetuta di alcune query può comportare una notevole riduzione delle prestazioni. La valutazione di una query può inoltre avere come effetto collaterale la modifica del valore dei dati o dello stato del programma. Non tutte le query hanno effetti collaterali. Per determinare la possibilità di valutare una query in modo sicuro, senza effetti collaterali, è necessario conoscere il codice con cui la query viene implementata. Per altre informazioni, vedere [effetti collaterali ed espressioni](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/a7a250bs(v=vs.120)).  
  
## <a name="edit-and-continue"></a>Modifica e continuazione  
 La funzionalità modifica e continuazione non supporta le modifiche apportate alle query LINQ to DataSet. Se si aggiunge, rimuove o modifica un'istruzione LINQ to DataSet durante una sessione di debug, viene visualizzata una finestra di dialogo che indica che la modifica non è supportata da modifica e continuazione. A questo punto è possibile annullare la modifica oppure interrompere la sessione di debug per avviare una nuova sessione con il codice modificato.  
  
 Inoltre, la funzionalità modifica e continuazione non supporta la modifica del tipo o del valore di una variabile utilizzata in un'istruzione LINQ to DataSet. Anche in questo caso è possibile annullare le modifiche oppure interrompere e riavviare la sessione di debug.  
  
 In Visual C# Studio non è possibile usare modifica e continuazione su nessun codice in un metodo contenente una query LINQ to DataSet.  
  
 In Visual Basic in Visual Studio, è possibile usare modifica e continuazione su codice non LINQ to DataSet, anche in un metodo che contiene una query di LINQ to DataSet. È possibile aggiungere o rimuovere codice prima dell'istruzione LINQ to DataSet, anche se le modifiche influiscono sul numero di riga della query LINQ to DataSet. L'esperienza di debug Visual Basic per il codice non LINQ to DataSet rimane invariata prima dell'introduzione di LINQ to DataSet. Tuttavia, non è possibile modificare, aggiungere o rimuovere una query LINQ to DataSet, a meno che non si interrompa il debug per applicare le modifiche.  
  
## <a name="see-also"></a>Vedere anche

- [Debug di codice gestito](/visualstudio/debugger/debugging-managed-code)
- [Guida per programmatori](programming-guide-linq-to-dataset.md)

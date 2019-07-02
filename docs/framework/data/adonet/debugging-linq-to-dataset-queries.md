---
title: Debug di query di LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
ms.openlocfilehash: 38eda9f352c4a8d8590e5e57b48c694eadd0397b
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67503980"
---
# <a name="debugging-linq-to-dataset-queries"></a>Debug di query di LINQ to DataSet

Visual Studio supporta il debug di LINQ per il codice del DataSet. Tuttavia, esistono alcune differenze tra LINQ di debug al codice di set di dati e non al set di dati gestiti codice LINQ. Funzionalità di debug più usare LINQ per le istruzioni set di dati, inclusa l'esecuzione di istruzioni, l'impostazione dei punti di interruzione e visualizzazione dei risultati nelle finestre del debugger. Tuttavia, esecuzione posticipata di query presenta alcuni effetti collaterali che è opportuno considerare durante il debug di LINQ per il codice del DataSet e sono previste alcune limitazioni all'uso di modifica e continuazione. Questo argomento illustra gli aspetti del debug che sono univoci per LINQ to DataSet rispetto a non-codice in LINQ to DataSet gestito.  
  
## <a name="viewing-results"></a>Visualizzazione dei risultati  
 È possibile visualizzare il risultato di una LINQ all'istruzione set di dati usando i suggerimenti dati, finestra Espressioni di controllo e la finestra di dialogo Controllo immediato. Quando si usa una finestra di origine, passare con il puntatore su una query nella finestra di origine per visualizzare un suggerimento dati. È possibile copiare un LINQ in set di dati variabile e incollarlo nella finestra Espressioni di controllo o la finestra di dialogo Controllo immediato. In LINQ to DataSet, una query non verrà valutata quando viene creato o dichiarato, ma solo quando viene eseguita la query. Questa operazione viene definita *un'esecuzione posticipata*. La variabile della query non dispone pertanto di un valore fino a quando non viene valutata. Per altre informazioni, vedere [le query in LINQ to DataSet](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md).  
  
 Per visualizzare i risultati della query, è necessario che la query venga valutata dal debugger. Questa valutazione implicita si verifica quando si visualizza un LINQ al risultato di query di set di dati nel debugger, e ha alcuni effetti, che è necessario considerare. La singola valutazione della query e l'espansione del nodo dei risultati richiedono tempo. La valutazione ripetuta di alcune query può comportare una notevole riduzione delle prestazioni. La valutazione di una query può inoltre avere come effetto collaterale la modifica del valore dei dati o dello stato del programma. Non tutte le query hanno effetti collaterali. Per determinare la possibilità di valutare una query in modo sicuro, senza effetti collaterali, è necessario conoscere il codice con cui la query viene implementata. Per altre informazioni, vedere [effetti collaterali ed espressioni](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/a7a250bs(v=vs.120)).  
  
## <a name="edit-and-continue"></a>Modifica e continuazione  
 Modifica e continuazione non supporta modifiche a LINQ alle query di set di dati. Se si aggiungere, rimuovere o modificare un LINQ all'istruzione set di dati durante una sessione di debug, viene visualizzata una finestra di dialogo indicante che la modifica non è supportata da modifica e continuazione. A questo punto è possibile annullare la modifica oppure interrompere la sessione di debug per avviare una nuova sessione con il codice modificato.  
  
 In modifica e continuazione non supporta la modifica il tipo o il valore di una variabile che viene usato in LINQ to DataSet istruzione. Anche in questo caso è possibile annullare le modifiche oppure interrompere e riavviare la sessione di debug.  
  
 Nell'oggetto visivo C# in Visual Studio, è possibile usare modifica e continuazione su qualsiasi codice in un metodo contenente una query LINQ to DataSet.  
  
 In Visual Basic in Visual Studio, è possibile usare modifica e continuazione su non-codice in LINQ to DataSet, anche in metodi contenente una query LINQ to DataSet. È possibile aggiungere o rimuovere codice prima di LINQ all'istruzione set di dati, anche se le modifiche influiscono sul numero di riga del query LINQ to DataSet. L'esperienza per non-codice in LINQ to DataSet di debug di Visual Basic rimane invariata com'era prima dell'introduzione di LINQ to DataSet. È possibile modificare, aggiungere o rimuovere una query LINQ to DataSet, tuttavia, a meno che non si arresta il debug per applicare le modifiche.  
  
## <a name="see-also"></a>Vedere anche

- [Debug di codice gestito](/visualstudio/debugger/debugging-managed-code)
- [Guida per programmatori](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)

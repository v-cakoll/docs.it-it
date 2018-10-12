---
title: Debug di query di LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
ms.openlocfilehash: c1014db4cad54420b917585becd2a2031638c1d9
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123605"
---
# <a name="debugging-linq-to-dataset-queries"></a>Debug di query di LINQ to DataSet

Visual Studio supporta il debug di [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] codice. Vi sono tuttavia alcune differenze tra l'esecuzione del debug di codice [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] e di codice gestito non [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. La maggior parte delle funzionalità di debug è compatibile con le istruzioni [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], inclusa l'esecuzione di istruzioni, l'impostazione dei punti di interruzione e la visualizzazione dei risultati nelle finestre del debugger. Posticipata, tuttavia, l'esecuzione in ha alcuni effetti collaterali che è opportuno considerare durante il debug di query [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] del codice e sono previste alcune limitazioni all'uso di modifica e continuazione. In questo argomento vengono illustrati gli aspetti del debug che sono univoci per [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] rispetto a non -[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] codice gestito.  
  
## <a name="viewing-results"></a>Visualizzazione dei risultati  
 È possibile visualizzare il risultato di un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] istruzione usando i suggerimenti dati, finestra Espressioni di controllo e la finestra di dialogo Controllo immediato. Quando si usa una finestra di origine, passare con il puntatore su una query nella finestra di origine per visualizzare un suggerimento dati. È possibile copiare una variabile [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] e incollarla nella finestra Espressioni di controllo o nella finestra di dialogo Controllo immediato. In [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] le query non vengono valutate al momento della creazione o della dichiarazione, ma solo quando vengono eseguite. Questa operazione viene definita *un'esecuzione posticipata*. La variabile della query non dispone pertanto di un valore fino a quando non viene valutata. Per altre informazioni, vedere [le query in LINQ to DataSet](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md).  
  
 Per visualizzare i risultati della query, è necessario che la query venga valutata dal debugger. Questa valutazione implicita si verifica quando si visualizza un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] risultato della query nel debugger e ha alcuni effetti, è necessario considerare. La singola valutazione della query e l'espansione del nodo dei risultati richiedono tempo. La valutazione ripetuta di alcune query può comportare una notevole riduzione delle prestazioni. La valutazione di una query può inoltre avere come effetto collaterale la modifica del valore dei dati o dello stato del programma. Non tutte le query hanno effetti collaterali. Per determinare la possibilità di valutare una query in modo sicuro, senza effetti collaterali, è necessario conoscere il codice con cui la query viene implementata. Per altre informazioni, vedere [effetti collaterali ed espressioni](https://msdn.microsoft.com/library/e1f8a6ea-9e19-481d-b6bd-df120ad3bf4e).  
  
## <a name="edit-and-continue"></a>Modifica e continuazione  
 Modifica e continuazione non supporta le modifiche apportate a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] le query. Se aggiungere, rimuovere o modificare un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] viene visualizzata una finestra di dialogo di istruzione durante una sessione di debug, indicante che la modifica non è supportata da modifica e continuazione. A questo punto è possibile annullare la modifica oppure interrompere la sessione di debug per avviare una nuova sessione con il codice modificato.  
  
 Inoltre, modifica e continuazione non supporta la modifica il tipo o il valore di una variabile che viene usato in un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] istruzione. Anche in questo caso è possibile annullare le modifiche oppure interrompere e riavviare la sessione di debug.  
  
 In Visual c# in Visual Studio, è possibile usare modifica e continuazione su qualsiasi codice in un metodo che contiene un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query.  
  
 In Visual Basic in Visual Studio, è possibile usare modifica e continuazione su non -[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] codice, anche in metodi contenente una [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query. È possibile aggiungere o rimuovere codice prima la [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] anche se le modifiche influiscono sul numero di riga dell'istruzione il [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query. L'esecuzione del debug di Visual Basic non -[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] codice rimane invariato rispetto a prima [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] è stata introdotta. È possibile modificare, aggiungere o rimuovere un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] esegue una query, tuttavia, a meno che non si arresta il debug per applicare le modifiche.  
  
## <a name="see-also"></a>Vedere anche  
 [Debug di codice gestito](/visualstudio/debugger/debugging-managed-code)  
 [Guida per programmatori](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)

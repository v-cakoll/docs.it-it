---
title: 'Procedura dettagliata: Creazione di una pipeline del flusso di dati'
description: Creare una pipeline del flusso di elementi, ovvero una serie di componenti o blocchi di flussi di data. Un blocco di flussi di lavoro esegue una determinata attività per contribuire a un obiettivo più grande.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow pipelines, creating with TPL
- Task Parallel Library, dataflows
- TPL dataflow library, creating dataflow pipeline
ms.assetid: 69308f82-aa22-4ac5-833d-e748533b58e8
ms.openlocfilehash: 7fe12b63b04d403334e4b64a421b105550467ca4
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767871"
---
# <a name="walkthrough-creating-a-dataflow-pipeline"></a>Procedura dettagliata: Creazione di una pipeline del flusso di dati
Sebbene sia possibile usare i metodi <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Dataflow.DataflowBlock.TryReceive%2A?displayProperty=nameWithType> per ricevere messaggi da blocchi di origine, è anche possibile connettere blocchi di messaggi per formare una *pipeline del flusso di dati*. Una pipeline del flusso di dati è costituita da una serie di componenti o *blocchi di flussi di dati*, ognuno dei quali esegue un'attività specifica che contribuisce a un obiettivo più grande. In ogni blocco di flussi di dati di una pipeline del flusso di dati viene eseguito un lavoro quando si riceve un messaggio da un altro blocco di flussi di dati. Un'analogia a questo è data da una catena di montaggio per la produzione di automobili. Man mano che ciascun veicolo passa attraverso la catena di montaggio, in una postazione viene assemblato il telaio, nella successiva viene installato il motore e così via. Grazie alla catena di montaggio in cui è possibile eseguire il montaggio di più veicoli contemporaneamente, si ottiene una maggiore produzione rispetto al montaggio completo dei veicoli uno alla volta.

 Questo documento illustra una pipeline del flusso dati che scarica il libro *L'Iliade di Omero* da un sito Web ed esegue ricerche nel testo per trovare corrispondenza tra parole specifiche e le stesse parole con l'ordine dei caratteri rovesciato. La formazione della pipeline del flusso di dati in questo documento consiste nei passaggi seguenti:  
  
1. Creare i blocchi di flussi di dati che fanno parte della pipeline.  
  
2. Connettere ogni blocco di flussi di dati al blocco successivo nella pipeline. L'output del blocco precedente nella pipeline viene ricevuto da ogni blocco come input.  
  
3. Per ogni blocco di flussi di dati, creare un'attività di continuazione mediante la quale il blocco successivo viene impostato sullo stato completato al termine del blocco precedente.  
  
4. Inserire i dati nell'intestazione della pipeline.  
  
5. Contrassegnare l'intestazione della pipeline come completata.  
  
6. Attendere il completamento di tutto il lavoro da parte della pipeline.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Prima di iniziare questa procedura dettagliata, leggere [Flusso di dati](dataflow-task-parallel-library.md).  
  
## <a name="creating-a-console-application"></a>Creazione di un'applicazione console  
 In Visual Studio creare un progetto Applicazione console di Visual C# o Visual Basic. Installare il pacchetto System.Threading.Tasks.Dataflow NuGet.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

 Aggiungere il seguente codice al progetto per creare l'applicazione di base.  
  
 [!code-csharp[TPLDataflow_Palindromes#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#2)]
 [!code-vb[TPLDataflow_Palindromes#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromesemptymain.vb#2)]  
  
## <a name="creating-the-dataflow-blocks"></a>Creazione dei blocchi di flussi di dati  
 Aggiungere il seguente codice al metodo `Main` per creare i blocchi di flussi di dati che fanno parte della pipeline. Nella tabella seguente viene riepilogato il ruolo di ciascun membro della pipeline.  
  
 [!code-csharp[TPLDataflow_Palindromes#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#3)]
 [!code-vb[TPLDataflow_Palindromes#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#3)]  
  
|Membro|Type|Descrizione|  
|------------|----------|-----------------|  
|`downloadString`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Scarica il testo del libro dal Web.|  
|`createWordList`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Suddivide il testo del libro in una matrice di parole.|  
|`filterWordList`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Rimuove le parole brevi e i duplicati dalla matrice di parole.|  
|`findReversedWords`|<xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>|Cerca tutte le parole nella raccolta filtrata della matrice di parole i cui contrari sono presenti anche nella matrice di parole.|  
|`printReversedWords`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Visualizza le parole e i contrari corrispondenti nella console.|  
  
 Sebbene sia possibile combinare più passaggi nella pipeline del flusso di dati in questo esempio in un unico passaggio, nell'esempio viene illustrato il concetto di composizione di più attività del flusso di dati indipendenti per eseguire un'attività più grande. Nell'esempio viene utilizzato l'oggetto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> per consentire a ogni membro della pipeline di eseguire un'operazione sui relativi dati di input e inviare i risultati al passaggio successivo nella pipeline. Il membro `findReversedWords` della pipeline è un oggetto <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> poiché tramite esso vengono generati più output indipendenti per ogni input. La parte finale della pipeline, `printReversedWords`, è un oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> poiché tramite esso viene eseguita un'azione sul relativo input e non viene generato un risultato.  
  
## <a name="forming-the-pipeline"></a>Formazione della pipeline  
 Aggiungere il codice seguente per connettere ogni blocco al successivo nella pipeline.  
  
 Quando si chiama il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A> per connettere un blocco di origine del flusso di dati a un blocco di destinazione del flusso di dati, i dati nel blocco di origine del flusso di dati vengono propagati nel blocco di destinazione quando diventano disponibili. Se si specifica anche <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions> con <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions.PropagateCompletion> impostato su true, l'esito positivo o negativo di un blocco nella pipeline causerà il completamento del blocco successivo nella pipeline.
  
 [!code-csharp[TPLDataflow_Palindromes#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#4)]
 [!code-vb[TPLDataflow_Palindromes#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#4)]  
  
## <a name="posting-data-to-the-pipeline"></a>Inserimento dei dati nella pipeline  
 Aggiungere il codice seguente per inserire l'URL del libro *L'Iliade di Omero* nell'intestazione della pipeline del flusso di dati.  
  
 [!code-csharp[TPLDataflow_Palindromes#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#6)]
 [!code-vb[TPLDataflow_Palindromes#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#6)]  
  
 In questo esempio viene usato il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A?displayProperty=nameWithType> in modo sincrono per inviare i dati all'intestazione della pipeline. Utilizzare il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A?displayProperty=nameWithType> quando è necessario inviare in modo asincrono i dati a un nodo del flusso di dati.  
  
## <a name="completing-pipeline-activity"></a>Completamento dell'attività della pipeline  
 Aggiungere il codice seguente per contrassegnare l'intestazione della pipeline come completata. L'intestazione della pipeline propaga il completamento dopo l'elaborazione di tutti i messaggi memorizzati nel buffer.
  
 [!code-csharp[TPLDataflow_Palindromes#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#7)]
 [!code-vb[TPLDataflow_Palindromes#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#7)]  
  
 In questo esempio viene inviato un URL tramite la pipeline del flusso di dati da elaborare. Se si invia più di un input attraverso una pipeline, chiamare il metodo <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A?displayProperty=nameWithType> dopo l'invio di tutti gli input. È possibile omettere questo passaggio se nell'applicazione non vi è alcun punto ben definito in cui i dati non sono più disponibili o non è necessaria l'attesa del completamento della pipeline da parte dell'applicazione.  
  
## <a name="waiting-for-the-pipeline-to-finish"></a>Attesa del completamento della pipeline  
 Aggiungere il codice seguente per attendere il completamento della pipeline. L'operazione globale viene completata al termine della parte finale della pipeline.  
  
 [!code-csharp[TPLDataflow_Palindromes#8](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#8)]
 [!code-vb[TPLDataflow_Palindromes#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#8)]  
  
 È possibile attendere il completamento del flusso di dati da qualsiasi thread o da più thread contemporaneamente.  
  
## <a name="the-complete-example"></a>Esempio completo  
 Nell'esempio riportato di seguito viene illustrato il codice completo per questa procedura guidata.  
  
 [!code-csharp[TPLDataflow_Palindromes#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#1)]
 [!code-vb[TPLDataflow_Palindromes#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#1)]  
  
## <a name="next-steps"></a>Passaggi successivi  
 In questo esempio viene inviato un URL da elaborare tramite la pipeline del flusso di dati. Se si invia più di un valore di input tramite una pipeline, è possibile introdurre un form di parallelismo nell'applicazione che rappresenta il numero di parti che possono essere spostate in una fabbrica di automobili. Quando tramite il primo membro della pipeline viene inviato il risultato al secondo membro, è possibile elaborare un altro elemento in parallelo mentre tramite il secondo membro viene elaborato il primo risultato.  
  
 Il parallelismo raggiunto attraverso l'uso di pipeline di flussi di dati è noto come *parallelismo con granularità grossolana* poiché consiste in genere in attività più o meno grandi. È anche possibile usare un *parallelismo con granularità più fine* di attività più piccole a esecuzione breve in una pipeline del flusso di dati. In questo esempio, nel membro `findReversedWords` della pipeline viene usato [PLINQ](introduction-to-plinq.md) per elaborare in parallelo più elementi nell'elenco di lavoro. L'utilizzo di parallelismo con granularità fine in una pipeline con granularità grossolana può migliorare la velocità effettiva globale.  
  
 È anche possibile connettere un blocco di origine del flusso di dati a più blocchi di destinazione per creare una *rete del flusso di dati*. La versione sottoposta a overload del metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A> accetta un oggetto <xref:System.Predicate%601> mediante il quale viene definito se il blocco di destinazione accetta ogni messaggio in base al relativo valore. La maggior parte dei tipi di blocchi di flussi di dati utilizzati come origini offrono messaggi a tutti i blocchi di destinazione connessi, nell'ordine in cui sono stati collegati, finché uno dei blocchi non accetta il messaggio. Tramite questo meccanismo di filtro, è possibile creare sistemi di blocchi di flussi di dati connessi in cui determinati dati vengono indirizzati tramite un percorso mentre altri tramite un altro percorso. Per un esempio che usa il filtro per creare una rete del flusso di dati, vedere [Procedura dettagliata: Uso del flusso di dati in un'applicazione Windows Forms](walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## <a name="see-also"></a>Vedere anche

- [Flusso di dati](dataflow-task-parallel-library.md)

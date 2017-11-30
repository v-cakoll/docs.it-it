---
title: 'Procedura dettagliata: creazione di un tipo di blocco di flussi di dati personalizzato'
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
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, creating custom dataflow blocks
- dataflow blocks, creating custom in TPL
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 809b21fa6e1470890011604792d849998dd03ede
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-creating-a-custom-dataflow-block-type"></a>Procedura dettagliata: creazione di un tipo di blocco di flussi di dati personalizzato
Anche se la libreria di flussi di dati TPL fornisce vari tipi di blocchi di flussi di dati che consentono una varietà di funzionalità, è anche possibile creare tipi di blocco personalizzato. Questo documento viene descritto come creare un tipo di blocco del flusso di dati che implementa il comportamento personalizzato.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Lettura [flussi di dati](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) prima di leggere questo documento.  
  
> [!TIP]
>  La libreria del flusso di dati TPL (spazio dei nomi <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) non viene distribuita con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Per installare il <xref:System.Threading.Tasks.Dataflow> dello spazio dei nomi, Apri il progetto in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], scegliere **Gestisci pacchetti NuGet** dal menu progetto e cercare online il `Microsoft.Tpl.Dataflow` pacchetto.  
  
## <a name="defining-the-sliding-window-dataflow-block"></a>Definire il blocco di flussi di finestra temporale scorrevole  
 Si consideri un'applicazione del flusso di dati che richiede che i valori di input deve essere memorizzato nel buffer e quindi l'output in modo finestra temporale scorrevole. Per i valori di input {0, 1, 2, 3, 4, 5} e una dimensione della finestra di tre, ad esempio, un blocco di flussi di finestra temporale scorrevole produce le matrici di output {0, 1, 2}, {1, 2, 3}, {2, 3, 4} e {3, 4, 5}. Nelle sezioni seguenti vengono descritti due modi per creare un tipo di blocco del flusso di dati che implementa il comportamento personalizzato. La prima tecnica utilizza il <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> metodo per combinare le funzionalità di un <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> oggetto e un <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> oggetto all'interno del blocco di una propagazione. La seconda tecnica definisce una classe che deriva da <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> e combina le funzionalità esistenti per eseguire un comportamento personalizzato.  
  
## <a name="using-the-encapsulate-method-to-define-the-sliding-window-dataflow-block"></a>Utilizzando il metodo per definire il blocco di flussi di finestra temporale scorrevole di incapsulare  
 L'esempio seguente usa il <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> metodo per creare un blocco di propagazione da un'origine e una destinazione. Un blocco di propagazione consente a un blocco di origine e un blocco di destinazione di agire come un ricevitore e mittente dei dati.  
  
 Questa tecnica è utile quando è necessaria una funzionalità del flusso di dati personalizzato, ma non è necessario un tipo che fornisce i campi, proprietà o metodi aggiuntivi.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## <a name="deriving-from-ipropagatorblock-to-define-the-sliding-window-dataflow-block"></a>Derivazione da IPropagatorBlock per definire il blocco di flussi di finestra temporale scorrevole  
 Nell'esempio seguente la `SlidingWindowBlock` classe. Questa classe deriva da <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> in modo che possa fungere da un'origine e destinazione dei dati. Come nell'esempio precedente, la `SlidingWindowBlock` classe si basa su tipi di blocchi di flussi di dati esistente. Tuttavia, il `SlidingWindowBlock` implementa anche i metodi necessari per il <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, e <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> interfacce. Inoltrare tutti questi metodi funzionano per i membri di tipo blocco di flussi di dati predefiniti. Ad esempio, il `Post` metodo rinvia lavoro per il `m_target` membro dati, che è anche un <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> oggetto.  
  
 Questa tecnica è utile quando è necessaria una funzionalità di flussi di dati personalizzati e richiedono anche un tipo che fornisce i campi, proprietà o metodi aggiuntivi. Ad esempio, il `SlidingWindowBlock` deriva dalla classe <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601> in modo da poter fornire la <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> e <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A> metodi. Il `SlidingWindowBlock` classe viene inoltre illustrato estendibilità fornendo il `WindowSize` proprietà, che recupera il numero di elementi nella finestra temporale scorrevole.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## <a name="the-complete-example"></a>Esempio completo  
 Nell'esempio riportato di seguito viene illustrato il codice completo per questa procedura guidata. Viene inoltre illustrato come utilizzare gli entrambi blocchi finestra temporale scorrevole in un metodo che scrive il blocco, da cui viene letta e stampa i risultati alla console.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Copiare il codice di esempio e incollarlo in un progetto di Visual Studio oppure incollarlo in un file denominato `SlidingWindowBlock.cs` (`SlidingWindowBlock.vb` per [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), quindi eseguire il comando seguente in una finestra del prompt dei comandi di Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**  
  
## <a name="next-steps"></a>Passaggi successivi  
  
## <a name="see-also"></a>Vedere anche  
 [Flusso di dati](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)

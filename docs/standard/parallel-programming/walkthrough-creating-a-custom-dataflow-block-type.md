---
title: 'Procedura dettagliata: creazione di un tipo di blocco di flussi di dati personalizzato'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, creating custom dataflow blocks
- dataflow blocks, creating custom in TPL
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
ms.openlocfilehash: 37857e465bf4089dbeecc4cfd532d0702f795495
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284702"
---
# <a name="walkthrough-creating-a-custom-dataflow-block-type"></a>Procedura dettagliata: creazione di un tipo di blocco di flussi di dati personalizzato
Anche se la libreria di flussi di dati TPL rende disponibili diversi tipi di blocchi di flussi di dati che offrono varie funzionalità, è anche possibile creare tipi di blocchi personalizzati. Questo documento descrive come creare un tipo di blocco di flussi di dati che implementi un comportamento personalizzato.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Prima di questo documento, leggere [Flusso di dati](dataflow-task-parallel-library.md).  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="defining-the-sliding-window-dataflow-block"></a>Definizione del blocco di flussi di dati finestra temporale scorrevole  
 Si consideri un'applicazione di flusso di dati che richiede che i valori di input vengano memorizzati nel buffer e quindi che l'output di questi avvenga in modalità finestra temporale scorrevole. Per i valori di input {0, 1, 2, 3, 4, 5} e per una dimensione della finestra pari a tre, ad esempio, un blocco di flussi di dati finestra temporale scorrevole genera le matrici di output {0, 1, 2}, {1, 2, 3}, {2, 3, 4} e {3, 4, 5}. Le sezioni seguenti descrivono due modi per creare un tipo di blocco di flussi di dati che implementi questo comportamento personalizzato. La prima tecnica usa il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> per combinare le funzionalità di un oggetto <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> e di un oggetto <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> in un solo blocco di propagazione. La seconda tecnica definisce una classe che deriva da <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> e combina le funzionalità esistenti per eseguire il comportamento personalizzato.  
  
## <a name="using-the-encapsulate-method-to-define-the-sliding-window-dataflow-block"></a>Uso del metodo Encapsulate per definire il blocco di flussi di dati finestra temporale scorrevole  
 L'esempio seguente usa il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> per creare un blocco di propagazione da un'origine e da una destinazione. Un blocco di propagazione consente a un blocco di origine e a un blocco di destinazione di fungere da ricevitore e mittente di dati.  
  
 Questa tecnica è utile quando sono necessarie funzionalità di flusso di dati personalizzate, ma non è necessario un tipo che fornisca metodi, proprietà o campi aggiuntivi.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## <a name="deriving-from-ipropagatorblock-to-define-the-sliding-window-dataflow-block"></a>Definire il blocco di flussi di dati finestra temporale scorrevole tramite derivazione da IPropagatorBlock  
 L'esempio seguente illustra la classe `SlidingWindowBlock`. Questa classe deriva da <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602>, quindi può fungere sia da origine che da destinazione dei dati. Come nell'esempio precedente, la classe `SlidingWindowBlock` si basa su tipi di blocchi di flussi di dati esistenti. La classe `SlidingWindowBlock`, tuttavia, implementa anche i metodi necessari per le interfacce <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> e <xref:System.Threading.Tasks.Dataflow.IDataflowBlock>. Tutti questi metodi inoltrano lavoro ai membri di tipo blocco di flussi di dati predefiniti. Il metodo `Post`, ad esempio, rinvia il lavoro al membro dati `m_target`, che è anche un oggetto <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>.  
  
 Questa tecnica è utile quando sono necessarie funzionalità di flusso di dati personalizzate ed è necessario anche un tipo che fornisca metodi, proprietà o campi aggiuntivi. Anche la classe `SlidingWindowBlock`, ad esempio, deriva da <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601> e può quindi fornire i metodi <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> e <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A>. La classe `SlidingWindowBlock` illustra anche l'estendibilità tramite la proprietà `WindowSize`, che recupera il numero di elementi nella finestra temporale scorrevole.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## <a name="the-complete-example"></a>Esempio completo  
 Nell'esempio riportato di seguito viene illustrato il codice completo per questa procedura guidata. Viene anche illustrato come usare entrambi i blocchi di finestre temporali scorrevoli in un metodo che scrive nel blocco, legge da questo e stampa i risultati nella console.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## <a name="see-also"></a>Vedere anche

- [Flusso di dati](dataflow-task-parallel-library.md)

---
title: 'Procedura: scollegare i blocchi di flussi di dati'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow blocks, unlinking in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, unlinking dataflow blocks
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
ms.openlocfilehash: b49cfc9730ba154202baf15093a54ba3ce0e2a8a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139299"
---
# <a name="how-to-unlink-dataflow-blocks"></a>Procedura: scollegare i blocchi di flussi di dati
In questo documento viene descritto come scollegare un blocco di flussi di dati di destinazione dalla relativa origine.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono creati tre oggetti <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, tramite ognuno dei quali viene chiamato il metodo `TrySolution` per calcolare un valore. Per questo esempio è necessario solo il risultato della prima chiamata a `TrySolution` per il completamento.  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 Per ricevere il valore dal primo oggetto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> completato, nell'esempio viene definito il metodo `ReceiveFromAny(T)`. Il metodo `ReceiveFromAny(T)` accetta una matrice di oggetti <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> e tramite esso viene collegato ognuno di questi oggetti a un oggetto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>. Quando si utilizza il metodo <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> per collegare un blocco di flussi di dati di origine a un blocco di destinazione, tramite l'origine i messaggi vengono propagati nella destinazione quando i dati diventano disponibili. Poiché la classe <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> accetta solo il primo messaggio offerto, tramite il metodo `ReceiveFromAny(T)` viene generato il relativo risultato chiamando il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A>. In questo modo viene generato il primo messaggio offerto all'oggetto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>. Il metodo <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> ha una versione sottoposta a overload che accetta un oggetto <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions> con una proprietà <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions.MaxMessages> che, quando viene impostata su `1`, indica al blocco di origine di scollegarsi dalla destinazione dopo la ricezione di un messaggio dall'origine da parte della destinazione. È importante per l'oggetto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> scollegarsi dalle relative origini perché la relazione tra la matrice delle origini e l'oggetto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> non è più richiesta dopo la ricezione di un messaggio da parte dell'oggetto <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>.  
  
 Per abilitare il completamento delle chiamate rimanenti a `TrySolution` dopo che tramite una di esse viene calcolato un valore, il metodo `TrySolution` accetta un oggetto <xref:System.Threading.CancellationToken> che viene annullato dopo che la chiamata a `ReceiveFromAny(T)` ha restituito un valore. Tramite il metodo <xref:System.Threading.SpinWait.SpinUntil%2A> viene restituito un valore quando questo oggetto <xref:System.Threading.CancellationToken> viene annullato.  
  
## <a name="see-also"></a>Vedere anche

- [Flusso di dati](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)

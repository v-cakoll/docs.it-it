---
title: Cenni preliminari sul componente BackgroundWorker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- BackgroundWorker
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
ms.openlocfilehash: e91d74b7ca5515dd63ba17a9111cadf5090dae2a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046111"
---
# <a name="backgroundworker-component-overview"></a>Cenni preliminari sul componente BackgroundWorker
Molte operazioni comuni hanno tempi di esecuzione particolarmente lunghi, Ad esempio:  
  
- Download di immagini  
  
- Chiamate di servizi Web  
  
- Download e caricamento di file (anche per applicazioni peer-to-peer)  
  
- Calcoli locali complessi  
  
- Transazioni di database  
  
- Accesso locale ai dischi, a causa della velocità ridotta rispetto all'accesso alla memoria  
  
 Operazioni come queste possono causare il blocco dell'interfaccia utente mentre sono in esecuzione. Nel caso sia necessario eseguire operazioni di questo genere ma si vogliano evitare ritardi di risposta dell'interfaccia utente, il componente <xref:System.ComponentModel.BackgroundWorker> costituisce la soluzione ideale.  
  
 Il componente <xref:System.ComponentModel.BackgroundWorker> offre la possibilità di eseguire operazioni che richiedono molto tempo in modo asincrono (in background) su un thread diverso da quello usato dall'interfaccia utente principale dell'applicazione. Per usare un componente <xref:System.ComponentModel.BackgroundWorker>, è sufficiente indicare il metodo di lavoro da eseguire in background e quindi chiamare il metodo <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>. Il thread chiamante continua l'esecuzione normale mentre il metodo di lavoro viene eseguito in modo asincrono. Al completamento dell'esecuzione del metodo, il componente <xref:System.ComponentModel.BackgroundWorker> avvisa il thread chiamante attivando l'evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>, in cui è possibile includere i risultati dell'operazione.  
  
 Il <xref:System.ComponentModel.BackgroundWorker> componente è disponibile nella scheda **componenti** della **casella degli strumenti**. Per aggiungere un componente <xref:System.ComponentModel.BackgroundWorker> al form, trascina il componente <xref:System.ComponentModel.BackgroundWorker> nel form. Viene visualizzato nella barra dei componenti e le relative proprietà vengono visualizzate nella finestra **Proprietà** .  
  
 Per avviare l'operazione asincrona, usare il metodo <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>. Il metodo <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> accetta un parametro `object` facoltativo, che può essere usato per passare gli argomenti al metodo di lavoro. La classe <xref:System.ComponentModel.BackgroundWorker> espone l'evento <xref:System.ComponentModel.BackgroundWorker.DoWork> a cui viene collegato il thread di lavoro mediante un gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork>.  
  
 Il gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork> accetta un parametro <xref:System.ComponentModel.DoWorkEventArgs> che include una proprietà <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>. Questa proprietà riceve il parametro da <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> e può essere passata al metodo di lavoro, che verrà chiamato nel gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork>. L'esempio seguente illustra come assegnare un risultato proveniente da un metodo di lavoro denominato `ComputeFibonacci`. Fa parte di un esempio più ampio, che è possibile trovare in [procedura: Implementare un form che usa un'operazione](how-to-implement-a-form-that-uses-a-background-operation.md)in background.  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 Per altre informazioni sull'uso dei gestori eventi, vedere [eventi](../../../standard/events/index.md).  
  
> [!CAUTION]
> L'uso di qualsiasi tipo di multithreading determina la potenziale esposizione a bug seri e complessi. Vedere [Procedure consigliate per l'uso del threading gestito](../../../standard/threading/managed-threading-best-practices.md) prima di implementare soluzioni che usano il multithreading.  
  
 Per ulteriori informazioni sull'utilizzo della <xref:System.ComponentModel.BackgroundWorker> classe, vedere [procedura: Eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md).  
  
## <a name="see-also"></a>Vedere anche

- [Threading gestito](../../../standard/threading/index.md)
- [Panoramica sul modello asincrono basato su eventi](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [Procedura: Implementare un modulo che usa un'operazione in background](how-to-implement-a-form-that-uses-a-background-operation.md)

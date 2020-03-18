---
title: Ottimizzazione dell'applicazione asincrona (C#)
ms.date: 07/20/2015
ms.assetid: 97696eb9-81fc-4940-9655-84daa8eb4d5c
ms.openlocfilehash: cff50e62ff62b70e97e7ea6e03714326d774e407
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73970233"
---
# <a name="fine-tuning-your-async-application-c"></a>Ottimizzazione dell'applicazione asincrona (C#)
È possibile rendere più precise e flessibili le applicazioni asincrone usando le proprietà e i metodi resi disponibili dal tipo <xref:System.Threading.Tasks.Task>. Gli argomenti di questa sezione mostrano esempi che usano <xref:System.Threading.CancellationToken> e metodi `Task` importanti, ad esempio <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.  
  
 Usando `WhenAny` e `WhenAll`, è possibile avviare più attività e attenderne il completamento da una singola attività di monitoraggio in modo più facile.  
  
- `WhenAny` restituisce un'attività completata quando una qualsiasi attività in una raccolta viene completata.  
  
     Per esempi che usano `WhenAny`, vedere [Annullare le attività asincrone rimanenti dopo che ne è stata completata una (C#)](./cancel-remaining-async-tasks-after-one-is-complete.md) e [Avviare più attività asincrone ed elaborarle quando vengono completate (C#)](./start-multiple-async-tasks-and-process-them-as-they-complete.md).  
  
- `WhenAll` restituisce un'attività completata quando tutte le attività in una raccolta vengono completate.  
  
     Per ulteriori informazioni e `WhenAll`in un esempio in cui viene utilizzato , vedere [Come estendere la procedura dettagliata asincrona utilizzando Task.WhenAll (Cè)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).
  
 Questa sezione presenta i seguenti esempi.  
  
- [Annullare un'attività asincrona o un elenco di attività (C )](./cancel-an-async-task-or-a-list-of-tasks.md).  
  
- [Annullamento delle attività asincrone dopo un periodo di tempo (c'è)Cancel Async Tasks after a Period of Time (C](./cancel-async-tasks-after-a-period-of-time.md)  
  
- [Annullare le attività asincrone rimanenti dopo che ne è stata completata una (C#)](./cancel-remaining-async-tasks-after-one-is-complete.md)  
  
- [Avviare più attività asincrone ed elaborarle quando vengono completate (C#)](./start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
> Per eseguire gli esempi, è necessario avere installato Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive nel computer.  
  
 I progetti creano un'interfaccia utente che contiene un pulsante che consente di avviare il processo e un pulsante che consente di annullarlo, come illustrato nell'immagine seguente. I pulsanti sono denominati `startButton` e `cancelButton`.  
  
 ![Finestra WPF con pulsante Annulla](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Finestra di dialogo con un pulsante Start e Stop")  
  
 È possibile scaricare i progetti completi di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione).  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione asincrona con async e await (C#)](./index.md)

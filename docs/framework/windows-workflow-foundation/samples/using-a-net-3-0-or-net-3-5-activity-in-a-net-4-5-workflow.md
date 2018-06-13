---
title: Utilizzo di un'attività di .NET Framework 3.0 o .NET Framework 3.5 in un flusso di lavoro di .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
ms.openlocfilehash: ab2e93918617bd1ca21fb32878d446db0dd2ef16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514899"
---
# <a name="using-a-net-framework-30-or-net-framework-35-activity-in-a-net-framework-45-workflow"></a>Utilizzo di un'attività di .NET Framework 3.0 o .NET Framework 3.5 in un flusso di lavoro di .NET Framework 4.5
Il <xref:System.Activities.Statements.Interop> attività consente di eseguire un'attività di .NET Framework 3.0 Windows Workflow Foundation (WF) all'interno di un [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] flusso di lavoro. In questo esempio viene illustrato come usare l'attività <xref:System.Activities.Statements.Interop> per passare una stringa come argomento a un'attività [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] personalizzata.  
  
## <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  In [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] aprire il file della soluzione SimpleInterop.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere CTRL+F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## <a name="see-also"></a>Vedere anche

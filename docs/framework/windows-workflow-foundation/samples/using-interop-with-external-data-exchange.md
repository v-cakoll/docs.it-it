---
title: Utilizzo di interoperabilità con scambio di dati esterni
ms.date: 03/30/2017
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
ms.openlocfilehash: 9571a571137ff0a493be67ee9c607cd46dd47889
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515372"
---
# <a name="using-interop-with-external-data-exchange"></a>Utilizzo di interoperabilità con scambio di dati esterni
Il <xref:System.Activities.Statements.Interop> attività può essere usata per eseguire le attività da Windows Workflow Foundation (WF) in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] e [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3) e flussi di lavoro all'interno di Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4). In questo esempio viene illustrato come configurare ed eseguire un flusso di lavoro WF3 che usa <xref:System.Workflow.Activities.ExternalDataExchangeService> (e le attività personalizzate corrispondenti per i metodi di chiamata e di gestione degli eventi) tramite l'attività <xref:System.Activities.Statements.Interop> in un servizio flusso di lavoro WF4.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire il file ExternalDataExchange.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Per compilare l'esempio, premere CTRL+MAIUSC+B.  
  
3.  Premere F5 per eseguire l'esempio.

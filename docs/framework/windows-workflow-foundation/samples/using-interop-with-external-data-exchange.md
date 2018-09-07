---
title: Utilizzo di interoperabilità con scambio di dati esterni
ms.date: 03/30/2017
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
ms.openlocfilehash: 534321e5b5568e0dd0988333dc98ccc18ff33df8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44064813"
---
# <a name="using-interop-with-external-data-exchange"></a><span data-ttu-id="209b1-102">Utilizzo di interoperabilità con scambio di dati esterni</span><span class="sxs-lookup"><span data-stu-id="209b1-102">Using Interop with External Data Exchange</span></span>
<span data-ttu-id="209b1-103">Il <xref:System.Activities.Statements.Interop> attività può essere usata per eseguire le attività da Windows Workflow Foundation (WF) in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] e [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3) e flussi di lavoro all'interno di Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4).</span><span class="sxs-lookup"><span data-stu-id="209b1-103">The <xref:System.Activities.Statements.Interop> activity can be used to execute activities from Windows Workflow Foundation (WF) in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3), and workflows within Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4).</span></span> <span data-ttu-id="209b1-104">In questo esempio viene illustrato come configurare ed eseguire un flusso di lavoro WF3 che usa <xref:System.Workflow.Activities.ExternalDataExchangeService> (e le attività personalizzate corrispondenti per i metodi di chiamata e di gestione degli eventi) tramite l'attività <xref:System.Activities.Statements.Interop> in un servizio flusso di lavoro WF4.</span><span class="sxs-lookup"><span data-stu-id="209b1-104">This sample shows how to configure and run a WF3 workflow that uses <xref:System.Workflow.Activities.ExternalDataExchangeService> (and corresponding custom activities for calling methods and handling events) by using the <xref:System.Activities.Statements.Interop> activity in a WF4 workflow service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="209b1-105">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="209b1-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="209b1-106">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="209b1-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="209b1-107">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="209b1-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="209b1-108">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="209b1-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="209b1-109">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="209b1-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="209b1-110">Aprire il file ExternalDataExchange.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="209b1-110">Open the ExternalDataExchange.sln file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="209b1-111">Per compilare l'esempio, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="209b1-111">To build the sample, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="209b1-112">Premere F5 per eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="209b1-112">To run the sample, press F5.</span></span>

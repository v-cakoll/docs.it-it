---
title: Traccia del flusso di lavoro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4332b93175f4cb751ba88c7d2b05e4b462de7748
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="workflow-tracing"></a><span data-ttu-id="43f9a-102">Traccia del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="43f9a-102">Workflow Tracing</span></span>
<span data-ttu-id="43f9a-103">La traccia del flusso di lavoro consente di acquisire informazioni diagnostiche usando i listener di traccia di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="43f9a-103">Workflow tracing offers a way to capture diagnostic information using .NET Framework trace listeners.</span></span> <span data-ttu-id="43f9a-104">La traccia può essere abilitata in seguito al rilevamento di un problema con l'applicazione, quindi nuovamente disabilitata quando il problema viene risolto.</span><span class="sxs-lookup"><span data-stu-id="43f9a-104">Tracing can be enabled if a problem is detected with the application and then disabled again once the problem is resolved.</span></span> <span data-ttu-id="43f9a-105">Sono disponibili due modi per abilitare la traccia di debug per i flussi di lavoro:</span><span class="sxs-lookup"><span data-stu-id="43f9a-105">There are two ways you could enable debug tracing for workflows.</span></span> <span data-ttu-id="43f9a-106">è possibile configurarla usando il visualizzatore di Traccia eventi oppure usare l'oggetto <xref:System.Diagnostics> per inviare eventi di traccia a un file.</span><span class="sxs-lookup"><span data-stu-id="43f9a-106">You can configure it using the Event Trace viewer or you can use <xref:System.Diagnostics> to send trace events to a file.</span></span>  
  
## <a name="enabling-debug-tracing-in-etw"></a><span data-ttu-id="43f9a-107">Abilitazione della traccia di debug in ETW</span><span class="sxs-lookup"><span data-stu-id="43f9a-107">Enabling Debug Tracing in ETW</span></span>  
 <span data-ttu-id="43f9a-108">Per abilitare la traccia tramite ETW, abilitare il canale Debug in Visualizzatore eventi:</span><span class="sxs-lookup"><span data-stu-id="43f9a-108">To enable tracing using ETW, enable the Debug channel in Event Viewer:</span></span>  
  
1.  <span data-ttu-id="43f9a-109">Passare al nodo dei registri analitici e di debug in Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="43f9a-109">Navigate to analytic and debug logs node in Event Viewer.</span></span>  
  
2.  <span data-ttu-id="43f9a-110">Nella visualizzazione struttura ad albero in Visualizzatore eventi, passare a **Visualizzatore eventi -> applicazioni e servizi -> Microsoft -> Windows -> Server applicazioni-applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="43f9a-110">In the tree view in Event Viewer, navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="43f9a-111">Fare doppio clic su **Server applicazioni-applicazioni** e selezionare **Visualizza -> Visualizza registri analitici e Debug**.</span><span class="sxs-lookup"><span data-stu-id="43f9a-111">Right-click **Application Server-Applications** and select **View->Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="43f9a-112">Fare doppio clic su **Debug** e selezionare **Attiva registro**.</span><span class="sxs-lookup"><span data-stu-id="43f9a-112">Right-click **Debug** and select **Enable Log**.</span></span>  
  
3.  <span data-ttu-id="43f9a-113">Quando un flusso di lavoro esegue il debug e le tracce vengono create nel canale di debug ETW, queste ultime possono essere visualizzate in Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="43f9a-113">When a workflow runs the debug and traces are emitted to ETW debug channel, they can be viewed in the Event Viewer.</span></span> <span data-ttu-id="43f9a-114">Passare a **Visualizzatore eventi -> applicazioni e servizi -> Microsoft -> Windows -> Server applicazioni-applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="43f9a-114">Navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="43f9a-115">Fare doppio clic su **Debug** e selezionare **aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="43f9a-115">Right-click **Debug** and select **Refresh**.</span></span>  
  
4.  <span data-ttu-id="43f9a-116">La dimensione del buffer di traccia analitica predefinita è solo 4 kilobyte (KB). Si consiglia di aumentare la dimensione a 32 KB.</span><span class="sxs-lookup"><span data-stu-id="43f9a-116">The default analytic trace buffer size is only 4 kilobytes (KB); it is recommended to increase the size to 32 KB.</span></span> <span data-ttu-id="43f9a-117">A tale scopo, eseguire i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="43f9a-117">To do this, perform the following steps.</span></span>  
  
    1.  <span data-ttu-id="43f9a-118">Eseguire il comando seguente nella directory del framework corrente (ad esempio, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="43f9a-118">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
    2.  <span data-ttu-id="43f9a-119">Modifica il \<bufferSize > valore nel file Windows.ApplicationServer.Applications.man a 32.</span><span class="sxs-lookup"><span data-stu-id="43f9a-119">Change the \<bufferSize> value in the Windows.ApplicationServer.Applications.man file to 32.</span></span>  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3.  <span data-ttu-id="43f9a-120">Eseguire il comando seguente nella directory del framework corrente (ad esempio, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="43f9a-120">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43f9a-121">Se si utilizza .NET Framework 4 Client Profile, è innanzitutto necessario registrare il manifesto ETW eseguendo il comando seguente dalla directory di .NET Framework 4:`ServiceModelReg.exe –i –c:etw`</span><span class="sxs-lookup"><span data-stu-id="43f9a-121">If you are using the .NET Framework 4 Client Profile, you must first register the ETW manifest by running the following command from the .NET Framework 4 directory: `ServiceModelReg.exe –i –c:etw`</span></span>  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a><span data-ttu-id="43f9a-122">Abilitazione della traccia di debug tramite l'oggetto System.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="43f9a-122">Enabling Debug Tracing using System.Diagnostics</span></span>  
 <span data-ttu-id="43f9a-123">Questi listener possono essere configurati nel file App.config dell'applicazione flusso di lavoro o nel file Web.config per un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="43f9a-123">These listeners can be configured in the App.config file of the workflow application, or the Web.config for a workflow service.</span></span> <span data-ttu-id="43f9a-124">In questo esempio, un [TextWriterTraceListener](http://go.microsoft.com/fwlink/?LinkId=165424) è configurato per il salvataggio delle informazioni di traccia nel file MyTraceLog.txt nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="43f9a-124">In this example, a [TextWriterTraceListener](http://go.microsoft.com/fwlink/?LinkId=165424) is configured to save tracing information to the MyTraceLog.txt file in the current directory.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.Activities" switchValue="Information">  
        <listeners>  
          <add name="textListener" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"  
           type="System.Diagnostics.TextWriterTraceListener"  
           initializeData="MyTraceLog.txt"  
           traceOutputOptions="ProcessId, DateTime" />  
    </sharedListeners>  
    <trace autoflush="true" indentsize="4">  
      <listeners>  
        <add name="textListener" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="43f9a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43f9a-125">See Also</span></span>  
 [<span data-ttu-id="43f9a-126">Monitoraggio dell'infrastruttura di App di Windows Server</span><span class="sxs-lookup"><span data-stu-id="43f9a-126">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="43f9a-127">Monitoraggio delle applicazioni con App Fabric</span><span class="sxs-lookup"><span data-stu-id="43f9a-127">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)

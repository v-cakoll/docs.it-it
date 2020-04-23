---
title: 'Procedura: registrare informazioni sui servizi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoLog property
- services, logging information
- Windows Service applications, logging information about
- event logs, service applications
- application event logs, service applications
- logs, service applications
ms.assetid: c0d8140f-c055-4d8e-a2e0-37358a550116
author: ghogen
ms.openlocfilehash: 3c974d5a98f8056e45899b109878e5a28ab2938e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053613"
---
# <a name="how-to-log-information-about-services"></a><span data-ttu-id="9b025-102">Procedura: registrare informazioni sui servizi</span><span class="sxs-lookup"><span data-stu-id="9b025-102">How to: Log Information About Services</span></span>
<span data-ttu-id="9b025-103">Per impostazione predefinita, tutti i progetti di servizio di Windows possono interagire con il log eventi dell'applicazione in cui possono scrivere informazioni ed eccezioni.</span><span class="sxs-lookup"><span data-stu-id="9b025-103">By default, all Windows Service projects have the ability to interact with the Application event log and write information and exceptions to it.</span></span> <span data-ttu-id="9b025-104">È possibile usare la proprietà <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> per indicare se si vuole fornire questa funzionalità nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9b025-104">You use the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to indicate whether you want this functionality in your application.</span></span> <span data-ttu-id="9b025-105">Per impostazione predefinita, la registrazione è attivata per tutti i servizi creati con il modello di progetto di servizio di Windows.</span><span class="sxs-lookup"><span data-stu-id="9b025-105">By default, logging is turned on for any service you create with the Windows Service project template.</span></span> <span data-ttu-id="9b025-106">È possibile usare un form statico della classe <xref:System.Diagnostics.EventLog> per scrivere le informazioni sul servizio in un log senza dover creare un'istanza di un componente <xref:System.Diagnostics.EventLog> o registrare manualmente un'origine.</span><span class="sxs-lookup"><span data-stu-id="9b025-106">You can use a static form of the <xref:System.Diagnostics.EventLog> class to write service information to a log without having to create an instance of an <xref:System.Diagnostics.EventLog> component or manually register a source.</span></span>  
  
 <span data-ttu-id="9b025-107">Il programma di installazione del servizio registra automaticamente ogni servizio nel progetto come origine valida degli eventi con il registro applicazioni sul computer in cui è installato il servizio, quando la registrazione è attivata.</span><span class="sxs-lookup"><span data-stu-id="9b025-107">The installer for your service automatically registers each service in your project as a valid source of events with the Application log on the computer where the service is installed, when logging is turned on.</span></span> <span data-ttu-id="9b025-108">Il servizio registra informazioni ogni volta che viene avviato, arrestato, sospeso, riavviato, installato o disinstallato,</span><span class="sxs-lookup"><span data-stu-id="9b025-108">The service logs information each time the service is started, stopped, paused, resumed, installed, or uninstalled.</span></span> <span data-ttu-id="9b025-109">oltre a registrare tutti gli errori che si verificano.</span><span class="sxs-lookup"><span data-stu-id="9b025-109">It also logs any failures that occur.</span></span> <span data-ttu-id="9b025-110">Non è necessario scrivere nessun codice per scrivere voci nel registro quando si usa il comportamento predefinito, perché è il servizio a farlo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9b025-110">You do not need to write any code to write entries to the log when using the default behavior; the service handles this for you automatically.</span></span>  
  
 <span data-ttu-id="9b025-111">Per scrivere in un registro eventi diverso dal registro applicazioni, è necessario impostare la proprietà <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> su `false`, creare il proprio registro eventi personalizzato nel codice dei servizi e registrare il servizio come origine valida delle voci di tale log.</span><span class="sxs-lookup"><span data-stu-id="9b025-111">If you want to write to an event log other than the Application log, you must set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to `false`, create your own custom event log within your services code, and register your service as a valid source of entries for that log.</span></span> <span data-ttu-id="9b025-112">È quindi necessario scrivere il codice per registrare le voci nel log quando si verifica un'azione a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="9b025-112">You must then write code to record entries to the log whenever an action you're interested in occurs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b025-113">Se si usa un registro eventi personalizzato e si configura l'applicazione di servizio perché vi possa scrivere, è necessario non tentare di accedere al registro eventi prima di impostare la proprietà <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> del servizio nel codice.</span><span class="sxs-lookup"><span data-stu-id="9b025-113">If you use a custom event log and configure your service application to write to it, you must not attempt to access the event log before setting the service's <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property in your code.</span></span> <span data-ttu-id="9b025-114">Il registro eventi ha bisogno del valore di questa proprietà per registrare il servizio come origine valida degli eventi.</span><span class="sxs-lookup"><span data-stu-id="9b025-114">The event log needs this property's value to register your service as a valid source of events.</span></span>  
  
### <a name="to-enable-default-event-logging-for-your-service"></a><span data-ttu-id="9b025-115">Per abilitare la registrazione predefinita degli eventi per il servizio</span><span class="sxs-lookup"><span data-stu-id="9b025-115">To enable default event logging for your service</span></span>  
  
- <span data-ttu-id="9b025-116">Impostare la proprietà <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> del componente su `true`.</span><span class="sxs-lookup"><span data-stu-id="9b025-116">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property for your component to `true`.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9b025-117">Per impostazione predefinita, questa proprietà è impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="9b025-117">By default, this property is set to `true`.</span></span> <span data-ttu-id="9b025-118">Non è necessario impostarla esplicitamente a meno che non si debba eseguire un'elaborazione più complessa, ad esempio la valutazione di una condizione seguita dall'impostazione della proprietà <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> in base al risultato di tale condizione.</span><span class="sxs-lookup"><span data-stu-id="9b025-118">You do not need to set this explicitly unless you are building more complex processing, such as evaluating a condition and then setting the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property based on the result of that condition.</span></span>  
  
### <a name="to-disable-event-logging-for-your-service"></a><span data-ttu-id="9b025-119">Per disabilitare la registrazione degli eventi per il servizio</span><span class="sxs-lookup"><span data-stu-id="9b025-119">To disable event logging for your service</span></span>  
  
- <span data-ttu-id="9b025-120">Impostare la proprietà <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> del componente su `false`.</span><span class="sxs-lookup"><span data-stu-id="9b025-120">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property for your component to `false`.</span></span>  
  
     [!code-csharp[VbRadconService#17](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#17)]
     [!code-vb[VbRadconService#17](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#17)]  
  
### <a name="to-set-up-logging-to-a-custom-log"></a><span data-ttu-id="9b025-121">Per configurare la registrazione in un log personalizzato</span><span class="sxs-lookup"><span data-stu-id="9b025-121">To set up logging to a custom log</span></span>  
  
1. <span data-ttu-id="9b025-122">Impostare la proprietà <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="9b025-122">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to `false`.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9b025-123">È necessario impostare <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> su false per usare un log personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9b025-123">You must set <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> to false in order to use a custom log.</span></span>  
  
2. <span data-ttu-id="9b025-124">Configurare un'istanza di un componente <xref:System.Diagnostics.EventLog> nell'applicazione di servizio di Windows.</span><span class="sxs-lookup"><span data-stu-id="9b025-124">Set up an instance of an <xref:System.Diagnostics.EventLog> component in your Windows Service application.</span></span>  
  
3. <span data-ttu-id="9b025-125">Creare un log personalizzato chiamando il metodo <xref:System.Diagnostics.EventLog.CreateEventSource%2A> e specificando la stringa di origine e il nome del file di log che si vuole creare.</span><span class="sxs-lookup"><span data-stu-id="9b025-125">Create a custom log by calling the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method and specifying the source string and the name of the log file you want to create.</span></span>  
  
4. <span data-ttu-id="9b025-126">Impostare la proprietà <xref:System.Diagnostics.EventLog.Source%2A> sull'istanza del componente <xref:System.Diagnostics.EventLog> per la stringa di origine creata nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="9b025-126">Set the <xref:System.Diagnostics.EventLog.Source%2A> property on the <xref:System.Diagnostics.EventLog> component instance to the source string you created in step 3.</span></span>  
  
5. <span data-ttu-id="9b025-127">Scrivere le voci accedendo al metodo <xref:System.Diagnostics.EventLog.WriteEntry%2A> nell'istanza del componente <xref:System.Diagnostics.EventLog> .</span><span class="sxs-lookup"><span data-stu-id="9b025-127">Write your entries by accessing the <xref:System.Diagnostics.EventLog.WriteEntry%2A> method on the <xref:System.Diagnostics.EventLog> component instance.</span></span>  
  
     <span data-ttu-id="9b025-128">Il codice seguente illustra come configurare la registrazione in un log personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9b025-128">The following code shows how to set up logging to a custom log.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9b025-129">In questo esempio di codice un'istanza di un componente <xref:System.Diagnostics.EventLog> è denominata `eventLog1` (`EventLog1` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="9b025-129">In this code example, an instance of an <xref:System.Diagnostics.EventLog> component is named `eventLog1` (`EventLog1` in Visual Basic).</span></span> <span data-ttu-id="9b025-130">Se si è creata un'istanza con un altro nome nel passaggio 2, modificare il codice di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="9b025-130">If you created an instance with another name in step 2, change the code accordingly.</span></span>  
  
     [!code-csharp[VbRadconService#14](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#14)]
     [!code-vb[VbRadconService#14](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#14)]  
    [!code-csharp[VbRadconService#15](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#15)]
    [!code-vb[VbRadconService#15](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="9b025-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b025-131">See also</span></span>

- [<span data-ttu-id="9b025-132">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="9b025-132">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)

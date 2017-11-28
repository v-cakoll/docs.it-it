---
title: 'Procedura: scrivere nel log eventi di un''applicazione (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Computer.EventLog element
- WriteEntry method [Visual Basic]
- My.Computer.EventLog element
- event logs, writing to
ms.assetid: cadbc8c1-87af-4746-934e-55b79a4f6e2b
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 018aff8dc130bfe7217c861a7d7bc8ae275ccc66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-to-an-application-event-log-visual-basic"></a><span data-ttu-id="016e6-102">Procedura: scrivere nel log eventi di un'applicazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="016e6-102">How to: Write to an Application Event Log (Visual Basic)</span></span>
<span data-ttu-id="016e6-103">È possibile usare gli oggetti `My.Application.Log` e `My.Log` per scrivere informazioni sugli eventi che si verificano nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="016e6-103">You can use the `My.Application.Log` and `My.Log` objects to write information about events that occur in your application.</span></span> <span data-ttu-id="016e6-104">L'esempio seguente mostra come configurare un listener di log eventi in modo che `My.Application.Log` scriva le informazioni di traccia nel log eventi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="016e6-104">This example shows how to configure an event log listener so `My.Application.Log` writes tracing information to the Application event log.</span></span>  
  
 <span data-ttu-id="016e6-105">Non è possibile scrivere nel log di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="016e6-105">You cannot write to the Security log.</span></span> <span data-ttu-id="016e6-106">Per scrivere nel log di sistema, è necessario essere membro dell'account LocalSystem o Administrator.</span><span class="sxs-lookup"><span data-stu-id="016e6-106">In order to write to the System log, you must be a member of the LocalSystem or Administrator account.</span></span>  
  
 <span data-ttu-id="016e6-107">Per visualizzare un log eventi, è possibile usare **Esplora server** o **Visualizzatore eventi di Windows**.</span><span class="sxs-lookup"><span data-stu-id="016e6-107">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="016e6-108">Per altre informazioni, vedere [ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299).</span><span class="sxs-lookup"><span data-stu-id="016e6-108">For more information, see [ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="016e6-109">I log eventi non sono supportati in Windows 95, Windows 98 o Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="016e6-109">Event logs are not supported on Windows 95, Windows 98, or Windows Millennium Edition.</span></span>  
  
### <a name="to-add-and-configure-the-event-log-listener"></a><span data-ttu-id="016e6-110">Per aggiungere e configurare il listener di log eventi</span><span class="sxs-lookup"><span data-stu-id="016e6-110">To add and configure the event log listener</span></span>  
  
1.  <span data-ttu-id="016e6-111">Fare clic con il pulsante destro del mouse sul file app.config in **Esplora soluzioni** , quindi scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="016e6-111">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="016e6-112">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="016e6-112">\- or -</span></span>  
  
     <span data-ttu-id="016e6-113">Se non è presente alcun file app.config:</span><span class="sxs-lookup"><span data-stu-id="016e6-113">If there is no app.config file,</span></span>  
  
    1.  <span data-ttu-id="016e6-114">Scegliere **Aggiungi nuovo elemento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="016e6-114">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="016e6-115">Nella finestra di dialogo **Aggiungi nuovo elemento** scegliere **File di configurazione dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="016e6-115">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="016e6-116">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="016e6-116">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="016e6-117">Individuare la sezione `<listeners>` nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="016e6-117">Locate the `<listeners>` section in the application configuration file.</span></span>  
  
     <span data-ttu-id="016e6-118">La sezione `<listeners>` si trova nella sezione `<source>` con l'attributo del nome "DefaultSource" annidato sotto la sezione `<system.diagnostics>` a sua volta annidata sotto la sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="016e6-118">You will find the `<listeners>` section in the `<source>` section with the name attribute "DefaultSource", which is nested under the `<system.diagnostics>` section, which is nested under the top-level `<configuration>` section.</span></span>  
  
3.  <span data-ttu-id="016e6-119">Aggiungere l'elemento seguente alla sezione `<listeners>` :</span><span class="sxs-lookup"><span data-stu-id="016e6-119">Add this element to that `<listeners>` section:</span></span>  
  
    ```xml  
    <add name="EventLog"/>  
    ```  
  
4.  <span data-ttu-id="016e6-120">Individuare la sezione `<sharedListeners>` nella sezione `<system.diagnostics>` all'interno della sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="016e6-120">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
5.  <span data-ttu-id="016e6-121">Aggiungere l'elemento seguente alla sezione `<sharedListeners>` :</span><span class="sxs-lookup"><span data-stu-id="016e6-121">Add this element to that `<sharedListeners>` section:</span></span>  
  
    ```xml  
    <add name="EventLog"  
        type="System.Diagnostics.EventLogTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
         initializeData="APPLICATION_NAME"/>  
    ```  
  
     <span data-ttu-id="016e6-122">Sostituire `APPLICATION_NAME` con il nome dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="016e6-122">Replace `APPLICATION_NAME` with the name of your application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="016e6-123">In genere, nel log eventi vengono scritti solo gli errori.</span><span class="sxs-lookup"><span data-stu-id="016e6-123">Typically, an application writes only errors to the event log.</span></span> <span data-ttu-id="016e6-124">Per informazioni sull'applicazione dei filtri all'output dei log, vedere [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="016e6-124">For information on filtering log output, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>  
  
### <a name="to-write-event-information-to-the-event-log"></a><span data-ttu-id="016e6-125">Per scrivere informazioni sugli eventi nel log eventi</span><span class="sxs-lookup"><span data-stu-id="016e6-125">To write event information to the event log</span></span>  
  
-   <span data-ttu-id="016e6-126">Usare il metodo `My.Application.Log.WriteEntry` o `My.Application.Log.WriteException` per scrivere le informazioni nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="016e6-126">Use the `My.Application.Log.WriteEntry` or `My.Application.Log.WriteException` method to write information to the event log.</span></span> <span data-ttu-id="016e6-127">Per altre informazioni, vedere [Procedura: Scrivere messaggi di log ](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) e [Procedura: Registrare eccezioni](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="016e6-127">For more information, see [How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) and [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span></span>  
  
     <span data-ttu-id="016e6-128">Dopo aver configurato il listener del log eventi per un assembly, vengono ricevuti tutti i messaggi che `My.Applcation.Log` scrive da tale assembly.</span><span class="sxs-lookup"><span data-stu-id="016e6-128">After you configure the event log listener for an assembly, it receives all messages that `My.Applcation.Log` writes from that assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="016e6-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="016e6-129">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>  
 [<span data-ttu-id="016e6-130">Utilizzo dei log applicazione</span><span class="sxs-lookup"><span data-stu-id="016e6-130">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [<span data-ttu-id="016e6-131">Procedura: Registrare eccezioni</span><span class="sxs-lookup"><span data-stu-id="016e6-131">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)  
 [<span data-ttu-id="016e6-132">Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="016e6-132">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)

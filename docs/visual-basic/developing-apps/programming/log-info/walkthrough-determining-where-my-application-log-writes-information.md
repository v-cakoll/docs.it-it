---
title: Individuazione della posizione di inserimento delle informazioni con My.Application.Log
ms.date: 07/20/2015
helpviewer_keywords:
- My.Log object, output location
- output, application log location
- My.Application.Log object, output location
- event logs, determining output location
- application event logs, output location
- applications [Visual Basic], output location
ms.assetid: 5b70143a-7741-45f2-ae1d-03324a3a4189
ms.openlocfilehash: f3fd0ed0388276f1400bf77d0abfb488634a45a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74353611"
---
# <a name="walkthrough-determining-where-myapplicationlog-writes-information-visual-basic"></a><span data-ttu-id="516e3-102">Procedura dettagliata: individuazione della posizione di inserimento delle informazioni con My.Application.Log (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="516e3-102">Walkthrough: Determining Where My.Application.Log Writes Information (Visual Basic)</span></span>

<span data-ttu-id="516e3-103">L'oggetto `My.Application.Log` può scrivere le informazioni in diversi listener di log.</span><span class="sxs-lookup"><span data-stu-id="516e3-103">The `My.Application.Log` object can write information to several log listeners.</span></span> <span data-ttu-id="516e3-104">I listener di log sono configurati dal file di configurazione del computer ed è possibile eseguirne l'override con il file di configurazione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="516e3-104">The log listeners are configured by the computer's configuration file and can be overridden by an application's configuration file.</span></span> <span data-ttu-id="516e3-105">Questo argomento descrive le impostazioni predefinite e illustra come determinare le impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="516e3-105">This topic describes the default settings and how to determine the settings for your application.</span></span>

<span data-ttu-id="516e3-106">Per altre informazioni sui percorsi di output predefiniti, vedere [Utilizzo dei log applicazione](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="516e3-106">For more information about the default output locations, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>

### <a name="to-determine-the-listeners-for-myapplicationlog"></a><span data-ttu-id="516e3-107">Per determinare i listener per My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="516e3-107">To determine the listeners for My.Application.Log</span></span>

1. <span data-ttu-id="516e3-108">Individuare il file di configurazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="516e3-108">Locate the assembly's configuration file.</span></span> <span data-ttu-id="516e3-109">Se si sta sviluppando l'assembly, è possibile accedere al file app.config in Visual Studio da **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="516e3-109">If you are developing the assembly, you can access the app.config in Visual Studio from the **Solution Explorer**.</span></span> <span data-ttu-id="516e3-110">In caso contrario, il nome del file di configurazione sarà il nome dell'assembly seguito da ".config" e si troverà nella stessa directory dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="516e3-110">Otherwise, the configuration file name is the assembly's name appended with ".config", and it is located in the same directory as the assembly.</span></span>

    > [!NOTE]
    > <span data-ttu-id="516e3-111">Non tutti gli assembly hanno un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="516e3-111">Not every assembly has a configuration file.</span></span>

    <span data-ttu-id="516e3-112">Il file di configurazione è un file XML.</span><span class="sxs-lookup"><span data-stu-id="516e3-112">The configuration file is an XML file.</span></span>

2. <span data-ttu-id="516e3-113">Individuare la sezione `<listeners>` all'interno della sezione `<source>` con l'attributo `name` "DefaultSource" che si trova nella sezione `<sources>` .</span><span class="sxs-lookup"><span data-stu-id="516e3-113">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="516e3-114">La sezione `<sources>` si trova nella sezione `<system.diagnostics>` all'interno della sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="516e3-114">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

    <span data-ttu-id="516e3-115">Se queste sezioni non esistono, è possibile configurare i listener di log `My.Application.Log` nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="516e3-115">If these sections do not exist, then the computer's configuration file may configure the `My.Application.Log` log listeners.</span></span> <span data-ttu-id="516e3-116">I passaggi seguenti descrivono come determinare ciò che viene definito dal file di configurazione del computer:</span><span class="sxs-lookup"><span data-stu-id="516e3-116">The following steps describe how to determine what the computer configuration file defines:</span></span>

    1. <span data-ttu-id="516e3-117">Individuare il file machine.config del computer.</span><span class="sxs-lookup"><span data-stu-id="516e3-117">Locate the computer's machine.config file.</span></span> <span data-ttu-id="516e3-118">Il file si trova in genere nella directory *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* dove `SystemRoot` è la directory del sistema operativo e `frameworkVersion` è la versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="516e3-118">Typically, it is located in the *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* directory, where `SystemRoot` is the operating system directory, and `frameworkVersion` is the version of the .NET Framework.</span></span>

        <span data-ttu-id="516e3-119">È possibile eseguire l'override delle impostazioni del file machine.config con il file di configurazione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="516e3-119">The settings in machine.config can be overridden by an application's configuration file.</span></span>

        <span data-ttu-id="516e3-120">Se gli elementi facoltativi seguenti non esistono, è possibile crearli.</span><span class="sxs-lookup"><span data-stu-id="516e3-120">If the optional elements listed below do not exist, you can create them.</span></span>

    2. <span data-ttu-id="516e3-121">Individuare la sezione `<listeners>` all'interno della sezione `<source>` con l'attributo `name` "DefaultSource" che si trova nella sezione `<sources>` all'interno della sezione `<system.diagnostics>` nella sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="516e3-121">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", in the `<sources>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

        <span data-ttu-id="516e3-122">Se queste sezioni non esistono, `My.Application.Log` conterrà solo i listener di log predefiniti.</span><span class="sxs-lookup"><span data-stu-id="516e3-122">If these sections do not exist, then the `My.Application.Log` has only the default log listeners.</span></span>

3. <span data-ttu-id="516e3-123">Individuare gli elementi <`add>` nella sezione <`listeners>`.</span><span class="sxs-lookup"><span data-stu-id="516e3-123">Locate the <`add>` elements in the <`listeners>` section.</span></span>

     <span data-ttu-id="516e3-124">Questi elementi consentono di aggiungere i listener di log denominati all'origine `My.Application.Log` .</span><span class="sxs-lookup"><span data-stu-id="516e3-124">These elements add the named log listeners to `My.Application.Log` source.</span></span>

4. <span data-ttu-id="516e3-125">Individuare gli elementi `<add>` con i nomi dei listener di log nella sezione `<sharedListeners>` all'interno della sezione `<system.diagnostics>` nella sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="516e3-125">Locate the `<add>` elements with the names of the log listeners in the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

5. <span data-ttu-id="516e3-126">Per molti tipi di listener condivisi, i dati di inizializzazione del listener includono una descrizione della posizione in cui il listener indirizza i dati:</span><span class="sxs-lookup"><span data-stu-id="516e3-126">For many types of shared listeners, the listener's initialization data includes a description of where the listener directs the data:</span></span>

    - <span data-ttu-id="516e3-127">Il listener <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> scrive le informazioni in un log file, come descritto nell'introduzione.</span><span class="sxs-lookup"><span data-stu-id="516e3-127">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> listener writes to a file log, as described in the introduction.</span></span>

    - <span data-ttu-id="516e3-128">Il listener <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> scrive le informazioni nel log eventi del computer specificato dal parametro `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="516e3-128">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> listener writes information to the computer event log specified by the `initializeData` parameter.</span></span> <span data-ttu-id="516e3-129">Per visualizzare un log eventi, è possibile usare **Esplora server** o **Visualizzatore eventi di Windows**.</span><span class="sxs-lookup"><span data-stu-id="516e3-129">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="516e3-130">Per altre informazioni, vedere l'articolo relativo agli [eventi ETW in .NET Framework](../../../../framework/performance/etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="516e3-130">For more information, see [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).</span></span>

    - <span data-ttu-id="516e3-131">I listener <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> e <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> scrivono le informazioni nel file specificato nel parametro `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="516e3-131">The <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> and <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> listeners write to the file specified in the `initializeData` parameter.</span></span>

    - <span data-ttu-id="516e3-132">Il listener <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> scrive le informazioni nella console della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="516e3-132">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> listener writes to the command-line console.</span></span>

    - <span data-ttu-id="516e3-133">Per sapere dove gli altri tipi di listener di log scrivono le informazioni, consultare la documentazione relativa al tipo di listener desiderato.</span><span class="sxs-lookup"><span data-stu-id="516e3-133">For information about where other types of log listeners write information, consult that type's documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="516e3-134">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="516e3-134">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.DelimitedListTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics>
- [<span data-ttu-id="516e3-135">Utilizzo dei log applicazione</span><span class="sxs-lookup"><span data-stu-id="516e3-135">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="516e3-136">Procedura: Registrare eccezioni</span><span class="sxs-lookup"><span data-stu-id="516e3-136">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [<span data-ttu-id="516e3-137">Procedura: Scrivere messaggi di log</span><span class="sxs-lookup"><span data-stu-id="516e3-137">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)
- [<span data-ttu-id="516e3-138">Procedura dettagliata: Modifica della posizione di inserimento delle informazioni con My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="516e3-138">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
- [<span data-ttu-id="516e3-139">ETW Events in the .NET Framework</span><span class="sxs-lookup"><span data-stu-id="516e3-139">ETW Events in the .NET Framework</span></span>](../../../../framework/performance/etw-events.md)
- [<span data-ttu-id="516e3-140">Risoluzione dei problemi: Listener di log</span><span class="sxs-lookup"><span data-stu-id="516e3-140">Troubleshooting: Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)

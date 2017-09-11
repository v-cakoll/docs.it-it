---
title: Individuazione della posizione di inserimento delle informazioni con My.Application.Log (Visual Basic)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Log object, output location
- output, application log location
- My.Application.Log object, outpout location
- event logs, determining output location
- application event logs, output location
- applications [Visual Basic], output location
ms.assetid: 5b70143a-7741-45f2-ae1d-03324a3a4189
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 36c91f607a5a9d0dcf65ee6e049b9a49cdd37929
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-determining-where-myapplicationlog-writes-information-visual-basic"></a><span data-ttu-id="18bc0-102">Procedura dettagliata: individuazione della posizione di inserimento delle informazioni con My.Application.Log (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18bc0-102">Walkthrough: Determining Where My.Application.Log Writes Information (Visual Basic)</span></span>
<span data-ttu-id="18bc0-103">L'oggetto `My.Application.Log` può scrivere le informazioni in diversi listener di log.</span><span class="sxs-lookup"><span data-stu-id="18bc0-103">The `My.Application.Log` object can write information to several log listeners.</span></span> <span data-ttu-id="18bc0-104">I listener di log sono configurati dal file di configurazione del computer ed è possibile eseguirne l'override con il file di configurazione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="18bc0-104">The log listeners are configured by the computer's configuration file and can be overridden by an application's configuration file.</span></span> <span data-ttu-id="18bc0-105">Questo argomento descrive le impostazioni predefinite e illustra come determinare le impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="18bc0-105">This topic describes the default settings and how to determine the settings for your application.</span></span>  
  
 <span data-ttu-id="18bc0-106">Per altre informazioni sui percorsi di output predefiniti, vedere [Utilizzo dei log applicazione](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="18bc0-106">For more information about the default output locations, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>  
  
### <a name="to-determine-the-listeners-for-myapplicationlog"></a><span data-ttu-id="18bc0-107">Per determinare i listener per My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="18bc0-107">To determine the listeners for My.Application.Log</span></span>  
  
1.  <span data-ttu-id="18bc0-108">Individuare il file di configurazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="18bc0-108">Locate the assembly's configuration file.</span></span> <span data-ttu-id="18bc0-109">Se si sta sviluppando l'assembly, è possibile accedere al file app.config in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] da **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="18bc0-109">If you are developing the assembly, you can access the app.config in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] from the **Solution Explorer**.</span></span> <span data-ttu-id="18bc0-110">In caso contrario, il nome del file di configurazione sarà il nome dell'assembly seguito da ".config" e si troverà nella stessa directory dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="18bc0-110">Otherwise, the configuration file name is the assembly's name appended with ".config", and it is located in the same directory as the assembly.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="18bc0-111">Non tutti gli assembly hanno un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="18bc0-111">Not every assembly has a configuration file.</span></span>  
  
     <span data-ttu-id="18bc0-112">Il file di configurazione è un file XML.</span><span class="sxs-lookup"><span data-stu-id="18bc0-112">The configuration file is an XML file.</span></span>  
  
2.  <span data-ttu-id="18bc0-113">Individuare la sezione `<listeners>` all'interno della sezione `<source>` con l'attributo `name` "DefaultSource" che si trova nella sezione `<sources>` .</span><span class="sxs-lookup"><span data-stu-id="18bc0-113">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="18bc0-114">La sezione `<sources>` si trova nella sezione `<system.diagnostics>` all'interno della sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="18bc0-114">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
     <span data-ttu-id="18bc0-115">Se queste sezioni non esistono, è possibile configurare i listener di log `My.Application.Log` nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="18bc0-115">If these sections do not exist, then the computer's configuration file may configure the `My.Application.Log` log listeners.</span></span> <span data-ttu-id="18bc0-116">I passaggi seguenti descrivono come determinare ciò che viene definito dal file di configurazione del computer:</span><span class="sxs-lookup"><span data-stu-id="18bc0-116">The following steps describe how to determine what the computer configuration file defines:</span></span>  
  
    1.  <span data-ttu-id="18bc0-117">Individuare il file machine.config del computer.</span><span class="sxs-lookup"><span data-stu-id="18bc0-117">Locate the computer's machine.config file.</span></span> <span data-ttu-id="18bc0-118">Il file si trova in genere nella directory *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* , dove `SystemRoot` è la directory del sistema operativo e `frameworkVersion` è la versione di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18bc0-118">Typically, it is located in the *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* directory, where `SystemRoot` is the operating system directory, and `frameworkVersion` is the version of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
         <span data-ttu-id="18bc0-119">È possibile eseguire l'override delle impostazioni del file machine.config con il file di configurazione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="18bc0-119">The settings in machine.config can be overridden by an application's configuration file.</span></span>  
  
         <span data-ttu-id="18bc0-120">Se gli elementi facoltativi seguenti non esistono, è possibile crearli.</span><span class="sxs-lookup"><span data-stu-id="18bc0-120">If the optional elements listed below do not exist, you can create them.</span></span>  
  
    2.  <span data-ttu-id="18bc0-121">Individuare la sezione `<listeners>` all'interno della sezione `<source>` con l'attributo `name` "DefaultSource" che si trova nella sezione `<sources>` all'interno della sezione `<system.diagnostics>` nella sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="18bc0-121">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", in the `<sources>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
         <span data-ttu-id="18bc0-122">Se queste sezioni non esistono, `My.Application.Log` conterrà solo i listener di log predefiniti.</span><span class="sxs-lookup"><span data-stu-id="18bc0-122">If these sections do not exist, then the `My.Application.Log` has only the default log listeners.</span></span>  
  
3.  <span data-ttu-id="18bc0-123">Individuare gli elementi <`add>` nella sezione <`listeners>`.</span><span class="sxs-lookup"><span data-stu-id="18bc0-123">Locate the <`add>` elements in the <`listeners>` section.</span></span>  
  
     <span data-ttu-id="18bc0-124">Questi elementi consentono di aggiungere i listener di log denominati all'origine `My.Application.Log` .</span><span class="sxs-lookup"><span data-stu-id="18bc0-124">These elements add the named log listeners to `My.Application.Log` source.</span></span>  
  
4.  <span data-ttu-id="18bc0-125">Individuare gli elementi `<add>` con i nomi dei listener di log nella sezione `<sharedListeners>` all'interno della sezione `<system.diagnostics>` nella sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="18bc0-125">Locate the `<add>` elements with the names of the log listeners in the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
5.  <span data-ttu-id="18bc0-126">Per molti tipi di listener condivisi, i dati di inizializzazione del listener includono una descrizione della posizione in cui il listener indirizza i dati:</span><span class="sxs-lookup"><span data-stu-id="18bc0-126">For many types of shared listeners, the listener's initialization data includes a description of where the listener directs the data:</span></span>  
  
    -   <span data-ttu-id="18bc0-127">Il listener <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName> scrive le informazioni in un log file, come descritto nell'introduzione.</span><span class="sxs-lookup"><span data-stu-id="18bc0-127">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName> listener writes to a file log, as described in the introduction.</span></span>  
  
    -   <span data-ttu-id="18bc0-128">Il listener <xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName> scrive le informazioni nel log eventi del computer specificato dal parametro `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="18bc0-128">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName> listener writes information to the computer event log specified by the `initializeData` parameter.</span></span> <span data-ttu-id="18bc0-129">Per visualizzare un log eventi, è possibile usare **Esplora server** o **Visualizzatore eventi di Windows**.</span><span class="sxs-lookup"><span data-stu-id="18bc0-129">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="18bc0-130">Per altre informazioni, vedere [ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299).</span><span class="sxs-lookup"><span data-stu-id="18bc0-130">For more information, see [ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299).</span></span>  
  
    -   <span data-ttu-id="18bc0-131">I listener <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName> e <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName> scrivono le informazioni nel file specificato nel parametro `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="18bc0-131">The <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName> and <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName> listeners write to the file specified in the `initializeData` parameter.</span></span>  
  
    -   <span data-ttu-id="18bc0-132">Il listener <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName> scrive le informazioni nella console della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="18bc0-132">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName> listener writes to the command-line console.</span></span>  
  
    -   <span data-ttu-id="18bc0-133">Per sapere dove gli altri tipi di listener di log scrivono le informazioni, consultare la documentazione relativa al tipo di listener desiderato.</span><span class="sxs-lookup"><span data-stu-id="18bc0-133">For information about where other types of log listeners write information, consult that type's documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18bc0-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18bc0-134">See Also</span></span>  
 <span data-ttu-id="18bc0-135"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="18bc0-135"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="18bc0-136"><xref:System.Diagnostics.DefaultTraceListener></span><span class="sxs-lookup"><span data-stu-id="18bc0-136"><xref:System.Diagnostics.DefaultTraceListener></span></span>   
 <span data-ttu-id="18bc0-137"><xref:System.Diagnostics.EventLogTraceListener></span><span class="sxs-lookup"><span data-stu-id="18bc0-137"><xref:System.Diagnostics.EventLogTraceListener></span></span>   
 <span data-ttu-id="18bc0-138"><xref:System.Diagnostics.DelimitedListTraceListener></span><span class="sxs-lookup"><span data-stu-id="18bc0-138"><xref:System.Diagnostics.DelimitedListTraceListener></span></span>   
 <span data-ttu-id="18bc0-139"><xref:System.Diagnostics.XmlWriterTraceListener></span><span class="sxs-lookup"><span data-stu-id="18bc0-139"><xref:System.Diagnostics.XmlWriterTraceListener></span></span>   
 <span data-ttu-id="18bc0-140"><xref:System.Diagnostics.ConsoleTraceListener></span><span class="sxs-lookup"><span data-stu-id="18bc0-140"><xref:System.Diagnostics.ConsoleTraceListener></span></span>   
 <span data-ttu-id="18bc0-141"><xref:System.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="18bc0-141"><xref:System.Diagnostics></span></span>   
 <span data-ttu-id="18bc0-142">[Utilizzo dei log applicazione](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="18bc0-142">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 <span data-ttu-id="18bc0-143">[Procedura: Registrare eccezioni](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="18bc0-143">[How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span></span>  
 <span data-ttu-id="18bc0-144">[Procedura: Scrivere messaggi di log](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span><span class="sxs-lookup"><span data-stu-id="18bc0-144">[How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span></span>  
 <span data-ttu-id="18bc0-145">[Procedura dettagliata: Modifica della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="18bc0-145">[Walkthrough: Changing Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span></span>  
 <span data-ttu-id="18bc0-146">[ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299)  (Eventi ETW in .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="18bc0-146">[ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299) </span></span>  
 [<span data-ttu-id="18bc0-147">Risoluzione dei problemi: Listener di log</span><span class="sxs-lookup"><span data-stu-id="18bc0-147">Troubleshooting: Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)


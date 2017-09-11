---
title: Filtro dell'output di My.Application.Log (Visual Basic)
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
- My.Log object, filtering output
- My.Application.Log object, filtering output
- application event logs, output filtering
ms.assetid: 2c0a457a-38a4-49e1-934d-a51320b7b4ca
caps.latest.revision: 22
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
ms.openlocfilehash: a19bd71f1346be292dcc7b143a0080ac1cf11ec0
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-filtering-myapplicationlog-output-visual-basic"></a><span data-ttu-id="21844-102">Procedura dettagliata: filtro dell'output di My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="21844-102">Walkthrough: Filtering My.Application.Log Output (Visual Basic)</span></span>
<span data-ttu-id="21844-103">Questa procedura dettagliata illustra come modificare il filtro di log predefinito per l'oggetto `My.Application.Log` per stabilire quali informazioni vengono passate dall'oggetto `Log` ai listener e quali informazioni vengono scritte dai listener.</span><span class="sxs-lookup"><span data-stu-id="21844-103">This walkthrough demonstrates how to change the default log filtering for the `My.Application.Log` object, to control what information is passed from the `Log` object to the listeners and what information is written by the listeners.</span></span> <span data-ttu-id="21844-104">È possibile modificare il comportamento di registrazione anche dopo la compilazione dell'applicazione, poiché le informazioni di configurazione vengono archiviate nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="21844-104">You can change the logging behavior even after building the application, because the configuration information is stored in the application's configuration file.</span></span>  
  
## <a name="getting-started"></a><span data-ttu-id="21844-105">Introduzione</span><span class="sxs-lookup"><span data-stu-id="21844-105">Getting Started</span></span>  
 <span data-ttu-id="21844-106">A ogni messaggio scritto da `My.Application.Log` è associato un livello di gravità, che i meccanismi di filtro usano per controllare l'output del log.</span><span class="sxs-lookup"><span data-stu-id="21844-106">Each message that `My.Application.Log` writes has an associated severity level, which filtering mechanisms use to control the log output.</span></span> <span data-ttu-id="21844-107">Questa applicazione di esempio usa i metodi `My.Application.Log` per scrivere alcuni messaggi di log con diversi livelli di gravità.</span><span class="sxs-lookup"><span data-stu-id="21844-107">This sample application uses `My.Application.Log` methods to write several log messages with different severity levels.</span></span>  
  
#### <a name="to-build-the-sample-application"></a><span data-ttu-id="21844-108">Per compilare l'applicazione di esempio</span><span class="sxs-lookup"><span data-stu-id="21844-108">To build the sample application</span></span>  
  
1.  <span data-ttu-id="21844-109">Aprire un nuovo progetto Applicazione Windows in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21844-109">Open a new [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="21844-110">Aggiungere un pulsante denominato Button1 a Form1.</span><span class="sxs-lookup"><span data-stu-id="21844-110">Add a button named Button1 to Form1.</span></span>  
  
3.  <span data-ttu-id="21844-111">Aggiungere il codice seguente al gestore eventi <xref:System.Windows.Forms.Control.Click> per Button1:</span><span class="sxs-lookup"><span data-stu-id="21844-111">In the <xref:System.Windows.Forms.Control.Click> event handler for Button1, add the following code:</span></span>  
  
     <span data-ttu-id="21844-112">[!code-vb[VbVbcnMyApplicationLogFiltering#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-filtering-my-application-log-output_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="21844-112">[!code-vb[VbVbcnMyApplicationLogFiltering#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-filtering-my-application-log-output_1.vb)]</span></span>  
  
4.  <span data-ttu-id="21844-113">Eseguire l'applicazione nel debugger.</span><span class="sxs-lookup"><span data-stu-id="21844-113">Run the application in the debugger.</span></span>  
  
5.  <span data-ttu-id="21844-114">Premere **Button1**.</span><span class="sxs-lookup"><span data-stu-id="21844-114">Press **Button1**.</span></span>  
  
     <span data-ttu-id="21844-115">L'applicazione scrive le informazioni seguenti nel file di log e di output di debug dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="21844-115">The application writes the following information to the application's debug output and log file.</span></span>  
  
     `DefaultSource Information: 0 : In Button1_Click`  
  
     `DefaultSource Error: 2 : Error in the application.`  
  
6.  <span data-ttu-id="21844-116">Chiudere l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="21844-116">Close the application.</span></span>  
  
     <span data-ttu-id="21844-117">Per informazioni su come visualizzare la finestra di output di debug dell'applicazione, vedere [Finestra di output](/visualstudio/ide/reference/output-window).</span><span class="sxs-lookup"><span data-stu-id="21844-117">For information on how to view the application's debug output window, see [Output Window](/visualstudio/ide/reference/output-window).</span></span> <span data-ttu-id="21844-118">Per informazioni sul percorso del file di log dell'applicazione, vedere [Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="21844-118">For information on the location of the application's log file, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="21844-119">Per impostazione predefinita, l'applicazione elimina l'output del file di log alla chiusura dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="21844-119">By default, the application flushes the log-file output when the application closes.</span></span>  
  
     <span data-ttu-id="21844-120">Nell'esempio precedente la seconda chiamata al metodo <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> e la chiamata al metodo <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> generano l'output del log, mentre non lo generano la prima e l'ultima chiamata al metodo `WriteEntry`.</span><span class="sxs-lookup"><span data-stu-id="21844-120">In the example above, the second call to the <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> method and the call to the <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> method produces log output, while the first and last calls to the `WriteEntry` method do not.</span></span> <span data-ttu-id="21844-121">Questo avviene poiché i livelli di gravità di `WriteEntry` e `WriteException` sono "Information" ed "Error", entrambi consentiti dal filtro di log predefinito dell'oggetto `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="21844-121">This is because the severity levels of `WriteEntry` and `WriteException` are "Information" and "Error", both of which are allowed by the `My.Application.Log` object's default log filtering.</span></span> <span data-ttu-id="21844-122">Tuttavia, agli eventi con i livelli di gravità "Start" e "Stop" non è consentito creare output di log.</span><span class="sxs-lookup"><span data-stu-id="21844-122">However, events with "Start" and "Stop" severity levels are prevented from producing log output.</span></span>  
  
## <a name="filtering-for-all-myapplicationlog-listeners"></a><span data-ttu-id="21844-123">Filtro per tutti i listener di My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="21844-123">Filtering for All My.Application.Log Listeners</span></span>  
 <span data-ttu-id="21844-124">L'oggetto `My.Application.Log` usa una classe <xref:System.Diagnostics.SourceSwitch> denominata `DefaultSwitch` per stabilire quali messaggi vengono passati dai metodi `WriteEntry` e `WriteException` ai listener di log.</span><span class="sxs-lookup"><span data-stu-id="21844-124">The `My.Application.Log` object uses a <xref:System.Diagnostics.SourceSwitch> named `DefaultSwitch` to control which messages it passes from the `WriteEntry` and `WriteException` methods to the log listeners.</span></span> <span data-ttu-id="21844-125">È possibile configurare `DefaultSwitch` nel file di configurazione dell'applicazione impostando il relativo valore su uno dei valori di enumerazione di <xref:System.Diagnostics.SourceLevels>.</span><span class="sxs-lookup"><span data-stu-id="21844-125">You can configure `DefaultSwitch` in the application's configuration file by setting its value to one of the <xref:System.Diagnostics.SourceLevels> enumeration values.</span></span> <span data-ttu-id="21844-126">Per impostazione predefinita, il valore è "Information".</span><span class="sxs-lookup"><span data-stu-id="21844-126">By default, its value is "Information".</span></span>  
  
 <span data-ttu-id="21844-127">Questa tabella illustra il livello di gravità richiesto al log per la scrittura di un messaggio ai listener, data un'impostazione `DefaultSwitch` specifica.</span><span class="sxs-lookup"><span data-stu-id="21844-127">This table shows the severity level required for Log to write a message to the listeners, given a particular `DefaultSwitch` setting.</span></span>  
  
|<span data-ttu-id="21844-128">Valore DefaultSwitch</span><span class="sxs-lookup"><span data-stu-id="21844-128">DefaultSwitch Value</span></span>|<span data-ttu-id="21844-129">Gravità del messaggio richiesto per l'output</span><span class="sxs-lookup"><span data-stu-id="21844-129">Message severity required for output</span></span>|  
|---|---| 
|`Critical`|`Critical`|  
|`Error`|<span data-ttu-id="21844-130">`Critical` o `Error`</span><span class="sxs-lookup"><span data-stu-id="21844-130">`Critical` or `Error`</span></span>|  
|`Warning`|<span data-ttu-id="21844-131">`Critical`, `Error` o `Warning`</span><span class="sxs-lookup"><span data-stu-id="21844-131">`Critical`, `Error`, or `Warning`</span></span>|  
|`Information`|<span data-ttu-id="21844-132">`Critical`, `Error`, `Warning` o `Information`</span><span class="sxs-lookup"><span data-stu-id="21844-132">`Critical`, `Error`, `Warning`, or `Information`</span></span>|  
|`Verbose`|<span data-ttu-id="21844-133">`Critical`, `Error`, `Warning`, `Information` o `Verbose`</span><span class="sxs-lookup"><span data-stu-id="21844-133">`Critical`, `Error`, `Warning`, `Information`, or `Verbose`</span></span>|  
|`ActivityTracing`|<span data-ttu-id="21844-134">`Start`, `Stop`, `Suspend`, `Resume` o `Transfer`</span><span class="sxs-lookup"><span data-stu-id="21844-134">`Start`, `Stop`, `Suspend`, `Resume`, or `Transfer`</span></span>|  
|`All`|<span data-ttu-id="21844-135">Sono consentiti tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="21844-135">All messages are allowed.</span></span>|  
|`Off`|<span data-ttu-id="21844-136">Tutti i messaggi vengono bloccati.</span><span class="sxs-lookup"><span data-stu-id="21844-136">All messages are blocked.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="21844-137">I metodi `WriteEntry` e `WriteException` hanno entrambi un overload che non specifica un livello di gravità.</span><span class="sxs-lookup"><span data-stu-id="21844-137">The `WriteEntry` and `WriteException` methods each have an overload that does not specify a severity level.</span></span> <span data-ttu-id="21844-138">Il livello di gravità implicito per l'overload di `WriteEntry` è "Information" e il livello di gravità implicito per l'overload `WriteException` è "Error".</span><span class="sxs-lookup"><span data-stu-id="21844-138">The implicit severity level for the `WriteEntry` overload is "Information", and the implicit severity level for the `WriteException` overload is "Error".</span></span>  
  
 <span data-ttu-id="21844-139">In questa tabella viene illustrato l'output di log dell'esempio precedente: con l'impostazione predefinita "Information" per `DefaultSwitch` solo la seconda chiamata al metodo `WriteEntry` e la chiamata al `WriteException` producono output di log.</span><span class="sxs-lookup"><span data-stu-id="21844-139">This table explains the log output shown in the previous example: with the default `DefaultSwitch` setting of "Information", only the second call to the `WriteEntry` method and the call to the `WriteException` method produce log output.</span></span>  
  
#### <a name="to-log-only-activity-tracing-events"></a><span data-ttu-id="21844-140">Per registrare solo gli eventi di traccia attività</span><span class="sxs-lookup"><span data-stu-id="21844-140">To log only activity tracing events</span></span>  
  
1.  <span data-ttu-id="21844-141">Fare clic con il pulsante destro del mouse su app.config **Esplora soluzioni** e selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="21844-141">Right-click app.config in the **Solution Explorer** and select **Open**.</span></span>  
  
     <span data-ttu-id="21844-142">-oppure-</span><span class="sxs-lookup"><span data-stu-id="21844-142">-or-</span></span>  
  
     <span data-ttu-id="21844-143">Se non è presente alcun file app.config:</span><span class="sxs-lookup"><span data-stu-id="21844-143">If there is no app.config file:</span></span>  
  
    1.  <span data-ttu-id="21844-144">Scegliere **Aggiungi nuovo elemento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="21844-144">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="21844-145">Nella finestra di dialogo **Aggiungi nuovo elemento** scegliere **File di configurazione dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="21844-145">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="21844-146">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="21844-146">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="21844-147">Individuare la sezione `<switches>` nella sezione `<system.diagnostics>` all'interno della sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="21844-147">Locate the `<switches>` section, which is in the `<system.diagnostics>` section, which is in the top-level `<configuration>` section.</span></span>  
  
3.  <span data-ttu-id="21844-148">Trovare l'elemento che consente di aggiungere `DefaultSwitch` alla raccolta di opzioni.</span><span class="sxs-lookup"><span data-stu-id="21844-148">Find the element that adds `DefaultSwitch` to the collection of switches.</span></span> <span data-ttu-id="21844-149">Deve essere simile all'elemento seguente:</span><span class="sxs-lookup"><span data-stu-id="21844-149">It should look similar to this element:</span></span>  
  
     `<add name="DefaultSwitch" value="Information" />`  
  
4.  <span data-ttu-id="21844-150">Modificare il valore dell'attributo `value` impostandolo su "ActivityTracing".</span><span class="sxs-lookup"><span data-stu-id="21844-150">Change the value of the `value` attribute to "ActivityTracing".</span></span>  
  
5.  <span data-ttu-id="21844-151">Il contenuto del file app.config dovrebbe essere simile al codice XML seguente.</span><span class="sxs-lookup"><span data-stu-id="21844-151">The content of the app.config file should be similar to the following XML:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <!-- This section configures My.Application.Log -->  
          <source name="DefaultSource" switchName="DefaultSwitch">  
            <listeners>  
              <add name="FileLog"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="DefaultSwitch" value="ActivityTracing" />  
        </switches>  
        <sharedListeners>  
          <add name="FileLog"  
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
                     Microsoft.VisualBasic, Version=8.0.0.0,   
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,   
                     processorArchitecture=MSIL"   
               initializeData="FileLogWriter"/>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
6.  <span data-ttu-id="21844-152">Eseguire l'applicazione nel debugger.</span><span class="sxs-lookup"><span data-stu-id="21844-152">Run the application in the debugger.</span></span>  
  
7.  <span data-ttu-id="21844-153">Premere **Button1**.</span><span class="sxs-lookup"><span data-stu-id="21844-153">Press **Button1**.</span></span>  
  
     <span data-ttu-id="21844-154">L'applicazione scrive le informazioni seguenti nel file di log e di output di debug dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="21844-154">The application writes the following information to the application's debug output and log file:</span></span>  
  
     `DefaultSource Start: 4 : Entering Button1_Click`  
  
     `DefaultSource Stop: 5 : Leaving Button1_Click`  
  
8.  <span data-ttu-id="21844-155">Chiudere l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="21844-155">Close the application.</span></span>  
  
9. <span data-ttu-id="21844-156">Impostare di nuovo il valore dell'attributo `value` su "Information".</span><span class="sxs-lookup"><span data-stu-id="21844-156">Change the value of the `value` attribute back to "Information".</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="21844-157">L'impostazione dell'opzione `DefaultSwitch` controlla solo `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="21844-157">The `DefaultSwitch` switch setting controls only `My.Application.Log`.</span></span> <span data-ttu-id="21844-158">Non modifica il comportamento delle classi <xref:System.Diagnostics.Trace?displayProperty=fullName> e <xref:System.Diagnostics.Debug?displayProperty=fullName> di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21844-158">It does not change how the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.Diagnostics.Trace?displayProperty=fullName> and <xref:System.Diagnostics.Debug?displayProperty=fullName> classes behave.</span></span>  
  
## <a name="individual-filtering-for-myapplicationlog-listeners"></a><span data-ttu-id="21844-159">Filtro individuale per i listener di My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="21844-159">Individual Filtering For My.Application.Log Listeners</span></span>  
 <span data-ttu-id="21844-160">Nell'esempio precedente viene illustrato come modificare il filtro per tutto l'output di `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="21844-160">The previous example shows how to change the filtering for all `My.Application.Log` output.</span></span> <span data-ttu-id="21844-161">Questo esempio illustra come filtrare un singolo listener di log.</span><span class="sxs-lookup"><span data-stu-id="21844-161">This example demonstrates how to filter an individual log listener.</span></span> <span data-ttu-id="21844-162">Per impostazione predefinita, un'applicazione ha due listener che scrivono nell'output di debug dell'applicazione e nel file di log.</span><span class="sxs-lookup"><span data-stu-id="21844-162">By default, an application has two listeners that write to the application's debug output and the log file.</span></span>  
  
 <span data-ttu-id="21844-163">Il file di configurazione controlla il comportamento dei listener di log, consentendo a ognuno di essi di avere un filtro, che è simile a un'opzione per `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="21844-163">The configuration file controls the behavior of the log listeners by allowing each one to have a filter, which is similar to a switch for `My.Application.Log`.</span></span> <span data-ttu-id="21844-164">Un listener di log genera un messaggio solo se la gravità del messaggio è consentita sia dall'opzione `DefaultSwitch` del log, sia dal filtro del listener di log.</span><span class="sxs-lookup"><span data-stu-id="21844-164">A log listener will output a message only if the message's severity is allowed by both the log's `DefaultSwitch` and the log listener's filter.</span></span>  
  
 <span data-ttu-id="21844-165">In questo esempio viene illustrato come configurare il filtro per un nuovo listener di debug e aggiungerlo all'oggetto `Log`.</span><span class="sxs-lookup"><span data-stu-id="21844-165">This example demonstrates how to configure filtering for a new debug listener and add it to the `Log` object.</span></span> <span data-ttu-id="21844-166">Il listener di debug predefinito deve essere rimosso dall'oggetto `Log` in modo che sia chiaro che i messaggi di debug provengono dal nuovo listener di debug.</span><span class="sxs-lookup"><span data-stu-id="21844-166">The default debug listener should be removed from the `Log` object, so it is clear that the debug messages come from the new debug listener.</span></span>  
  
#### <a name="to-log-only-activity-tracing-events"></a><span data-ttu-id="21844-167">Per registrare solo gli eventi di traccia attività</span><span class="sxs-lookup"><span data-stu-id="21844-167">To log only activity-tracing events</span></span>  
  
1.  <span data-ttu-id="21844-168">Fare clic con il pulsante destro del mouse su app.config in **Esplora soluzioni** e scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="21844-168">Right-click app.config in the **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="21844-169">-oppure-</span><span class="sxs-lookup"><span data-stu-id="21844-169">-or-</span></span>  
  
     <span data-ttu-id="21844-170">Se non è presente alcun file app.config:</span><span class="sxs-lookup"><span data-stu-id="21844-170">If there is no app.config file:</span></span>  
  
    1.  <span data-ttu-id="21844-171">Scegliere **Aggiungi nuovo elemento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="21844-171">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="21844-172">Nella finestra di dialogo **Aggiungi nuovo elemento** scegliere **File di configurazione dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="21844-172">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="21844-173">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="21844-173">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="21844-174">Fare clic con il pulsante destro del mouse su app.config in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="21844-174">Right-click app.config in **Solution Explorer**.</span></span> <span data-ttu-id="21844-175">Scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="21844-175">Choose **Open**.</span></span>  
  
3.  <span data-ttu-id="21844-176">Individuare la sezione `<listeners>` all'interno della sezione `<source>` con l'attributo `name` "DefaultSource" che si trova nella sezione `<sources>` .</span><span class="sxs-lookup"><span data-stu-id="21844-176">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", which is under the `<sources>` section.</span></span> <span data-ttu-id="21844-177">La sezione `<sources>` si trova nella sezione `<system.diagnostics>` all'interno della sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="21844-177">The `<sources>` section is under the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
4.  <span data-ttu-id="21844-178">Aggiungere l'elemento seguente alla sezione `<listeners>`:</span><span class="sxs-lookup"><span data-stu-id="21844-178">Add this element to the `<listeners>` section:</span></span>  
  
    ```xml  
    <!-- Remove the default debug listener. -->  
    <remove name="Default"/>  
    <!-- Add a filterable debug listener. -->  
    <add name="NewDefault"/>  
    ```  
  
5.  <span data-ttu-id="21844-179">Individuare la sezione `<sharedListeners>` nella sezione `<system.diagnostics>` all'interno della sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="21844-179">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
6.  <span data-ttu-id="21844-180">Aggiungere l'elemento seguente alla sezione `<sharedListeners>` :</span><span class="sxs-lookup"><span data-stu-id="21844-180">Add this element to that `<sharedListeners>` section:</span></span>  
  
    ```xml  
    <add name="NewDefault"   
         type="System.Diagnostics.DefaultTraceListener,   
               System, Version=2.0.0.0, Culture=neutral,   
               PublicKeyToken=b77a5c561934e089,   
               processorArchitecture=MSIL">  
        <filter type="System.Diagnostics.EventTypeFilter"   
                initializeData="Error" />  
    </add>  
    ```  
  
     <span data-ttu-id="21844-181">Il filtro <xref:System.Diagnostics.EventTypeFilter> accetta uno dei valori di enumerazione di <xref:System.Diagnostics.SourceLevels> come proprio attributo `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="21844-181">The <xref:System.Diagnostics.EventTypeFilter> filter takes one of the <xref:System.Diagnostics.SourceLevels> enumeration values as its `initializeData` attribute.</span></span>  
  
7.  <span data-ttu-id="21844-182">Il contenuto del file app.config dovrebbe essere simile al codice XML seguente.</span><span class="sxs-lookup"><span data-stu-id="21844-182">The content of the app.config file should be similar to the following XML:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <!-- This section configures My.Application.Log -->  
          <source name="DefaultSource" switchName="DefaultSwitch">  
            <listeners>  
              <add name="FileLog"/>  
              <!-- Remove the default debug listener. -->  
              <remove name="Default"/>  
              <!-- Add a filterable debug listener. -->  
              <add name="NewDefault"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="DefaultSwitch" value="Information" />  
        </switches>  
        <sharedListeners>  
          <add name="FileLog"  
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
                     Microsoft.VisualBasic, Version=8.0.0.0,   
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,   
                     processorArchitecture=MSIL"   
               initializeData="FileLogWriter"/>  
          <add name="NewDefault"   
               type="System.Diagnostics.DefaultTraceListener,   
                     System, Version=2.0.0.0, Culture=neutral,   
                     PublicKeyToken=b77a5c561934e089,   
                     processorArchitecture=MSIL">  
            <filter type="System.Diagnostics.EventTypeFilter"   
                    initializeData="Error" />  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
8.  <span data-ttu-id="21844-183">Eseguire l'applicazione nel debugger.</span><span class="sxs-lookup"><span data-stu-id="21844-183">Run the application in the debugger.</span></span>  
  
9. <span data-ttu-id="21844-184">Premere **Button1**.</span><span class="sxs-lookup"><span data-stu-id="21844-184">Press **Button1**.</span></span>  
  
     <span data-ttu-id="21844-185">L'applicazione scrive le informazioni seguenti nel file di log dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="21844-185">The application writes the following information to the application's log file:</span></span>  
  
     `Default Information: 0 : In Button1_Click`  
  
     `Default Error: 2 : Error in the application.`  
  
     <span data-ttu-id="21844-186">L'applicazione scrive meno informazioni nell'output di debug dell'applicazione perché il filtro è più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="21844-186">The application writes less information to the application's debug output because of the more restrictive filtering.</span></span>  
  
     `Default Error   2   Error`  
  
10. <span data-ttu-id="21844-187">Chiudere l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="21844-187">Close the application.</span></span>  
  
 <span data-ttu-id="21844-188">Per altre informazioni sulla modifica delle impostazioni del log dopo la distribuzione, vedere [Utilizzo dei log applicazione](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="21844-188">For more information about changing log settings after deployment, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21844-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21844-189">See Also</span></span>  
 <span data-ttu-id="21844-190">[Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="21844-190">[Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span></span>  
 <span data-ttu-id="21844-191">[Procedura dettagliata: Modifica della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="21844-191">[Walkthrough: Changing Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span></span>  
 <span data-ttu-id="21844-192">[Procedura dettagliata: Creazione di listener di log personalizzati](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md) </span><span class="sxs-lookup"><span data-stu-id="21844-192">[Walkthrough: Creating Custom Log Listeners](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md) </span></span>  
 <span data-ttu-id="21844-193">[Procedura: Scrivere messaggi di log](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span><span class="sxs-lookup"><span data-stu-id="21844-193">[How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span></span>  
 <span data-ttu-id="21844-194">[Opzioni di traccia](../../../../framework/debug-trace-profile/trace-switches.md) </span><span class="sxs-lookup"><span data-stu-id="21844-194">[Trace Switches](../../../../framework/debug-trace-profile/trace-switches.md) </span></span>  
 [<span data-ttu-id="21844-195">Registrazione di informazioni relative all'applicazione</span><span class="sxs-lookup"><span data-stu-id="21844-195">Logging Information from the Application</span></span>](../../../../visual-basic/developing-apps/programming/log-info/logging-information-from-the-application.md)


---
title: Filtro dell'output di My.Application.Log
ms.date: 07/20/2015
helpviewer_keywords:
- My.Log object, filtering output
- My.Application.Log object, filtering output
- application event logs, output filtering
ms.assetid: 2c0a457a-38a4-49e1-934d-a51320b7b4ca
ms.openlocfilehash: f18556bbe1ca2d77925482319246d403892d31ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74353597"
---
# <a name="walkthrough-filtering-myapplicationlog-output-visual-basic"></a><span data-ttu-id="4d448-102">Procedura dettagliata: filtro dell'output di My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="4d448-102">Walkthrough: Filtering My.Application.Log Output (Visual Basic)</span></span>

<span data-ttu-id="4d448-103">Questa procedura dettagliata illustra come modificare il filtro di log predefinito per l'oggetto `My.Application.Log` per stabilire quali informazioni vengono passate dall'oggetto `Log` ai listener e quali informazioni vengono scritte dai listener.</span><span class="sxs-lookup"><span data-stu-id="4d448-103">This walkthrough demonstrates how to change the default log filtering for the `My.Application.Log` object, to control what information is passed from the `Log` object to the listeners and what information is written by the listeners.</span></span> <span data-ttu-id="4d448-104">È possibile modificare il comportamento di registrazione anche dopo la compilazione dell'applicazione, poiché le informazioni di configurazione vengono archiviate nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4d448-104">You can change the logging behavior even after building the application, because the configuration information is stored in the application's configuration file.</span></span>

## <a name="getting-started"></a><span data-ttu-id="4d448-105">Introduzione</span><span class="sxs-lookup"><span data-stu-id="4d448-105">Getting Started</span></span>

<span data-ttu-id="4d448-106">A ogni messaggio scritto da `My.Application.Log` è associato un livello di gravità, che i meccanismi di filtro usano per controllare l'output del log.</span><span class="sxs-lookup"><span data-stu-id="4d448-106">Each message that `My.Application.Log` writes has an associated severity level, which filtering mechanisms use to control the log output.</span></span> <span data-ttu-id="4d448-107">Questa applicazione di esempio usa i metodi `My.Application.Log` per scrivere alcuni messaggi di log con diversi livelli di gravità.</span><span class="sxs-lookup"><span data-stu-id="4d448-107">This sample application uses `My.Application.Log` methods to write several log messages with different severity levels.</span></span>

#### <a name="to-build-the-sample-application"></a><span data-ttu-id="4d448-108">Per compilare l'applicazione di esempio</span><span class="sxs-lookup"><span data-stu-id="4d448-108">To build the sample application</span></span>

1. <span data-ttu-id="4d448-109">Aprire un nuovo progetto Applicazione Windows in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4d448-109">Open a new Visual Basic Windows Application project.</span></span>

2. <span data-ttu-id="4d448-110">Aggiungere un pulsante denominato Button1 a Form1.</span><span class="sxs-lookup"><span data-stu-id="4d448-110">Add a button named Button1 to Form1.</span></span>

3. <span data-ttu-id="4d448-111">Aggiungere il codice seguente al gestore eventi <xref:System.Windows.Forms.Control.Click> per Button1:</span><span class="sxs-lookup"><span data-stu-id="4d448-111">In the <xref:System.Windows.Forms.Control.Click> event handler for Button1, add the following code:</span></span>

     [!code-vb[VbVbcnMyApplicationLogFiltering#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyApplicationLogFiltering/VB/Form1.vb#1)]

4. <span data-ttu-id="4d448-112">Eseguire l'applicazione nel debugger.</span><span class="sxs-lookup"><span data-stu-id="4d448-112">Run the application in the debugger.</span></span>

5. <span data-ttu-id="4d448-113">Premere **Button1**.</span><span class="sxs-lookup"><span data-stu-id="4d448-113">Press **Button1**.</span></span>

     <span data-ttu-id="4d448-114">L'applicazione scrive le informazioni seguenti nel file di log e di output di debug dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4d448-114">The application writes the following information to the application's debug output and log file.</span></span>

     `DefaultSource Information: 0 : In Button1_Click`

     `DefaultSource Error: 2 : Error in the application.`

6. <span data-ttu-id="4d448-115">Chiudere l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4d448-115">Close the application.</span></span>

     <span data-ttu-id="4d448-116">Per informazioni su come visualizzare la finestra di output di debug dell'applicazione, vedere [Finestra di output](/visualstudio/ide/reference/output-window).</span><span class="sxs-lookup"><span data-stu-id="4d448-116">For information on how to view the application's debug output window, see [Output Window](/visualstudio/ide/reference/output-window).</span></span> <span data-ttu-id="4d448-117">Per informazioni sul percorso del file di log dell'applicazione, vedere [Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="4d448-117">For information on the location of the application's log file, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="4d448-118">Per impostazione predefinita, l'applicazione elimina l'output del file di log alla chiusura dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4d448-118">By default, the application flushes the log-file output when the application closes.</span></span>

     <span data-ttu-id="4d448-119">Nell'esempio precedente la seconda chiamata al metodo <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> e la chiamata al metodo <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> generano l'output del log, mentre non lo generano la prima e l'ultima chiamata al metodo `WriteEntry`.</span><span class="sxs-lookup"><span data-stu-id="4d448-119">In the example above, the second call to the <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> method and the call to the <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> method produces log output, while the first and last calls to the `WriteEntry` method do not.</span></span> <span data-ttu-id="4d448-120">Questo avviene poiché i livelli di gravità di `WriteEntry` e `WriteException` sono "Information" ed "Error", entrambi consentiti dal filtro di log predefinito dell'oggetto `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="4d448-120">This is because the severity levels of `WriteEntry` and `WriteException` are "Information" and "Error", both of which are allowed by the `My.Application.Log` object's default log filtering.</span></span> <span data-ttu-id="4d448-121">Tuttavia, agli eventi con i livelli di gravità "Start" e "Stop" non è consentito creare output di log.</span><span class="sxs-lookup"><span data-stu-id="4d448-121">However, events with "Start" and "Stop" severity levels are prevented from producing log output.</span></span>

## <a name="filtering-for-all-myapplicationlog-listeners"></a><span data-ttu-id="4d448-122">Filtro per tutti i listener di My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="4d448-122">Filtering for All My.Application.Log Listeners</span></span>

<span data-ttu-id="4d448-123">L'oggetto `My.Application.Log` usa una classe <xref:System.Diagnostics.SourceSwitch> denominata `DefaultSwitch` per stabilire quali messaggi vengono passati dai metodi `WriteEntry` e `WriteException` ai listener di log.</span><span class="sxs-lookup"><span data-stu-id="4d448-123">The `My.Application.Log` object uses a <xref:System.Diagnostics.SourceSwitch> named `DefaultSwitch` to control which messages it passes from the `WriteEntry` and `WriteException` methods to the log listeners.</span></span> <span data-ttu-id="4d448-124">È possibile configurare `DefaultSwitch` nel file di configurazione dell'applicazione impostando il relativo valore su uno dei valori di enumerazione di <xref:System.Diagnostics.SourceLevels>.</span><span class="sxs-lookup"><span data-stu-id="4d448-124">You can configure `DefaultSwitch` in the application's configuration file by setting its value to one of the <xref:System.Diagnostics.SourceLevels> enumeration values.</span></span> <span data-ttu-id="4d448-125">Per impostazione predefinita, il valore è "Information".</span><span class="sxs-lookup"><span data-stu-id="4d448-125">By default, its value is "Information".</span></span>

<span data-ttu-id="4d448-126">Questa tabella illustra il livello di gravità richiesto al log per la scrittura di un messaggio ai listener, data un'impostazione `DefaultSwitch` specifica.</span><span class="sxs-lookup"><span data-stu-id="4d448-126">This table shows the severity level required for Log to write a message to the listeners, given a particular `DefaultSwitch` setting.</span></span>

|<span data-ttu-id="4d448-127">Valore DefaultSwitch</span><span class="sxs-lookup"><span data-stu-id="4d448-127">DefaultSwitch Value</span></span>|<span data-ttu-id="4d448-128">Gravità del messaggio richiesto per l'output</span><span class="sxs-lookup"><span data-stu-id="4d448-128">Message severity required for output</span></span>|
|---|---|
|`Critical`|`Critical`|
|`Error`|<span data-ttu-id="4d448-129">`Critical` o `Error`</span><span class="sxs-lookup"><span data-stu-id="4d448-129">`Critical` or `Error`</span></span>|
|`Warning`|<span data-ttu-id="4d448-130">`Critical`, `Error` o `Warning`</span><span class="sxs-lookup"><span data-stu-id="4d448-130">`Critical`, `Error`, or `Warning`</span></span>|
|`Information`|<span data-ttu-id="4d448-131">`Critical`, `Error`, `Warning` o `Information`</span><span class="sxs-lookup"><span data-stu-id="4d448-131">`Critical`, `Error`, `Warning`, or `Information`</span></span>|
|`Verbose`|<span data-ttu-id="4d448-132">`Critical`, `Error`, `Warning`, `Information` o `Verbose`</span><span class="sxs-lookup"><span data-stu-id="4d448-132">`Critical`, `Error`, `Warning`, `Information`, or `Verbose`</span></span>|
|`ActivityTracing`|<span data-ttu-id="4d448-133">`Start`, `Stop`, `Suspend`, `Resume` o `Transfer`</span><span class="sxs-lookup"><span data-stu-id="4d448-133">`Start`, `Stop`, `Suspend`, `Resume`, or `Transfer`</span></span>|
|`All`|<span data-ttu-id="4d448-134">Sono consentiti tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="4d448-134">All messages are allowed.</span></span>|
|`Off`|<span data-ttu-id="4d448-135">Tutti i messaggi vengono bloccati.</span><span class="sxs-lookup"><span data-stu-id="4d448-135">All messages are blocked.</span></span>|

> [!NOTE]
> <span data-ttu-id="4d448-136">I metodi `WriteEntry` e `WriteException` hanno entrambi un overload che non specifica un livello di gravità.</span><span class="sxs-lookup"><span data-stu-id="4d448-136">The `WriteEntry` and `WriteException` methods each have an overload that does not specify a severity level.</span></span> <span data-ttu-id="4d448-137">Il livello di gravità implicito per l'overload di `WriteEntry` è "Information" e il livello di gravità implicito per l'overload `WriteException` è "Error".</span><span class="sxs-lookup"><span data-stu-id="4d448-137">The implicit severity level for the `WriteEntry` overload is "Information", and the implicit severity level for the `WriteException` overload is "Error".</span></span>

<span data-ttu-id="4d448-138">In questa tabella viene illustrato l'output di log dell'esempio precedente: con l'impostazione predefinita "Information" per `DefaultSwitch` solo la seconda chiamata al metodo `WriteEntry` e la chiamata al `WriteException` producono output di log.</span><span class="sxs-lookup"><span data-stu-id="4d448-138">This table explains the log output shown in the previous example: with the default `DefaultSwitch` setting of "Information", only the second call to the `WriteEntry` method and the call to the `WriteException` method produce log output.</span></span>

#### <a name="to-log-only-activity-tracing-events"></a><span data-ttu-id="4d448-139">Per registrare solo gli eventi di traccia attività</span><span class="sxs-lookup"><span data-stu-id="4d448-139">To log only activity tracing events</span></span>

1. <span data-ttu-id="4d448-140">Fare clic con il pulsante destro del mouse su app.config **Esplora soluzioni** e selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="4d448-140">Right-click app.config in the **Solution Explorer** and select **Open**.</span></span>

     <span data-ttu-id="4d448-141">-oppure-</span><span class="sxs-lookup"><span data-stu-id="4d448-141">-or-</span></span>

     <span data-ttu-id="4d448-142">Se non è presente alcun file app.config:</span><span class="sxs-lookup"><span data-stu-id="4d448-142">If there is no app.config file:</span></span>

    1. <span data-ttu-id="4d448-143">Scegliere **Aggiungi nuovo elemento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="4d448-143">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="4d448-144">Nella finestra di dialogo **Aggiungi nuovo elemento** scegliere **File di configurazione dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="4d448-144">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="4d448-145">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="4d448-145">Click **Add**.</span></span>

2. <span data-ttu-id="4d448-146">Individuare la sezione `<switches>` nella sezione `<system.diagnostics>` all'interno della sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="4d448-146">Locate the `<switches>` section, which is in the `<system.diagnostics>` section, which is in the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="4d448-147">Trovare l'elemento che consente di aggiungere `DefaultSwitch` alla raccolta di opzioni.</span><span class="sxs-lookup"><span data-stu-id="4d448-147">Find the element that adds `DefaultSwitch` to the collection of switches.</span></span> <span data-ttu-id="4d448-148">Deve essere simile all'elemento seguente:</span><span class="sxs-lookup"><span data-stu-id="4d448-148">It should look similar to this element:</span></span>

     `<add name="DefaultSwitch" value="Information" />`

4. <span data-ttu-id="4d448-149">Modificare il valore dell'attributo `value` impostandolo su "ActivityTracing".</span><span class="sxs-lookup"><span data-stu-id="4d448-149">Change the value of the `value` attribute to "ActivityTracing".</span></span>

5. <span data-ttu-id="4d448-150">Il contenuto del file app.config dovrebbe essere simile al codice XML seguente.</span><span class="sxs-lookup"><span data-stu-id="4d448-150">The content of the app.config file should be similar to the following XML:</span></span>

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

6. <span data-ttu-id="4d448-151">Eseguire l'applicazione nel debugger.</span><span class="sxs-lookup"><span data-stu-id="4d448-151">Run the application in the debugger.</span></span>

7. <span data-ttu-id="4d448-152">Premere **Button1**.</span><span class="sxs-lookup"><span data-stu-id="4d448-152">Press **Button1**.</span></span>

     <span data-ttu-id="4d448-153">L'applicazione scrive le informazioni seguenti nel file di log e di output di debug dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="4d448-153">The application writes the following information to the application's debug output and log file:</span></span>

     `DefaultSource Start: 4 : Entering Button1_Click`

     `DefaultSource Stop: 5 : Leaving Button1_Click`

8. <span data-ttu-id="4d448-154">Chiudere l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4d448-154">Close the application.</span></span>

9. <span data-ttu-id="4d448-155">Impostare di nuovo il valore dell'attributo `value` su "Information".</span><span class="sxs-lookup"><span data-stu-id="4d448-155">Change the value of the `value` attribute back to "Information".</span></span>

    > [!NOTE]
    > <span data-ttu-id="4d448-156">L'impostazione dell'opzione `DefaultSwitch` controlla solo `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="4d448-156">The `DefaultSwitch` switch setting controls only `My.Application.Log`.</span></span> <span data-ttu-id="4d448-157">Non modifica il comportamento delle classi <xref:System.Diagnostics.Trace?displayProperty=nameWithType> e <xref:System.Diagnostics.Debug?displayProperty=nameWithType> di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d448-157">It does not change how the .NET Framework <xref:System.Diagnostics.Trace?displayProperty=nameWithType> and <xref:System.Diagnostics.Debug?displayProperty=nameWithType> classes behave.</span></span>

## <a name="individual-filtering-for-myapplicationlog-listeners"></a><span data-ttu-id="4d448-158">Filtro individuale per i listener di My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="4d448-158">Individual Filtering For My.Application.Log Listeners</span></span>

<span data-ttu-id="4d448-159">Nell'esempio precedente viene illustrato come modificare il filtro per tutto l'output di `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="4d448-159">The previous example shows how to change the filtering for all `My.Application.Log` output.</span></span> <span data-ttu-id="4d448-160">Questo esempio illustra come filtrare un singolo listener di log.</span><span class="sxs-lookup"><span data-stu-id="4d448-160">This example demonstrates how to filter an individual log listener.</span></span> <span data-ttu-id="4d448-161">Per impostazione predefinita, un'applicazione ha due listener che scrivono nell'output di debug dell'applicazione e nel file di log.</span><span class="sxs-lookup"><span data-stu-id="4d448-161">By default, an application has two listeners that write to the application's debug output and the log file.</span></span>

<span data-ttu-id="4d448-162">Il file di configurazione controlla il comportamento dei listener di log, consentendo a ognuno di essi di avere un filtro, che è simile a un'opzione per `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="4d448-162">The configuration file controls the behavior of the log listeners by allowing each one to have a filter, which is similar to a switch for `My.Application.Log`.</span></span> <span data-ttu-id="4d448-163">Un listener di log genera un messaggio solo se la gravità del messaggio è consentita sia dall'opzione `DefaultSwitch` del log, sia dal filtro del listener di log.</span><span class="sxs-lookup"><span data-stu-id="4d448-163">A log listener will output a message only if the message's severity is allowed by both the log's `DefaultSwitch` and the log listener's filter.</span></span>

<span data-ttu-id="4d448-164">In questo esempio viene illustrato come configurare il filtro per un nuovo listener di debug e aggiungerlo all'oggetto `Log`.</span><span class="sxs-lookup"><span data-stu-id="4d448-164">This example demonstrates how to configure filtering for a new debug listener and add it to the `Log` object.</span></span> <span data-ttu-id="4d448-165">Il listener di debug predefinito deve essere rimosso dall'oggetto `Log` in modo che sia chiaro che i messaggi di debug provengono dal nuovo listener di debug.</span><span class="sxs-lookup"><span data-stu-id="4d448-165">The default debug listener should be removed from the `Log` object, so it is clear that the debug messages come from the new debug listener.</span></span>

#### <a name="to-log-only-activity-tracing-events"></a><span data-ttu-id="4d448-166">Per registrare solo gli eventi di traccia attività</span><span class="sxs-lookup"><span data-stu-id="4d448-166">To log only activity-tracing events</span></span>

1. <span data-ttu-id="4d448-167">Fare clic con il pulsante destro del mouse su app.config in **Esplora soluzioni** e scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="4d448-167">Right-click app.config in the **Solution Explorer** and choose **Open**.</span></span>

     <span data-ttu-id="4d448-168">\-oppure-</span><span class="sxs-lookup"><span data-stu-id="4d448-168">\-or-</span></span>

     <span data-ttu-id="4d448-169">Se non è presente alcun file app.config:</span><span class="sxs-lookup"><span data-stu-id="4d448-169">If there is no app.config file:</span></span>

    1. <span data-ttu-id="4d448-170">Scegliere **Aggiungi nuovo elemento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="4d448-170">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="4d448-171">Nella finestra di dialogo **Aggiungi nuovo elemento** scegliere **File di configurazione dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="4d448-171">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="4d448-172">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="4d448-172">Click **Add**.</span></span>

2. <span data-ttu-id="4d448-173">Fare clic con il pulsante destro del mouse su app.config in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="4d448-173">Right-click app.config in **Solution Explorer**.</span></span> <span data-ttu-id="4d448-174">Scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="4d448-174">Choose **Open**.</span></span>

3. <span data-ttu-id="4d448-175">Individuare la sezione `<listeners>` all'interno della sezione `<source>` con l'attributo `name` "DefaultSource" che si trova nella sezione `<sources>` .</span><span class="sxs-lookup"><span data-stu-id="4d448-175">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", which is under the `<sources>` section.</span></span> <span data-ttu-id="4d448-176">La sezione `<sources>` si trova nella sezione `<system.diagnostics>` all'interno della sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="4d448-176">The `<sources>` section is under the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

4. <span data-ttu-id="4d448-177">Aggiungere l'elemento seguente alla sezione `<listeners>`:</span><span class="sxs-lookup"><span data-stu-id="4d448-177">Add this element to the `<listeners>` section:</span></span>

    ```xml
    <!-- Remove the default debug listener. -->
    <remove name="Default"/>
    <!-- Add a filterable debug listener. -->
    <add name="NewDefault"/>
    ```

5. <span data-ttu-id="4d448-178">Individuare la sezione `<sharedListeners>` nella sezione `<system.diagnostics>` all'interno della sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="4d448-178">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

6. <span data-ttu-id="4d448-179">Aggiungere l'elemento seguente alla sezione `<sharedListeners>` :</span><span class="sxs-lookup"><span data-stu-id="4d448-179">Add this element to that `<sharedListeners>` section:</span></span>

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

     <span data-ttu-id="4d448-180">Il filtro <xref:System.Diagnostics.EventTypeFilter> accetta uno dei valori di enumerazione di <xref:System.Diagnostics.SourceLevels> come proprio attributo `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="4d448-180">The <xref:System.Diagnostics.EventTypeFilter> filter takes one of the <xref:System.Diagnostics.SourceLevels> enumeration values as its `initializeData` attribute.</span></span>

7. <span data-ttu-id="4d448-181">Il contenuto del file app.config dovrebbe essere simile al codice XML seguente.</span><span class="sxs-lookup"><span data-stu-id="4d448-181">The content of the app.config file should be similar to the following XML:</span></span>

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

8. <span data-ttu-id="4d448-182">Eseguire l'applicazione nel debugger.</span><span class="sxs-lookup"><span data-stu-id="4d448-182">Run the application in the debugger.</span></span>

9. <span data-ttu-id="4d448-183">Premere **Button1**.</span><span class="sxs-lookup"><span data-stu-id="4d448-183">Press **Button1**.</span></span>

     <span data-ttu-id="4d448-184">L'applicazione scrive le informazioni seguenti nel file di log dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="4d448-184">The application writes the following information to the application's log file:</span></span>

     `Default Information: 0 : In Button1_Click`

     `Default Error: 2 : Error in the application.`

     <span data-ttu-id="4d448-185">L'applicazione scrive meno informazioni nell'output di debug dell'applicazione perché il filtro è più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="4d448-185">The application writes less information to the application's debug output because of the more restrictive filtering.</span></span>

     `Default Error   2   Error`

10. <span data-ttu-id="4d448-186">Chiudere l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4d448-186">Close the application.</span></span>

<span data-ttu-id="4d448-187">Per altre informazioni sulla modifica delle impostazioni del log dopo la distribuzione, vedere [Utilizzo dei log applicazione](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="4d448-187">For more information about changing log settings after deployment, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4d448-188">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4d448-188">See also</span></span>

- [<span data-ttu-id="4d448-189">Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="4d448-189">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="4d448-190">Procedura dettagliata: Modifica della posizione di inserimento delle informazioni con My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="4d448-190">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
- [<span data-ttu-id="4d448-191">Procedura dettagliata: Creazione di listener di log personalizzati</span><span class="sxs-lookup"><span data-stu-id="4d448-191">Walkthrough: Creating Custom Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)
- [<span data-ttu-id="4d448-192">Procedura: Scrivere messaggi di log</span><span class="sxs-lookup"><span data-stu-id="4d448-192">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)
- [<span data-ttu-id="4d448-193">Opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="4d448-193">Trace Switches</span></span>](../../../../framework/debug-trace-profile/trace-switches.md)
- [<span data-ttu-id="4d448-194">Registrazione di informazioni relative all'applicazione</span><span class="sxs-lookup"><span data-stu-id="4d448-194">Logging Information from the Application</span></span>](../../../../visual-basic/developing-apps/programming/log-info/index.md)

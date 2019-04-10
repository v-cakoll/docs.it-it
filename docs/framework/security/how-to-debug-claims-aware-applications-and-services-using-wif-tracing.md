---
title: 'Procedura: Eseguire il debug di servizi e applicazioni in grado di riconoscere attestazioni con le funzionalità di traccia WIF'
ms.date: 03/30/2017
ms.assetid: 3d51ba59-3adb-4ca4-bd33-5027531af687
author: BrucePerlerMS
ms.openlocfilehash: 43fa859aa84189817dffe74ecd72253ab9b82585
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321549"
---
# <a name="how-to-debug-claims-aware-applications-and-services-using-wif-tracing"></a><span data-ttu-id="3db76-102">Procedura: Eseguire il debug di servizi e applicazioni in grado di riconoscere attestazioni con le funzionalità di traccia WIF</span><span class="sxs-lookup"><span data-stu-id="3db76-102">How To: Debug Claims-Aware Applications And Services Using WIF Tracing</span></span>
## <a name="applies-to"></a><span data-ttu-id="3db76-103">Si applica a</span><span class="sxs-lookup"><span data-stu-id="3db76-103">Applies To</span></span>  
  
-   <span data-ttu-id="3db76-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="3db76-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="3db76-105">Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="3db76-105">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>  
  
-   <span data-ttu-id="3db76-106">Risoluzione dei problemi e debug di applicazioni WIF</span><span class="sxs-lookup"><span data-stu-id="3db76-106">Troubleshooting and Debugging WIF Applications</span></span>  
  
## <a name="summary"></a><span data-ttu-id="3db76-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3db76-107">Summary</span></span>  
 <span data-ttu-id="3db76-108">Questa procedura descrive i passaggi necessari per configurare le funzionalità di traccia di WIF, raccogliere i log di traccia e analizzarli mediante lo strumento visualizzatore di tracce dei servizi.</span><span class="sxs-lookup"><span data-stu-id="3db76-108">This How-To describes required steps for how to configure WIF tracing, collect trace logs, and how to analyze the trace logs using Trace Viewer tool.</span></span> <span data-ttu-id="3db76-109">Fornisce un mapping generale delle voci di traccia alle azioni necessarie per la risoluzione dei problemi correlati a WIF.</span><span class="sxs-lookup"><span data-stu-id="3db76-109">It provides general mapping for trace entries to actions needed to troubleshoot issues related to WIF.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="3db76-110">Sommario</span><span class="sxs-lookup"><span data-stu-id="3db76-110">Contents</span></span>  
  
-   <span data-ttu-id="3db76-111">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="3db76-111">Objectives</span></span>  
  
-   <span data-ttu-id="3db76-112">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="3db76-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="3db76-113">Passaggio 1 - Configurare le funzionalità di traccia di WIF usando il file Web.config</span><span class="sxs-lookup"><span data-stu-id="3db76-113">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
-   <span data-ttu-id="3db76-114">Passaggio 2 - Analizzare i file di traccia di WIF usando lo strumento visualizzatore di tracce dei servizi</span><span class="sxs-lookup"><span data-stu-id="3db76-114">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
-   <span data-ttu-id="3db76-115">Passaggio 3 - Identificare soluzioni per la risoluzione dei problemi correlati a WIF</span><span class="sxs-lookup"><span data-stu-id="3db76-115">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
-   <span data-ttu-id="3db76-116">Elementi correlati</span><span class="sxs-lookup"><span data-stu-id="3db76-116">Related Items</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="3db76-117">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="3db76-117">Objectives</span></span>  
  
-   <span data-ttu-id="3db76-118">Configurare le funzionalità di traccia WIF.</span><span class="sxs-lookup"><span data-stu-id="3db76-118">Configure WIF tracing.</span></span>  
  
-   <span data-ttu-id="3db76-119">Visualizzare i log di traccia nello strumento visualizzatore di tracce dei servizi.</span><span class="sxs-lookup"><span data-stu-id="3db76-119">View trace logs in the Trace Viewer tool.</span></span>  
  
-   <span data-ttu-id="3db76-120">Identificare i problemi relativi a WIF nei log di traccia.</span><span class="sxs-lookup"><span data-stu-id="3db76-120">Identify WIF related issues in the trace logs.</span></span>  
  
-   <span data-ttu-id="3db76-121">Applicare azioni correttive ai problemi correlati a WIF riscontrati nei log di traccia.</span><span class="sxs-lookup"><span data-stu-id="3db76-121">Apply corrective actions to WIF related issues found in the trace logs.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="3db76-122">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="3db76-122">Summary of Steps</span></span>  
  
-   <span data-ttu-id="3db76-123">Passaggio 1 - Configurare le funzionalità di traccia di WIF usando il file Web.config</span><span class="sxs-lookup"><span data-stu-id="3db76-123">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
-   <span data-ttu-id="3db76-124">Passaggio 2 - Analizzare i file di traccia di WIF usando lo strumento visualizzatore di tracce dei servizi</span><span class="sxs-lookup"><span data-stu-id="3db76-124">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
-   <span data-ttu-id="3db76-125">Passaggio 3 - Identificare soluzioni per la risoluzione dei problemi correlati a WIF</span><span class="sxs-lookup"><span data-stu-id="3db76-125">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
## <a name="step-1--configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="3db76-126">Passaggio 1 - Configurare le funzionalità di traccia di WIF usando il file Web.config</span><span class="sxs-lookup"><span data-stu-id="3db76-126">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
 <span data-ttu-id="3db76-127">In questo passaggio si aggiungeranno modifiche alle sezioni di configurazione del file *Web.config* in modo da abilitare la traccia e l'archiviazione degli eventi WIF in un log di traccia.</span><span class="sxs-lookup"><span data-stu-id="3db76-127">In this step, you will add changes to configuration sections in the *Web.config* file that enable WIF to trace its events and store them in a trace log.</span></span>  
  
#### <a name="to-configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="3db76-128">Per configurare le funzionalità di traccia di WIF usando il file Web.config</span><span class="sxs-lookup"><span data-stu-id="3db76-128">To configure WIF tracing using Web.config configuration file</span></span>  
  
1. <span data-ttu-id="3db76-129">Aprire il file di configurazione radice **Web.config** o **App.config** nell'editor di Visual Studio facendo doppio clic su di esso in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="3db76-129">Open the root **Web.config** or **App.config** configuration file in the Visual Studio editor by double clicking on it in **Solution Explorer**.</span></span> <span data-ttu-id="3db76-130">Se la soluzione non dispone di un file di configurazione **Web.config** o **App.config**, aggiungerlo facendo clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e scegliendo **Aggiungi**, quindi **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="3db76-130">If your solution does not have **Web.config** or **App.config** configuration file, add it by right clicking on the solution in the **Solution Explorer** and clicking **Add**, then clicking **New Item…**.</span></span> <span data-ttu-id="3db76-131">Nella finestra di dialogo **Nuovo elemento** selezionare **File di configurazione dell'applicazione** per **App.config** o **File di configurazione Web** per **Web.config** nell'elenco e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3db76-131">On the **New Item** dialog, Select **Application Configuration File** for **App.config** or **Web Configuration File** for **Web.config** from the list and click **OK**.</span></span>  
  
2. <span data-ttu-id="3db76-132">Aggiungere le voci di configurazione simili alla seguente al file di configurazione all'interno del nodo **\<configuration>** alla fine del file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="3db76-132">Add the configuration entries similar to the following to the configuration file inside **\<configuration>** node at the end of the configuration file:</span></span>  
  
    ```xml  
    <system.diagnostics>  
        <sources>  
            <source name="System.IdentityModel" switchValue="Verbose">  
                <listeners>  
                    <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="WIFTrace.e2e"/>  
                </listeners>  
            </source>  
        </sources>  
        <trace autoflush="true"/>  
    </system.diagnostics>  
    ```  
  
3. <span data-ttu-id="3db76-133">La configurazione precedente indica a WIF di generare eventi di traccia dettagliati e registrarli nel file *WIFTrace.e2e*.</span><span class="sxs-lookup"><span data-stu-id="3db76-133">The above configuration instructs WIF to generate verbose trace events and log them into *WIFTrace.e2e* file.</span></span> <span data-ttu-id="3db76-134">Per un elenco completo dei valori per il **switchValue** , fare riferimento alla tabella di livello di traccia nell'argomento seguente: [Configurazione della traccia](../wcf/diagnostics/tracing/configuring-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="3db76-134">For a complete list of values for the **switchValue** switch, refer to the Trace Level table found in the following topic: [Configuring Tracing](../wcf/diagnostics/tracing/configuring-tracing.md).</span></span>  
  
## <a name="step-2--analyze-wif-trace-files-using-trace-viewer-tool"></a><span data-ttu-id="3db76-135">Passaggio 2 - Analizzare i file di traccia di WIF usando lo strumento visualizzatore di tracce dei servizi</span><span class="sxs-lookup"><span data-stu-id="3db76-135">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
 <span data-ttu-id="3db76-136">In questo passaggio si userà lo strumento visualizzatore di tracce dei servizi (SvcTraceViewer.exe) per analizzare i log di traccia di WIF.</span><span class="sxs-lookup"><span data-stu-id="3db76-136">In this step, you will use the Trace Viewer Tool (SvcTraceViewer.exe) to analyze WIF trace logs.</span></span>  
  
#### <a name="to-analyze-wif-trace-logs-using-trace-viewer-tool-svctraceviewerexe"></a><span data-ttu-id="3db76-137">Per analizzare i log di traccia di WIF con lo strumento visualizzatore di tracce dei servizi (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="3db76-137">To analyze WIF trace logs using Trace Viewer tool (SvcTraceViewer.exe)</span></span>  
  
1. <span data-ttu-id="3db76-138">Lo strumento visualizzatore di tracce dei servizi (SvcTraceViewer.exe) è incluso in Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="3db76-138">Trace Viewer tool (SvcTraceViewer.exe) ships as part of the Windows SDK.</span></span> <span data-ttu-id="3db76-139">Se è già stato installato il SDK di Windows, è possibile scaricarlo qui: [Windows SDK](https://www.microsoft.com/download/en/details.aspx?id=8279).</span><span class="sxs-lookup"><span data-stu-id="3db76-139">If you haven’t already installed the Windows SDK, you can download it here: [Windows SDK](https://www.microsoft.com/download/en/details.aspx?id=8279).</span></span>  
  
2. <span data-ttu-id="3db76-140">Eseguire lo strumento visualizzatore di tracce dei servizi (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="3db76-140">Run the Trace Viewer tool (SvcTraceViewer.exe).</span></span> <span data-ttu-id="3db76-141">In genere è disponibile nella cartella **Bin** del percorso di installazione.</span><span class="sxs-lookup"><span data-stu-id="3db76-141">It is typically available in the **Bin** folder of the installation path.</span></span>  
  
3. <span data-ttu-id="3db76-142">Aprire il file di log di traccia di WIF, ad esempio, WIFTrace.e2e scegliendo **Apri** dal menu **File**</span><span class="sxs-lookup"><span data-stu-id="3db76-142">Open the WIF trace log file, for example, WIFTrace.e2e by selecting **File**, **Open…**</span></span> <span data-ttu-id="3db76-143">oppure usando la scelta rapida da tastiera **CTRL+O**.</span><span class="sxs-lookup"><span data-stu-id="3db76-143">option in the menu or using the **Ctrl+O** shortcut.</span></span> <span data-ttu-id="3db76-144">Il file di log di traccia verrà aperto nel visualizzatore di tracce dei servizi.</span><span class="sxs-lookup"><span data-stu-id="3db76-144">The trace log file opens in the Trace Viewer tool.</span></span>  
  
4. <span data-ttu-id="3db76-145">Esaminare le voci nella scheda **Attività**. Ogni voce contiene un numero di attività, il numero di tracce registrate, la durata dell'attività e i timestamp di inizio e fine.</span><span class="sxs-lookup"><span data-stu-id="3db76-145">Review entries in the **Activity** tab. Each entry should contain an activity number, the number of traces that were logged, duration of the activity and its start and end timestamps.</span></span>  
  
5. <span data-ttu-id="3db76-146">Fare clic sulla scheda **Attività**. Nell'area principale dello strumento saranno visibili le voci di traccia dettagliate.</span><span class="sxs-lookup"><span data-stu-id="3db76-146">Click on the **Activity** tab. You should see detailed trace entries in the main area of the tool.</span></span> <span data-ttu-id="3db76-147">Usare la **livello** elenco a discesa del menu per filtrare specifici a livello di traccia, ad esempio: **Tutti i**, **avviso**, **errori**, **informazioni**e così via.</span><span class="sxs-lookup"><span data-stu-id="3db76-147">Use the **Level** dropdown list on the menu to filter specific level of traces, for example: **All**, **Warning**, **Errors**, **Information**, etc.</span></span>  
  
6. <span data-ttu-id="3db76-148">Fare clic sulle specifiche voci di traccia per esaminare i dettagli nell'area inferiore dello strumento.</span><span class="sxs-lookup"><span data-stu-id="3db76-148">Click on specific trace entries to review the details in the lower area of the tool.</span></span> <span data-ttu-id="3db76-149">I dettagli sono disponibili nelle visualizzazioni **Formattato** e **XML** scegliendo le schede corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="3db76-149">The details can be viewed using **Formatted** and **XML** view by choosing corresponding tabs.</span></span>  
  
## <a name="step-3--identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="3db76-150">Passaggio 3 - Identificare soluzioni per la risoluzione dei problemi correlati a WIF</span><span class="sxs-lookup"><span data-stu-id="3db76-150">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
 <span data-ttu-id="3db76-151">Questo passaggio illustra come individuare soluzioni per i problemi correlati a WIF identificati mediante il log di traccia WIF e lo strumento visualizzatore di tracce dei servizi.</span><span class="sxs-lookup"><span data-stu-id="3db76-151">In this step, you can identify solutions for WIF-related issues identified by using the WIF trace log and Trace Viewer tool.</span></span> <span data-ttu-id="3db76-152">Illustra inoltre il mapping generale delle eccezioni correlate a WIF alle possibili soluzioni o alle azioni necessarie per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="3db76-152">It outlines general mapping of WIF related exceptions to potential solutions or required actions to troubleshoot the issue.</span></span>  
  
#### <a name="to-identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="3db76-153">Per identificare soluzioni per correggere i problemi correlati a WIF</span><span class="sxs-lookup"><span data-stu-id="3db76-153">To identify solutions to fix WIF related issues</span></span>  
  
1. <span data-ttu-id="3db76-154">Esaminare la tabella seguente di eccezioni WIF e le azioni necessarie per correggere i problemi.</span><span class="sxs-lookup"><span data-stu-id="3db76-154">Review the following table of WIF exceptions and the required actions to correct the issues.</span></span>  
  
|**<span data-ttu-id="3db76-155">ID errore</span><span class="sxs-lookup"><span data-stu-id="3db76-155">Error ID</span></span>**|**<span data-ttu-id="3db76-156">Messaggio di errore</span><span class="sxs-lookup"><span data-stu-id="3db76-156">Error Message</span></span>**|**<span data-ttu-id="3db76-157">Azione necessaria per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="3db76-157">Action needed to fix the error</span></span>**|  
|-|-|-|  
|<span data-ttu-id="3db76-158">ID4175</span><span class="sxs-lookup"><span data-stu-id="3db76-158">ID4175</span></span>|<span data-ttu-id="3db76-159">L'emittente del token di sicurezza non è stato riconosciuto da IssuerNameRegistry.</span><span class="sxs-lookup"><span data-stu-id="3db76-159">The issuer of the security token was not recognized by the IssuerNameRegistry.</span></span>  <span data-ttu-id="3db76-160">Per accettare token di sicurezza da questa autorità emittente, configurare IssuerNameRegistry per restituire un nome valido per l'emittente.</span><span class="sxs-lookup"><span data-stu-id="3db76-160">To accept security tokens from this issuer, configure the IssuerNameRegistry to return a valid name for this issuer.</span></span>|<span data-ttu-id="3db76-161">L'errore può essere causato dall'aver copiato un'identificazione personale dallo snap-in MMC e averla poi incollata nel file *Web. config*.</span><span class="sxs-lookup"><span data-stu-id="3db76-161">This error can be caused by copying a thumbprint from the MMC snap-in and pasting it into the *Web.config* file.</span></span> <span data-ttu-id="3db76-162">In particolare, copiando dalla finestra delle proprietà del certificato è possibile ottenere un carattere aggiuntivo non stampabile nella stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="3db76-162">Specifically, you can get an extra non-printable character in the text string when copying from the certificate properties window.</span></span> <span data-ttu-id="3db76-163">Questo carattere aggiuntivo provoca l'esito negativo della corrispondenza identificazione personale. La procedura per copiare correttamente l'identificazione personale è reperibile in [basata sulle attestazioni l'accesso Single Sign-in per il Web e Microsoft Azure](https://docs.microsoft.com/previous-versions/msp-n-p/ff359102%28v=pandp.10%29).</span><span class="sxs-lookup"><span data-stu-id="3db76-163">This extra character causes the thumbprint match to fail.The procedure for correctly copying the thumbprint can be found at [Claims-Based Single Sign-On for the Web and Microsoft Azure](https://docs.microsoft.com/previous-versions/msp-n-p/ff359102%28v=pandp.10%29).</span></span>|  
  
## <a name="related-items"></a><span data-ttu-id="3db76-164">Elementi correlati</span><span class="sxs-lookup"><span data-stu-id="3db76-164">Related Items</span></span>  
  
-   [<span data-ttu-id="3db76-165">Uso di Service Trace Viewer per la visualizzazione di tracce correlate e risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="3db76-165">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)

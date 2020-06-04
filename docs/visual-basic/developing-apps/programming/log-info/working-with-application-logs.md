---
title: Utilizzo dei log applicazione
ms.date: 07/20/2015
helpviewer_keywords:
- logs, application
- application event logs, Visual Basic
- application event logs
ms.assetid: 2581afd1-5791-4bc4-86b2-46244e9fe468
ms.openlocfilehash: e33efac8f65832c87d5c9271eba25c2ca1d1803b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387595"
---
# <a name="working-with-application-logs-in-visual-basic"></a><span data-ttu-id="d7c02-102">Utilizzo dei log applicazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d7c02-102">Working with Application Logs in Visual Basic</span></span>

<span data-ttu-id="d7c02-103">Gli oggetti `My.Application.Log` e `My.Log` consentono di scrivere facilmente nei log le informazioni di registrazione e di traccia.</span><span class="sxs-lookup"><span data-stu-id="d7c02-103">The `My.Application.Log` and `My.Log` objects make it easy to write logging and tracing information to logs.</span></span>

## <a name="how-messages-are-logged"></a><span data-ttu-id="d7c02-104">Modalità di registrazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="d7c02-104">How Messages are Logged</span></span>

<span data-ttu-id="d7c02-105">Viene verificata innanzitutto la gravità del messaggio con la proprietà <xref:System.Diagnostics.TraceSource.Switch%2A> della proprietà <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> del log.</span><span class="sxs-lookup"><span data-stu-id="d7c02-105">First, the severity of the message is checked with the <xref:System.Diagnostics.TraceSource.Switch%2A> property of the log's <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> property.</span></span> <span data-ttu-id="d7c02-106">Per impostazione predefinita, solo i messaggi con il livello di gravità "Informazione" o un livello superiore vengono inviati ai listener di traccia, specificati nella raccolta `TraceListener` del log.</span><span class="sxs-lookup"><span data-stu-id="d7c02-106">By default, only messages of severity "Information" and higher are passed on to the trace listeners, specified in the log's `TraceListener` collection.</span></span> <span data-ttu-id="d7c02-107">Ogni listener confronta quindi la gravità del messaggio con la proprietà <xref:System.Diagnostics.TraceSource.Switch%2A> del listener.</span><span class="sxs-lookup"><span data-stu-id="d7c02-107">Then, each listener compares the severity of the message to the listener's <xref:System.Diagnostics.TraceSource.Switch%2A> property.</span></span> <span data-ttu-id="d7c02-108">Se la gravità del messaggio è abbastanza elevata, il listener scrive il messaggio.</span><span class="sxs-lookup"><span data-stu-id="d7c02-108">If the message's severity is high enough, the listener writes out the message.</span></span>

<span data-ttu-id="d7c02-109">Il diagramma seguente mostra il modo in cui un messaggio scritto nel metodo `WriteEntry` viene inviato ai metodi `WriteLine` dei listener di traccia del log:</span><span class="sxs-lookup"><span data-stu-id="d7c02-109">The following diagram shows how a message written to the `WriteEntry` method gets passed to the `WriteLine` methods of the log's trace listeners:</span></span>

![Diagramma che illustra una chiamata a My Log.](./media/working-with-application-logs/my-log-call-messages.png)

<span data-ttu-id="d7c02-111">È possibile modificare il comportamento del log e dei listener di traccia modificando il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7c02-111">You can change the behavior of the log and the trace listeners by changing the application's configuration file.</span></span> <span data-ttu-id="d7c02-112">Il diagramma seguente mostra la corrispondenza tra le parti del log e il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d7c02-112">The following diagram shows the correspondence between the parts of the log and the configuration file.</span></span>

![Diagramma che illustra la configurazione di My Log.](./media/working-with-application-logs/my-log-configuration.png)

## <a name="where-messages-are-logged"></a><span data-ttu-id="d7c02-114">Posizione di registrazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="d7c02-114">Where Messages are Logged</span></span>

<span data-ttu-id="d7c02-115">Se l'assembly non contiene un file di configurazione, gli oggetti `My.Application.Log` e `My.Log` scrivono nell'output di debug dell'applicazione, tramite la classe <xref:System.Diagnostics.DefaultTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="d7c02-115">If the assembly has no configuration file, the `My.Application.Log` and `My.Log` objects write to the application's debug output (through the <xref:System.Diagnostics.DefaultTraceListener> class).</span></span> <span data-ttu-id="d7c02-116">Inoltre, l'oggetto `My.Application.Log` scrive nel file di log dell'assembly, tramite la classe <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> , mentre l'oggetto `My.Log` scrive nell'output della pagina Web ASP.NET, tramite la classe <xref:System.Web.WebPageTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="d7c02-116">In addition, the `My.Application.Log` object writes to the assembly's log file (through the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class), while the `My.Log` object writes to the ASP.NET Web page's output (through the <xref:System.Web.WebPageTraceListener> class).</span></span>

<span data-ttu-id="d7c02-117">L'output di debug può essere visualizzato nella finestra **Output** di Visual Studio quando si esegue l'applicazione in modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="d7c02-117">The debug output can be viewed in the Visual Studio **Output** window when running your application in debug mode.</span></span> <span data-ttu-id="d7c02-118">Per aprire la finestra **Output** , scegliere **Finestre** dal menu **Debug**, quindi fare clic su **Output**.</span><span class="sxs-lookup"><span data-stu-id="d7c02-118">To open the **Output** window, click the **Debug** menu item, point to **Windows**, and then click **Output**.</span></span> <span data-ttu-id="d7c02-119">Nella finestra **Output** selezionare **Debug** dall'elenco **Mostra output di** .</span><span class="sxs-lookup"><span data-stu-id="d7c02-119">In the **Output** window, select **Debug** from the **Show output from** box.</span></span>

<span data-ttu-id="d7c02-120">Per impostazione predefinita, `My.Application.Log` scrive il file di log nel percorso dei dati applicazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d7c02-120">By default, `My.Application.Log` writes the log file in the path for the user's application data.</span></span> <span data-ttu-id="d7c02-121">È possibile ottenere il percorso dalla proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> dell'oggetto <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> .</span><span class="sxs-lookup"><span data-stu-id="d7c02-121">You can get the path from the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> property of the <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> object.</span></span> <span data-ttu-id="d7c02-122">Il formato del percorso è il seguente:</span><span class="sxs-lookup"><span data-stu-id="d7c02-122">The format of that path is as follows:</span></span>

`BasePath`\\`CompanyName`\\`ProductName`\\`ProductVersion`

<span data-ttu-id="d7c02-123">Di seguito è riportato un tipico valore per `BasePath` .</span><span class="sxs-lookup"><span data-stu-id="d7c02-123">A typical value for `BasePath` is as follows.</span></span>

<span data-ttu-id="d7c02-124">C:\Documents and Settings\\\`username\`\Dati applicazioni</span><span class="sxs-lookup"><span data-stu-id="d7c02-124">C:\Documents and Settings\\`username`\Application Data</span></span>

<span data-ttu-id="d7c02-125">I valori di `CompanyName`, `ProductName`e `ProductVersion` provengono dalle informazioni sull'assembly dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7c02-125">The values of `CompanyName`, `ProductName`, and `ProductVersion` come from the application's assembly information.</span></span> <span data-ttu-id="d7c02-126">Il formato del nome del file di log è *NomeAssembly*.log, dove *NomeAssembly* è il nome file dell'assembly senza estensione.</span><span class="sxs-lookup"><span data-stu-id="d7c02-126">The form of the log file name is *AssemblyName*.log, where *AssemblyName* is the file name of the assembly without the extension.</span></span> <span data-ttu-id="d7c02-127">Se è necessario più di un file di log, ad esempio quando il log originale non è disponibile quando l'applicazione tenta di scrivere nel log, il formato per il nome del file di log è *AssemblyName* - *Iteration*. log, dove `iteration` è un positivo `Integer` .</span><span class="sxs-lookup"><span data-stu-id="d7c02-127">If more than one log file is needed, such as when the original log is unavailable when the application attempts to write to the log, the form for the log file name is *AssemblyName*-*iteration*.log, where `iteration` is a positive `Integer`.</span></span>

<span data-ttu-id="d7c02-128">È possibile eseguire l'override del comportamento predefinito aggiungendo o modificando i file di configurazione del computer e dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7c02-128">You can override the default behavior by adding or changing the computer's and the application's configuration files.</span></span> <span data-ttu-id="d7c02-129">Per altre informazioni, vedere [Procedura dettagliata: modifica della posizione di inserimento delle informazioni con My.Application.Log](walkthrough-changing-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="d7c02-129">For more information, see [Walkthrough: Changing Where My.Application.Log Writes Information](walkthrough-changing-where-my-application-log-writes-information.md).</span></span>

## <a name="configuring-log-settings"></a><span data-ttu-id="d7c02-130">Configurazione delle impostazioni del log</span><span class="sxs-lookup"><span data-stu-id="d7c02-130">Configuring Log Settings</span></span>

<span data-ttu-id="d7c02-131">L' `Log` oggetto ha un'implementazione predefinita che funziona senza un file di configurazione dell'applicazione, app. config. Per modificare i valori predefiniti, è necessario aggiungere un file di configurazione con le nuove impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d7c02-131">The `Log` object has a default implementation that works without an application configuration file, app.config. To change the defaults, you must add a configuration file with the new settings.</span></span> <span data-ttu-id="d7c02-132">Per altre informazioni, vedere [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="d7c02-132">For more information, see [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).</span></span>

<span data-ttu-id="d7c02-133">Le sezioni della configurazione del log si trovano nel nodo `<system.diagnostics>` all'interno del nodo principale `<configuration>` del file app.config.</span><span class="sxs-lookup"><span data-stu-id="d7c02-133">The log configuration sections are located in the `<system.diagnostics>` node in the main `<configuration>` node of the app.config file.</span></span> <span data-ttu-id="d7c02-134">Le informazioni del log vengono definite in diversi nodi:</span><span class="sxs-lookup"><span data-stu-id="d7c02-134">Log information is defined in several nodes:</span></span>

- <span data-ttu-id="d7c02-135">I listener per l'oggetto `Log` vengono definiti nel nodo `<sources>` denominato DefaultSource.</span><span class="sxs-lookup"><span data-stu-id="d7c02-135">The listeners for the `Log` object are defined in the `<sources>` node named DefaultSource.</span></span>

- <span data-ttu-id="d7c02-136">Il filtro della gravità per l'oggetto `Log` viene definito nel nodo `<switches>` denominato DefaultSwitch.</span><span class="sxs-lookup"><span data-stu-id="d7c02-136">The severity filter for the `Log` object is defined in the `<switches>` node named DefaultSwitch.</span></span>

- <span data-ttu-id="d7c02-137">I listener di log vengono definiti nel nodo `<sharedListeners>` .</span><span class="sxs-lookup"><span data-stu-id="d7c02-137">The log listeners are defined in the `<sharedListeners>` node.</span></span>

 <span data-ttu-id="d7c02-138">Esempi dei nodi `<sources>`, `<switches>`e `<sharedListeners>` sono illustrati nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d7c02-138">Examples of `<sources>`, `<switches>`, and `<sharedListeners>` nodes are shown in the following code:</span></span>

```xml
<configuration>
  <system.diagnostics>
    <sources>
      <source name="DefaultSource" switchName="DefaultSwitch">
        <listeners>
          <add name="FileLog"/>
        </listeners>
      </source>
    </sources>
    <switches>
      <add name="DefaultSwitch" value="Information" />
    </switches>
    <sharedListeners>
      <add name="FileLog"
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
          Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,
          PublicKeyToken=b03f5f7f11d50a3a, processorArchitecture=MSIL"
        initializeData="FileLogWriter"
      />
    </sharedListeners>
  </system.diagnostics>
</configuration>
```

## <a name="changing-log-settings-after-deployment"></a><span data-ttu-id="d7c02-139">Modifica delle impostazioni del log dopo la distribuzione</span><span class="sxs-lookup"><span data-stu-id="d7c02-139">Changing Log Settings after Deployment</span></span>

<span data-ttu-id="d7c02-140">Quando si sviluppa un'applicazione, le relative impostazioni di configurazione vengono archiviate nel file app.config, come illustrato negli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="d7c02-140">When you develop an application, its configuration settings are stored in the app.config file, as shown in the examples above.</span></span> <span data-ttu-id="d7c02-141">Dopo aver distribuito l'applicazione, è ancora possibile configurare il log modificando il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d7c02-141">After you deploy your application, you can still configure the log by editing the configuration file.</span></span> <span data-ttu-id="d7c02-142">In un'applicazione basata su Windows, il nome di questo file è *NomeApplicazione*.exe.config e il file deve risiedere nella stessa cartella del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="d7c02-142">In a Windows-based application, this file's name is *applicationName*.exe.config, and it must reside in the same folder as the executable file.</span></span> <span data-ttu-id="d7c02-143">In caso di applicazioni Web si tratta del file Web.config associato al progetto.</span><span class="sxs-lookup"><span data-stu-id="d7c02-143">For a Web application, this is the Web.config file associated with the project.</span></span>

<span data-ttu-id="d7c02-144">Quando l'applicazione esegue il codice che crea un'istanza di una classe per la prima volta, viene verificata la presenza di informazioni sull'oggetto nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d7c02-144">When your application executes the code that creates an instance of a class for the first time, it checks the configuration file for information about the object.</span></span> <span data-ttu-id="d7c02-145">Per l'oggetto `Log` , questa operazione viene eseguita la prima volta che si accede all'oggetto `Log` .</span><span class="sxs-lookup"><span data-stu-id="d7c02-145">For the `Log` object, this happens the first time the `Log` object is accessed.</span></span> <span data-ttu-id="d7c02-146">Il file di configurazione viene esaminato dal sistema solo una volta per ogni oggetto, ovvero la prima volta che l'oggetto viene creato dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7c02-146">The system examines the configuration file only once for any particular object—the first time your application creates the object.</span></span> <span data-ttu-id="d7c02-147">Per rendere effettive le modifiche è necessario quindi riavviare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7c02-147">Therefore, you may need to restart the application for the changes to take effect.</span></span>

<span data-ttu-id="d7c02-148">In un'applicazione distribuita, il codice di traccia viene abilitato riconfigurando gli oggetti opzione prima che l'applicazione venga avviata.</span><span class="sxs-lookup"><span data-stu-id="d7c02-148">In a deployed application, you enable trace code by reconfiguring switch objects before your application starts.</span></span> <span data-ttu-id="d7c02-149">In genere, questo implica l'attivazione e la disattivazione degli oggetti opzione o la modifica dei livelli di traccia, quindi il riavvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7c02-149">Typically, this involves turning the switch objects on and off or by changing the tracing levels, and then restarting your application.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="d7c02-150">Considerazioni relative alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="d7c02-150">Security Considerations</span></span>

<span data-ttu-id="d7c02-151">Durante la scrittura di dati nel log tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d7c02-151">Consider the following when writing data to the log:</span></span>

- <span data-ttu-id="d7c02-152">**Assicurarsi che siano fornite tutte le informazioni utente.**</span><span class="sxs-lookup"><span data-stu-id="d7c02-152">**Avoid leaking user information.**</span></span> <span data-ttu-id="d7c02-153">Assicurarsi che nel log dell'applicazione vengano scritte solo informazioni approvate.</span><span class="sxs-lookup"><span data-stu-id="d7c02-153">Ensure that your application writes only approved information to the log.</span></span> <span data-ttu-id="d7c02-154">Ad esempio, il log dell'applicazione può contenere i nomi degli utenti ma non le password.</span><span class="sxs-lookup"><span data-stu-id="d7c02-154">For example, it may be acceptable for the application log to contain user names, but not user passwords.</span></span>

- <span data-ttu-id="d7c02-155">**Proteggere le posizioni del log.**</span><span class="sxs-lookup"><span data-stu-id="d7c02-155">**Make log locations secure.**</span></span> <span data-ttu-id="d7c02-156">Tutti i log contenenti informazioni potenzialmente riservate devono essere archiviati in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="d7c02-156">Any log that contains potentially sensitive information should be stored in a secure location.</span></span>

- <span data-ttu-id="d7c02-157">**Evitare informazioni fuorvianti.**</span><span class="sxs-lookup"><span data-stu-id="d7c02-157">**Avoid misleading information.**</span></span> <span data-ttu-id="d7c02-158">In generale, l'applicazione deve convalidare tutti i dati immessi da un utente prima di poterli usare.</span><span class="sxs-lookup"><span data-stu-id="d7c02-158">In general, your application should validate all data entered by a user before using that data.</span></span> <span data-ttu-id="d7c02-159">Questo vale anche per la scrittura dei dati nel log dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7c02-159">This includes writing data to the application log.</span></span>

- <span data-ttu-id="d7c02-160">**Evitare Denial of Service.**</span><span class="sxs-lookup"><span data-stu-id="d7c02-160">**Avoid denial of service.**</span></span> <span data-ttu-id="d7c02-161">Se nel log dell'applicazione viene scritta una quantità eccessiva di informazioni, il log potrebbe riempirsi o potrebbe essere difficile trovare le informazioni importanti.</span><span class="sxs-lookup"><span data-stu-id="d7c02-161">If your application writes too much information to the log, it could fill the log or make finding important information difficult.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7c02-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7c02-162">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="d7c02-163">Registrazione di informazioni relative all'applicazione</span><span class="sxs-lookup"><span data-stu-id="d7c02-163">Logging Information from the Application</span></span>](index.md)

---
title: 'Procedura: Creare, inizializzare e configurare opzioni di traccia'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- trace switches, configuring
- tracing [.NET Framework], trace switches
- switches, trace
- tracing [.NET Framework], enabling or disabling
- Web.config configuration file, trace switches
ms.assetid: 5a0e41bf-f99c-4692-8799-f89617f5bcf9
ms.openlocfilehash: 358e34b2ce5d896ba02b343ce060604f2d42eeeb
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216485"
---
# <a name="how-to-create-initialize-and-configure-trace-switches"></a><span data-ttu-id="d6d1e-102">Procedura: Creare, inizializzare e configurare opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="d6d1e-102">How to: Create, Initialize and Configure Trace Switches</span></span>
<span data-ttu-id="d6d1e-103">Le opzioni di traccia consentono di abilitare, disabilitare e filtrare l'output di traccia.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-103">Trace switches enable you to enable, disable, and filter tracing output.</span></span>  
  
<a name="create"></a>   
## <a name="creating-and-initializing-a-trace-switch"></a><span data-ttu-id="d6d1e-104">Creazione e inizializzazione di un'opzione di traccia</span><span class="sxs-lookup"><span data-stu-id="d6d1e-104">Creating and initializing a trace switch</span></span>  
 <span data-ttu-id="d6d1e-105">Per usare le opzioni di traccia, è necessario prima di tutto crearle e inserirle nel codice.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-105">In order to use trace switches, you must first create them and place them in your code.</span></span> <span data-ttu-id="d6d1e-106">Sono presenti due classi predefinite da cui è possibile creare oggetti opzione: <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> e <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-106">There are two predefined classes from which you can create switch objects: the <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> class and the <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="d6d1e-107">Si utilizza l'oggetto <xref:System.Diagnostics.BooleanSwitch> solo se è necessario stabilire se i messaggi di traccia vengono visualizzati; l'oggetto <xref:System.Diagnostics.TraceSwitch> viene invece utilizzato se è necessario distinguere tra i livelli di traccia.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-107">You would use <xref:System.Diagnostics.BooleanSwitch> if you care only about whether or not a tracing message appears; you would use <xref:System.Diagnostics.TraceSwitch> if you want to discriminate between levels of tracing.</span></span> <span data-ttu-id="d6d1e-108">Se si utilizza un oggetto <xref:System.Diagnostics.TraceSwitch> è possibile definire messaggi di debug personalizzati e associarli a diversi livelli di traccia.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-108">If you use a <xref:System.Diagnostics.TraceSwitch>, you can define your own debugging messages and associate them with different trace levels.</span></span> <span data-ttu-id="d6d1e-109">È possibile usare entrambi i tipi di opzioni sia per la traccia sia per il debug.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-109">You can use both types of switches with either tracing or debugging.</span></span> <span data-ttu-id="d6d1e-110">Per impostazione predefinita, un oggetto <xref:System.Diagnostics.BooleanSwitch> è disabilitato e un oggetto <xref:System.Diagnostics.TraceSwitch> è impostato sul livello <xref:System.Diagnostics.TraceLevel.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-110">By default, a <xref:System.Diagnostics.BooleanSwitch> is disabled and a <xref:System.Diagnostics.TraceSwitch> is set to level <xref:System.Diagnostics.TraceLevel.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d6d1e-111">È possibile creare e inserire opzioni di traccia in un punto qualsiasi del codice in cui possano essere usate.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-111">Trace switches can be created and placed in any part of your code that might use them.</span></span>  
  
 <span data-ttu-id="d6d1e-112">Nonostante sia possibile impostare i livelli di traccia e altre opzioni di configurazione all'interno del codice, è consigliabile utilizzare il file di configurazione per gestire lo stato delle opzioni.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-112">Although you can set trace levels and other configuration options in code, we recommend that you use the configuration file to manage the state of your switches.</span></span> <span data-ttu-id="d6d1e-113">Questo perché la gestione della configurazione delle opzioni nel sistema di configurazione consente una maggiore flessibilità: è infatti possibile attivare e disattivare diverse opzioni e modificare i livelli senza ricompilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-113">This is because managing the configuration of your switches in the configuration system gives you greater flexibility — you can turn on and off various switches and change levels without recompiling your application.</span></span>  
  
#### <a name="to-create-and-initialize-a-trace-switch"></a><span data-ttu-id="d6d1e-114">Per creare e inizializzare un'opzione di traccia</span><span class="sxs-lookup"><span data-stu-id="d6d1e-114">To create and initialize a trace switch</span></span>  
  
1. <span data-ttu-id="d6d1e-115">Definire un'opzione di tipo <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> o <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType> e impostare il nome e la descrizione dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-115">Define a switch as either type <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> or type <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType> and set the name and description of the switch.</span></span>  
  
2. <span data-ttu-id="d6d1e-116">Configurare l'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-116">Configure your trace switch.</span></span> <span data-ttu-id="d6d1e-117">Per altre informazioni, vedere [Configurazione delle opzioni di traccia](#configure).</span><span class="sxs-lookup"><span data-stu-id="d6d1e-117">For more information, see [Configuring trace switches](#configure).</span></span>  
  
     <span data-ttu-id="d6d1e-118">Il codice seguente crea due opzioni, una per ogni tipo:</span><span class="sxs-lookup"><span data-stu-id="d6d1e-118">The following code creates two switches, one of each type:</span></span>  
  
    ```vb  
    Dim dataSwitch As New BooleanSwitch("Data", "DataAccess module")  
    Dim generalSwitch As New TraceSwitch("General", "Entire application")  
    ```  
  
    ```csharp  
    System.Diagnostics.BooleanSwitch dataSwitch =   
       new System.Diagnostics.BooleanSwitch("Data", "DataAccess module");  
    System.Diagnostics.TraceSwitch generalSwitch =   
       new System.Diagnostics.TraceSwitch("General",   
       "Entire application");  
    ```  
  
<a name="configure"></a>   
## <a name="configuring-trace-switches"></a><span data-ttu-id="d6d1e-119">Configurazione di opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="d6d1e-119">Configuring trace switches</span></span>  
 <span data-ttu-id="d6d1e-120">Una volta distribuita l'applicazione, è ancora possibile attivare o disabilitare l'output di traccia configurando le opzioni di traccia dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-120">After your application has been distributed, you can still enable or disable trace output by configuring the trace switches in your application.</span></span> <span data-ttu-id="d6d1e-121">Configurare un'opzione significa modificarne il valore da un'origine esterna una volta inizializzata.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-121">Configuring a switch means changing its value from an external source after it has been initialized.</span></span> <span data-ttu-id="d6d1e-122">È possibile modificare i valori degli oggetti opzione mediante il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-122">You can change the values of the switch objects using the configuration file.</span></span> <span data-ttu-id="d6d1e-123">Si configura un'opzione di traccia per attivarla e disabilitarla oppure per impostarne il livello, determinando la quantità e il tipo di messaggi da inviare ai listener.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-123">You configure a trace switch to turn it on and off, or to set its level, determining the amount and type of messages it passes along to listeners.</span></span>  
  
 <span data-ttu-id="d6d1e-124">Le opzioni vengono configurate tramite il file CONFIG.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-124">Your switches are configured using the .config file.</span></span> <span data-ttu-id="d6d1e-125">In caso di applicazioni Web si tratta del file Web.config associato al progetto.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-125">For a Web application, this is the Web.config file associated with the project.</span></span> <span data-ttu-id="d6d1e-126">In un'applicazione Windows, questo file è denominato (nome applicazione). exe. config. In un'applicazione distribuita, questo file deve trovarsi nella stessa cartella del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-126">In a Windows application, this file is named (application name).exe.config. In a deployed application, this file must reside in the same folder as the executable.</span></span>  
  
 <span data-ttu-id="d6d1e-127">Quando l'applicazione esegue il codice che crea un'istanza di un'opzione per la prima volta, viene verificata la presenza nel file di configurazione di informazioni sul livello di traccia relative all'opzione denominata.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-127">When your application executes the code that creates an instance of a switch for the first time, it checks the configuration file for trace-level information about the named switch.</span></span> <span data-ttu-id="d6d1e-128">Il file di configurazione viene esaminato dal sistema di tracciatura solo una volta per ogni opzione, la prima volta che l'opzione in questione viene creata dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-128">The tracing system examines the configuration file only once for any particular switch — the first time your application creates the switch.</span></span>  
  
 <span data-ttu-id="d6d1e-129">In un'applicazione distribuita, il codice di traccia viene abilitato riconfigurando gli oggetti opzione quando l'applicazione non è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-129">In a deployed application, you enable trace code by reconfiguring switch objects when your application is not running.</span></span> <span data-ttu-id="d6d1e-130">In genere questo implica l'attivazione e la disattivazione degli oggetti opzione o la modifica dei livelli di traccia, quindi il riavvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-130">Typically this involves turning the switch objects on and off or by changing the tracing levels, and then restarting your application.</span></span>  
  
 <span data-ttu-id="d6d1e-131">Quando si crea un'istanza di un'opzione, la si inizializza anche specificando due argomenti: un argomento *displayName* e un argomento *description*.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-131">When you create an instance of a switch, you also initialize it by specifying two arguments: a *displayName* argument and a *description* argument.</span></span> <span data-ttu-id="d6d1e-132">L'argomento *displayName* del costruttore imposta la proprietà <xref:System.Diagnostics.Switch.DisplayName%2A?displayProperty=nameWithType> dell'istanza della classe <xref:System.Diagnostics.Switch>.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-132">The *displayName* argument of the constructor sets the <xref:System.Diagnostics.Switch.DisplayName%2A?displayProperty=nameWithType> property of the <xref:System.Diagnostics.Switch> class instance.</span></span> <span data-ttu-id="d6d1e-133">L'argomento *displayName* rappresenta il nome usato per configurare l'opzione nel file CONFIG, mentre l'argomento *description* restituisce una breve descrizione dell'opzione e dei messaggi che controlla.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-133">The *displayName* is the name that is used to configure the switch in the .config file, and the *description* argument should return a brief description of the switch and what messages it controls.</span></span>  
  
 <span data-ttu-id="d6d1e-134">Oltre a specificare il nome di un'opzione da configurare, è necessario specificare un valore per l'opzione.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-134">In addition to specifying the name of a switch to configure, you must also specify a value for the switch.</span></span> <span data-ttu-id="d6d1e-135">Tale valore deve essere Integer.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-135">This value is an Integer.</span></span> <span data-ttu-id="d6d1e-136">Per <xref:System.Diagnostics.BooleanSwitch>, un valore pari a 0 corrisponde a **Off**, mentre un valore diverso da 0 corrisponde a **On**.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-136">For <xref:System.Diagnostics.BooleanSwitch>, a value of 0 corresponds to **Off**, and any nonzero value corresponds to **On**.</span></span> <span data-ttu-id="d6d1e-137">Per la classe <xref:System.Diagnostics.TraceSwitch>, 0,1,2,3 e 4 corrispondono rispettivamente a **Off**, **Error**, **Warning**, **Info** e **Verbose**.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-137">For <xref:System.Diagnostics.TraceSwitch>, 0,1,2,3, and 4 correspond **Off**, **Error**, **Warning**, **Info**, and **Verbose**, respectively.</span></span> <span data-ttu-id="d6d1e-138">Tutti i numeri maggiori di 4 vengono considerati come **Verbose**, tutti i numeri minori di zero vengono considerati **Off**.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-138">Any number greater than 4 is treated as **Verbose**, and any number less than zero is treated as **Off**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6d1e-139">In .NET Framework versione 2.0 è possibile usare testo per specificare il valore di un'opzione,</span><span class="sxs-lookup"><span data-stu-id="d6d1e-139">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="d6d1e-140">ad esempio `true` per la classe <xref:System.Diagnostics.BooleanSwitch> o il testo che rappresenta un valore di enumerazione, come `Error` per la classe <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-140">For example, `true` for a <xref:System.Diagnostics.BooleanSwitch> or the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="d6d1e-141">La riga `<add name="myTraceSwitch" value="Error" />` equivale a `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-141">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
 <span data-ttu-id="d6d1e-142">Per consentire all'utente finale di configurare un'opzione di traccia di un'applicazione, è necessario fornire una documentazione dettagliata delle opzioni nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-142">In order for end users to be able to configure an application's trace switches, you must provide detailed documentation on the switches in your application.</span></span> <span data-ttu-id="d6d1e-143">Devono essere descritte in dettaglio le opzioni, ciò che controllano e le modalità di attivazione e disattivazione.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-143">You should detail which switches control what and how to turn them on and off.</span></span> <span data-ttu-id="d6d1e-144">È inoltre necessario fornire all'utente finale un file CONFIG dotato di una Guida adeguata nei commenti.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-144">You should also provide your end user with a .config file that has appropriate Help in the comments.</span></span>  
  
#### <a name="to-configure-trace-switches"></a><span data-ttu-id="d6d1e-145">Per configurare opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="d6d1e-145">To configure trace switches</span></span>  
  
1. <span data-ttu-id="d6d1e-146">Per usare le opzioni di traccia, è necessario prima di tutto crearle e inserirle nel codice, come descritto nella sezione [Creazione e inizializzazione di un'opzione di traccia](#create).</span><span class="sxs-lookup"><span data-stu-id="d6d1e-146">In order to use trace switches, you must first create them and place them in your code as described in the section [Creating and initializing a trace switch](#create).</span></span>  
  
2. <span data-ttu-id="d6d1e-147">Se il progetto non contiene un file di configurazione (app.config o Web.config), scegliere **Aggiungi nuovo elemento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-147">If your project does not contain a configuration file (app.config or Web.config), then from the **Project** menu, select **Add New Item**.</span></span>  
  
    - <span data-ttu-id="d6d1e-148">**Visual Basic:** nella finestra di dialogo **Aggiungi nuovo elemento** scegliere **File di configurazione dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-148">**Visual Basic:** In the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
         <span data-ttu-id="d6d1e-149">Verrà creato e aperto il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-149">The application configuration file is created and opened.</span></span> <span data-ttu-id="d6d1e-150">Si tratta di un documento XML il cui elemento radice è `<configuration>.`</span><span class="sxs-lookup"><span data-stu-id="d6d1e-150">This is an XML document whose root element is `<configuration>.`</span></span>  
  
    - <span data-ttu-id="d6d1e-151">**Visual C#:** nella finestra di dialogo **Aggiungi nuovo elemento** fare clic su **File XML**.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-151">**Visual C#:** In the **Add New Item** dialog box, choose **XML File**.</span></span> <span data-ttu-id="d6d1e-152">Assegnare un nome al file **app. config**. Nell'editor XML, dopo la dichiarazione XML, aggiungere il codice XML seguente:</span><span class="sxs-lookup"><span data-stu-id="d6d1e-152">Name this file **app.config**. In the XML editor, after the XML declaration, add the following XML:</span></span>  
  
        ```xml  
        <configuration>  
        </configuration>  
        ```  
  
         <span data-ttu-id="d6d1e-153">Una volta compilato il progetto, il file app.config viene copiato nella cartella di output del progetto e rinominato *nomeapplicazione*.exe.config.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-153">When your project is compiled, the app.config file is copied to the project output folder and is renamed *applicationname*.exe.config.</span></span>  
  
3. <span data-ttu-id="d6d1e-154">Dopo il tag `<configuration>`, ma prima del tag `</configuration>`, aggiungere il codice XML appropriato per la configurazione delle opzioni.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-154">After the `<configuration>` tag but before the `</configuration>` tag, add the appropriate XML to configure your switches.</span></span> <span data-ttu-id="d6d1e-155">Gli esempi seguenti illustrano un oggetto **BooleanSwitch** con una proprietà **DisplayName** di `DataMessageSwitch` e un oggetto **TraceSwitch** con una proprietà **DisplayName** di `TraceLevelSwitch`.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-155">The following examples demonstrate a **BooleanSwitch** with a **DisplayName** property of `DataMessageSwitch` and a **TraceSwitch** with a **DisplayName** property of `TraceLevelSwitch`.</span></span>  
  
    ```xml  
    <system.diagnostics>  
       <switches>  
          <add name="DataMessagesSwitch" value="0" />  
          <add name="TraceLevelSwitch" value="0" />  
       </switches>  
    </system.diagnostics>  
    ```  
  
     <span data-ttu-id="d6d1e-156">In questa configurazione entrambe le opzioni sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-156">In this configuration, both switches are off.</span></span>  
  
4. <span data-ttu-id="d6d1e-157">Se è necessario attivare un **BooleanSwitch**, come `DataMessagesSwitch` illustrato nell'esempio precedente, impostare **Value** su qualsiasi intero diverso da 0.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-157">If you need to turn on a **BooleanSwitch**, such as `DataMessagesSwitch` shown in the previous example, change the **Value** to any integer other than 0.</span></span>  
  
5. <span data-ttu-id="d6d1e-158">Se è necessario attivare un **TraceSwitch**, come `TraceLevelSwitch` illustrato nell'esempio precedente, impostare **Value** sul livello appropriato (da 1 a 4).</span><span class="sxs-lookup"><span data-stu-id="d6d1e-158">If you need to turn on a **TraceSwitch**, such as `TraceLevelSwitch` shown in the previous example, change the **Value** to the appropriate level setting (1 to 4).</span></span>  
  
6. <span data-ttu-id="d6d1e-159">Aggiungere commenti al file CONFIG in modo che l'utente possa comprendere chiaramente quali valori modificare per configurare correttamente le opzioni.</span><span class="sxs-lookup"><span data-stu-id="d6d1e-159">Add comments to the .config file so the end user has a clear understanding of what values to change to configure the switches appropriately.</span></span>  
  
     <span data-ttu-id="d6d1e-160">L'esempio seguente mostra come può apparire il codice finale, comprensivo di commenti:</span><span class="sxs-lookup"><span data-stu-id="d6d1e-160">The following example shows how the final code, including comments, might look:</span></span>  
  
    ```xml  
    <system.diagnostics>  
       <switches>  
          <!-- This switch controls data messages. In order to receive data   
             trace messages, change value="0" to value="1" -->  
          <add name="DataMessagesSwitch" value="0" />  
          <!-- This switch controls general messages. In order to   
             receive general trace messages change the value to the   
             appropriate level. "1" gives error messages, "2" gives errors   
             and warnings, "3" gives more detailed error information, and   
             "4" gives verbose trace information -->  
          <add name="TraceLevelSwitch" value="0" />  
       </switches>  
    </system.diagnostics>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d6d1e-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6d1e-161">See also</span></span>

- [<span data-ttu-id="d6d1e-162">Traccia e strumentazione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="d6d1e-162">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="d6d1e-163">Procedura: aggiungere istruzioni di traccia al codice dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d6d1e-163">How to: Add Trace Statements to Application Code</span></span>](how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="d6d1e-164">Opzioni di traccia</span><span class="sxs-lookup"><span data-stu-id="d6d1e-164">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="d6d1e-165">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="d6d1e-165">Trace and Debug Settings Schema</span></span>](../configure-apps/file-schema/trace-debug/index.md)

---
title: Modifica della posizione di inserimento delle informazioni con My.Application.Log
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, walkthroughs
- event logs, changing output location
ms.assetid: ecc74f95-743c-450d-93f6-09a30db0fe4a
ms.openlocfilehash: bdee0a91360580b156c1734ef4c82139b18ce2b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74336728"
---
# <a name="walkthrough-changing-where-myapplicationlog-writes-information-visual-basic"></a><span data-ttu-id="400d7-102">Procedura dettagliata: modifica della posizione di inserimento delle informazioni con My.Application.Log (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="400d7-102">Walkthrough: Changing Where My.Application.Log Writes Information (Visual Basic)</span></span>

<span data-ttu-id="400d7-103">È possibile usare gli oggetti `My.Application.Log` e `My.Log` per registrare informazioni sugli eventi che si verificano nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="400d7-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="400d7-104">Questa procedura dettagliata mostra come eseguire l'override delle impostazioni predefinite e fare in modo che l'oggetto `Log` scriva le informazioni in altri listener di log.</span><span class="sxs-lookup"><span data-stu-id="400d7-104">This walkthrough shows how to override the default settings and cause the `Log` object to write to other log listeners.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="400d7-105">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="400d7-105">Prerequisites</span></span>

<span data-ttu-id="400d7-106">L'oggetto `Log` può scrivere le informazioni in diversi listener di log.</span><span class="sxs-lookup"><span data-stu-id="400d7-106">The `Log` object can write information to several log listeners.</span></span> <span data-ttu-id="400d7-107">Prima di modificare le configurazioni dei listener di log è necessario determinarne la configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="400d7-107">You need to determine the current configuration of the log listeners before changing the configurations.</span></span> <span data-ttu-id="400d7-108">Per altre informazioni, vedere [Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="400d7-108">For more information, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>

<span data-ttu-id="400d7-109">Si consiglia di consultare la [Procedura: Scrivere informazioni sugli eventi in un file di testo](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) o [Procedura: Scrivere nel registro eventi di un'applicazione](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md).</span><span class="sxs-lookup"><span data-stu-id="400d7-109">You may want to review [How to: Write Event Information to a Text File](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) or [How to: Write to an Application Event Log](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md).</span></span>

### <a name="to-add-listeners"></a><span data-ttu-id="400d7-110">Per aggiungere listener</span><span class="sxs-lookup"><span data-stu-id="400d7-110">To add listeners</span></span>

1. <span data-ttu-id="400d7-111">Fare clic con il pulsante destro del mouse sul file app.config in **Esplora soluzioni** , quindi scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="400d7-111">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>

     <span data-ttu-id="400d7-112">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="400d7-112">\- or -</span></span>

     <span data-ttu-id="400d7-113">Se non è presente alcun file app.config:</span><span class="sxs-lookup"><span data-stu-id="400d7-113">If there is no app.config file:</span></span>

    1. <span data-ttu-id="400d7-114">Scegliere **Aggiungi nuovo elemento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="400d7-114">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="400d7-115">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **File di configurazione dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="400d7-115">From the **Add New Item** dialog box, select **Application Configuration File**.</span></span>

    3. <span data-ttu-id="400d7-116">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="400d7-116">Click **Add**.</span></span>

2. <span data-ttu-id="400d7-117">Individuare la sezione `<listeners>` all'interno della sezione `<source>` con l'attributo `name` "DefaultSource" che si trova nella sezione `<sources>` .</span><span class="sxs-lookup"><span data-stu-id="400d7-117">Locate the `<listeners>` section, under the `<source>` section with the `name` attribute "DefaultSource", in the `<sources>` section.</span></span> <span data-ttu-id="400d7-118">La sezione `<sources>` si trova nella sezione `<system.diagnostics>` all'interno della sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="400d7-118">The `<sources>` section is in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="400d7-119">Aggiungere gli elementi seguenti alla sezione `<listeners>` .</span><span class="sxs-lookup"><span data-stu-id="400d7-119">Add these elements to that `<listeners>` section.</span></span>

    ```xml
    <!-- Uncomment to connect the application file log. -->
    <!-- <add name="FileLog" /> -->
    <!-- Uncomment to connect the event log. -->
    <!-- <add name="EventLog" /> -->
    <!-- Uncomment to connect the event log. -->
    <!-- <add name="Delimited" /> -->
    <!-- Uncomment to connect the XML log. -->
    <!-- <add name="XmlWriter" /> -->
    <!-- Uncomment to connect the console log. -->
    <!-- <add name="Console" /> -->
    ```

4. <span data-ttu-id="400d7-120">Rimuovere il commento dai listener di log per i quali si vuole ricevere i messaggi di `Log` .</span><span class="sxs-lookup"><span data-stu-id="400d7-120">Uncomment the log listeners that you want to receive `Log` messages.</span></span>

5. <span data-ttu-id="400d7-121">Individuare la sezione `<sharedListeners>` nella sezione `<system.diagnostics>` all'interno della sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="400d7-121">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

6. <span data-ttu-id="400d7-122">Aggiungere gli elementi seguenti alla sezione `<sharedListeners>` .</span><span class="sxs-lookup"><span data-stu-id="400d7-122">Add these elements to that `<sharedListeners>` section.</span></span>

    ```xml
    <add name="FileLog"
         type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
               Microsoft.VisualBasic, Version=8.0.0.0,
               Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
         initializeData="FileLogWriter" />
    <add name="EventLog"
         type="System.Diagnostics.EventLogTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="sample application"/>
    <add name="Delimited"
         type="System.Diagnostics.DelimitedListTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="c:\temp\sampleDelimitedFile.txt"
         traceOutputOptions="DateTime" />
    <add name="XmlWriter"
         type="System.Diagnostics.XmlWriterTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="c:\temp\sampleLogFile.xml" />
    <add name="Console"
         type="System.Diagnostics.ConsoleTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="true" />
    ```

7. <span data-ttu-id="400d7-123">Il contenuto del file app.config dovrebbe essere simile al codice XML seguente.</span><span class="sxs-lookup"><span data-stu-id="400d7-123">The content of the app.config file should be similar to the following XML:</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.diagnostics>
        <sources>
          <!-- This section configures My.Application.Log -->
          <source name="DefaultSource" switchName="DefaultSwitch">
            <listeners>
              <add name="FileLog"/>
              <!-- Uncomment to connect the application file log. -->
              <!-- <add name="FileLog" /> -->
              <!-- Uncomment to connect the event log. -->
              <!-- <add name="EventLog" /> -->
              <!-- Uncomment to connect the event log. -->
              <!-- <add name="Delimited" /> -->
              <!-- Uncomment to connect the XML log. -->
              <!-- <add name="XmlWriter" /> -->
              <!-- Uncomment to connect the console log. -->
              <!-- <add name="Console" /> -->
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
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
               initializeData="FileLogWriter" />
          <add name="EventLog"
               type="System.Diagnostics.EventLogTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="sample application"/>
          <add name="Delimited"
               type="System.Diagnostics.DelimitedListTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="c:\temp\sampleDelimitedFile.txt"
               traceOutputOptions="DateTime" />
          <add name="XmlWriter"
               type="System.Diagnostics.XmlWriterTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="c:\temp\sampleLogFile.xml" />
          <add name="Console"
               type="System.Diagnostics.ConsoleTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="true" />
        </sharedListeners>
      </system.diagnostics>
    </configuration>
    ```

### <a name="to-reconfigure-a-listener"></a><span data-ttu-id="400d7-124">Per riconfigurare un listener</span><span class="sxs-lookup"><span data-stu-id="400d7-124">To reconfigure a listener</span></span>

1. <span data-ttu-id="400d7-125">Individuare l'elemento `<add>` del listener nella sezione `<sharedListeners>` .</span><span class="sxs-lookup"><span data-stu-id="400d7-125">Locate the listener's `<add>` element from the `<sharedListeners>` section.</span></span>

2. <span data-ttu-id="400d7-126">L'attributo `type` fornisce il nome del tipo di listener.</span><span class="sxs-lookup"><span data-stu-id="400d7-126">The `type` attribute gives the name of the listener type.</span></span> <span data-ttu-id="400d7-127">Questo tipo deve ereditare dalla classe <xref:System.Diagnostics.TraceListener> .</span><span class="sxs-lookup"><span data-stu-id="400d7-127">This type must inherit from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="400d7-128">Usare il tipo con nome sicuro per assicurarsi di usare il tipo corretto.</span><span class="sxs-lookup"><span data-stu-id="400d7-128">Use the strongly named type name to ensure that the right type is used.</span></span> <span data-ttu-id="400d7-129">Per altre informazioni, vedere la sezione seguente "Per aggiungere riferimenti a un tipo con nome sicuro".</span><span class="sxs-lookup"><span data-stu-id="400d7-129">For more information, see the "To reference a strongly named type" section below.</span></span>

     <span data-ttu-id="400d7-130">Di seguito sono riportati alcuni esempi di listener che si possono usare.</span><span class="sxs-lookup"><span data-stu-id="400d7-130">Some types that you can use are:</span></span>

    - <span data-ttu-id="400d7-131">Il listener <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> , che scrive le informazioni in un log file.</span><span class="sxs-lookup"><span data-stu-id="400d7-131">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> listener, which writes to a file log.</span></span>

    - <span data-ttu-id="400d7-132">Il listener <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> , che scrive le informazioni nel log eventi del computer specificato dal parametro `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="400d7-132">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> listener, which writes information to the computer event log specified by the `initializeData` parameter.</span></span>

    - <span data-ttu-id="400d7-133">I listener <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> e <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> , che scrivono le informazioni nel file specificato nel parametro `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="400d7-133">The <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> and <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> listeners, which write to the file specified in the `initializeData` parameter.</span></span>

    - <span data-ttu-id="400d7-134">Il listener <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> , che scrive le informazioni nella console della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="400d7-134">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> listener, which writes to the command-line console.</span></span>

     <span data-ttu-id="400d7-135">Per sapere dove gli altri tipi di listener di log scrivono le informazioni, consultare la documentazione relativa al tipo di listener desiderato.</span><span class="sxs-lookup"><span data-stu-id="400d7-135">For information about where other types of log listeners write information, consult that type's documentation.</span></span>

3. <span data-ttu-id="400d7-136">Quando crea l'oggetto listener di log, l'applicazione passa l'attributo `initializeData` come parametro del costruttore.</span><span class="sxs-lookup"><span data-stu-id="400d7-136">When the application creates the log-listener object, it passes the `initializeData` attribute as the constructor parameter.</span></span> <span data-ttu-id="400d7-137">Il significato dell'attributo `initializeData` dipende dal listener di traccia.</span><span class="sxs-lookup"><span data-stu-id="400d7-137">The meaning of the `initializeData` attribute depends on the trace listener.</span></span>

4. <span data-ttu-id="400d7-138">Dopo aver creato il listener di log, l'applicazione imposta le proprietà del listener.</span><span class="sxs-lookup"><span data-stu-id="400d7-138">After creating the log listener, the application sets the listener's properties.</span></span> <span data-ttu-id="400d7-139">Tali proprietà sono definite dagli altri attributi contenuti nell'elemento `<add>` .</span><span class="sxs-lookup"><span data-stu-id="400d7-139">These properties are defined by the other attributes in the `<add>` element.</span></span> <span data-ttu-id="400d7-140">Per altre informazioni sulle proprietà di un determinato listener, consultare la documentazione relativa al tipo di listener corrispondente.</span><span class="sxs-lookup"><span data-stu-id="400d7-140">For more information on the properties for a particular listener, see the documentation for that listener's type.</span></span>

### <a name="to-reference-a-strongly-named-type"></a><span data-ttu-id="400d7-141">Per aggiungere riferimenti a un tipo con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="400d7-141">To reference a strongly named type</span></span>

1. <span data-ttu-id="400d7-142">Per assicurarsi di usare il tipo di listener di log appropriato, usare il nome di tipo completo e il nome di assembly sicuro.</span><span class="sxs-lookup"><span data-stu-id="400d7-142">To ensure that the right type is used for your log listener, make sure to use the fully qualified type name and the strongly named assembly name.</span></span> <span data-ttu-id="400d7-143">La sintassi di un tipo con nome sicuro è la seguente:</span><span class="sxs-lookup"><span data-stu-id="400d7-143">The syntax of a strongly named type is as follows:</span></span>

     <span data-ttu-id="400d7-144">\<*nome tipo*>, \<*nome assembly*>, \<*numero versione*>, \<*impostazioni cultura*>, \<*nome sicuro*></span><span class="sxs-lookup"><span data-stu-id="400d7-144">\<*type name*>, \<*assembly name*>, \<*version number*>, \<*culture*>, \<*strong name*></span></span>

2. <span data-ttu-id="400d7-145">L'esempio di codice seguente mostra come determinare il tipo con nome sicuro per un tipo completo, in questo caso "System.Diagnostics.FileLogTraceListener".</span><span class="sxs-lookup"><span data-stu-id="400d7-145">This code example shows how to determine the strongly named type name for a fully qualified type—"System.Diagnostics.FileLogTraceListener" in this case.</span></span>

     [!code-vb[VbVbalrMyApplicationLog#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#15)]

     <span data-ttu-id="400d7-146">Questo è l'output, e può essere usato per aggiungere riferimenti univoci a un tipo con nome sicuro, come nella procedura "Per aggiungere listener" precedente.</span><span class="sxs-lookup"><span data-stu-id="400d7-146">This is the output, and it can be used to uniquely reference a strongly named type, as in the "To add listeners" procedure above.</span></span>

     `Microsoft.VisualBasic.Logging.FileLogTraceListener, Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`

## <a name="see-also"></a><span data-ttu-id="400d7-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="400d7-147">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType>
- <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>
- [<span data-ttu-id="400d7-148">Procedura: Scrivere informazioni sugli eventi in un file di testo</span><span class="sxs-lookup"><span data-stu-id="400d7-148">How to: Write Event Information to a Text File</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)
- [<span data-ttu-id="400d7-149">Procedura: scrivere nel log eventi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="400d7-149">How to: Write to an Application Event Log</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)

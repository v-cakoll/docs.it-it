---
title: Creazione di listener di log personalizzati
ms.date: 07/20/2015
helpviewer_keywords:
- custom log listeners
- My.Application.Log object, custom log listeners
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
ms.openlocfilehash: 7b611e93119dc66a9404cf271ea201676d7b5318
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74353620"
---
# <a name="walkthrough-creating-custom-log-listeners-visual-basic"></a><span data-ttu-id="89f4a-102">Procedura dettagliata: creazione di listener di log personalizzati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89f4a-102">Walkthrough: Creating Custom Log Listeners (Visual Basic)</span></span>

<span data-ttu-id="89f4a-103">Questa procedura spiega come creare un listener di log personalizzato e configurarlo in modo che resti in ascolto dell'output dell'oggetto `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="89f4a-103">This walkthrough demonstrates how to create a custom log listener and configure it to listen to the output of the `My.Application.Log` object.</span></span>

## <a name="getting-started"></a><span data-ttu-id="89f4a-104">Introduzione</span><span class="sxs-lookup"><span data-stu-id="89f4a-104">Getting Started</span></span>

<span data-ttu-id="89f4a-105">I listener di log devono ereditare dalla <xref:System.Diagnostics.TraceListener> classe.</span><span class="sxs-lookup"><span data-stu-id="89f4a-105">Log listeners must inherit from the <xref:System.Diagnostics.TraceListener> class.</span></span>

#### <a name="to-create-the-listener"></a><span data-ttu-id="89f4a-106">Per creare il listener</span><span class="sxs-lookup"><span data-stu-id="89f4a-106">To create the listener</span></span>

- <span data-ttu-id="89f4a-107">Nell'applicazione creare una classe denominata `SimpleListener` che eredita da <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="89f4a-107">In your application, create a class named `SimpleListener` that inherits from <xref:System.Diagnostics.TraceListener>.</span></span>

     [!code-vb[VbVbalrMyApplicationLog#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#16)]

     <span data-ttu-id="89f4a-108">I metodi <xref:System.Diagnostics.TraceListener.Write%2A> e <xref:System.Diagnostics.TraceListener.WriteLine%2A>, richiesti dalla classe di base, chiamano `MsgBox` per visualizzare l'input.</span><span class="sxs-lookup"><span data-stu-id="89f4a-108">The <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods, required by the base class, call `MsgBox` to display their input.</span></span>

     <span data-ttu-id="89f4a-109">L'attributo <xref:System.Security.Permissions.HostProtectionAttribute> viene applicato ai metodi <xref:System.Diagnostics.TraceListener.Write%2A> e <xref:System.Diagnostics.TraceListener.WriteLine%2A> in modo che i relativi attributi corrispondano ai metodi della classe di base.</span><span class="sxs-lookup"><span data-stu-id="89f4a-109">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is applied to the <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods so that their attributes match the base class methods.</span></span> <span data-ttu-id="89f4a-110">L'attributo <xref:System.Security.Permissions.HostProtectionAttribute> consente all'host che esegue il codice di determinare se il codice espone la sincronizzazione con protezione host.</span><span class="sxs-lookup"><span data-stu-id="89f4a-110">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute allows the host that runs the code to determine that the code exposes host-protection synchronization.</span></span>

    > [!NOTE]
    > <span data-ttu-id="89f4a-111">L'attributo <xref:System.Security.Permissions.HostProtectionAttribute> ha effetto solo su applicazioni non gestite che ospitano Common Language Runtime e implementano la protezione host, ad esempio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="89f4a-111">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is effective only on unmanaged applications that host the common language runtime and that implement host protection, such as SQL Server.</span></span>

<span data-ttu-id="89f4a-112">Per assicurarsi che `My.Application.Log` usi il listener di log, assegnare un nome sicuro all'assembly che contiene il listener di log.</span><span class="sxs-lookup"><span data-stu-id="89f4a-112">To ensure that `My.Application.Log` uses your log listener, you should strongly name the assembly that contains your log listener.</span></span>

<span data-ttu-id="89f4a-113">La procedura seguente prevede alcuni semplici passaggi per la creazione di un assembly di listener di log con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="89f4a-113">The next procedure provides some simple steps for creating a strongly named log-listener assembly.</span></span> <span data-ttu-id="89f4a-114">Per altre informazioni, vedere [Creazione e utilizzo degli assembly con nome sicuro](../../../../standard/assembly/create-use-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="89f4a-114">For more information, see [Creating and Using Strong-Named Assemblies](../../../../standard/assembly/create-use-strong-named.md).</span></span>

#### <a name="to-strongly-name-the-log-listener-assembly"></a><span data-ttu-id="89f4a-115">Per assegnare un nome sicuro all'assembly di listener di log</span><span class="sxs-lookup"><span data-stu-id="89f4a-115">To strongly name the log-listener assembly</span></span>

1. <span data-ttu-id="89f4a-116">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="89f4a-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="89f4a-117">Scegliere **Proprietà**dal menu **Progetto** .</span><span class="sxs-lookup"><span data-stu-id="89f4a-117">On the **Project** menu, choose **Properties**.</span></span>

2. <span data-ttu-id="89f4a-118">Fare clic sulla scheda **Firma** .</span><span class="sxs-lookup"><span data-stu-id="89f4a-118">Click the **Signing** tab.</span></span>

3. <span data-ttu-id="89f4a-119">Selezionare la casella **Firma assembly** .</span><span class="sxs-lookup"><span data-stu-id="89f4a-119">Select the **Sign the assembly** box.</span></span>

4. <span data-ttu-id="89f4a-120">Selezionare \*\* \<Nuovo>\*\* dall'elenco a discesa Scegli un file di chiave con **nome sicuro.**</span><span class="sxs-lookup"><span data-stu-id="89f4a-120">Select **\<New>** from the **Choose a strong name key file** drop-down list.</span></span>

     <span data-ttu-id="89f4a-121">Si aprirà la finestra di dialogo **Crea chiave con nome sicuro** .</span><span class="sxs-lookup"><span data-stu-id="89f4a-121">The **Create Strong Name Key** dialog box opens.</span></span>

5. <span data-ttu-id="89f4a-122">Specificare un nome per il file di chiave nella casella **Nome file di chiave**.</span><span class="sxs-lookup"><span data-stu-id="89f4a-122">Provide a name for the key file in the **Key file name** box.</span></span>

6. <span data-ttu-id="89f4a-123">Digitare una password nelle caselle **Immettere la password** e **Conferma password**.</span><span class="sxs-lookup"><span data-stu-id="89f4a-123">Enter a password in the **Enter password** and **Confirm password** boxes.</span></span>

7. <span data-ttu-id="89f4a-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="89f4a-124">Click **OK**.</span></span>

8. <span data-ttu-id="89f4a-125">Ricompilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="89f4a-125">Rebuild the application.</span></span>

## <a name="adding-the-listener"></a><span data-ttu-id="89f4a-126">Aggiungere il listener</span><span class="sxs-lookup"><span data-stu-id="89f4a-126">Adding the Listener</span></span>

<span data-ttu-id="89f4a-127">Ora che l'assembly ha un nome sicuro è necessario determinare il nome sicuro del listener in modo che `My.Application.Log` usi il listener di log.</span><span class="sxs-lookup"><span data-stu-id="89f4a-127">Now that the assembly has a strong name, you need to determine the strong name of the listener so that `My.Application.Log` uses your log listener.</span></span>

<span data-ttu-id="89f4a-128">Il formato di un tipo con nome sicuro è il seguente.</span><span class="sxs-lookup"><span data-stu-id="89f4a-128">The format of a strongly named type is as follows.</span></span>

<span data-ttu-id="89f4a-129">\<nome tipo>, \<nome assembly>, \<numero versione>, \<impostazioni cultura>, \<nome sicuro></span><span class="sxs-lookup"><span data-stu-id="89f4a-129">\<type name>, \<assembly name>, \<version number>, \<culture>, \<strong name></span></span>

#### <a name="to-determine-the-strong-name-of-the-listener"></a><span data-ttu-id="89f4a-130">Per determinare il nome sicuro del listener</span><span class="sxs-lookup"><span data-stu-id="89f4a-130">To determine the strong name of the listener</span></span>

- <span data-ttu-id="89f4a-131">Il codice seguente illustra come determinare il nome sicuro del tipo per `SimpleListener`.</span><span class="sxs-lookup"><span data-stu-id="89f4a-131">The following code shows how to determine the strongly named type name for `SimpleListener`.</span></span>

     [!code-vb[VbVbalrMyApplicationLog#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#17)]

     <span data-ttu-id="89f4a-132">Il nome sicuro del tipo dipende dal progetto.</span><span class="sxs-lookup"><span data-stu-id="89f4a-132">The strong name of the type depends on your project.</span></span>

<span data-ttu-id="89f4a-133">Con il nome sicuro è possibile aggiungere il listener alla raccolta di listener di log `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="89f4a-133">With the strong name, you can add the listener to the `My.Application.Log` log-listener collection.</span></span>

#### <a name="to-add-the-listener-to-myapplicationlog"></a><span data-ttu-id="89f4a-134">Per aggiungere il listener a My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="89f4a-134">To add the listener to My.Application.Log</span></span>

1. <span data-ttu-id="89f4a-135">Fare clic con il pulsante destro del mouse su app.config in **Esplora soluzioni** e scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="89f4a-135">Right-click on app.config in the **Solution Explorer** and choose **Open**.</span></span>

     <span data-ttu-id="89f4a-136">-oppure-</span><span class="sxs-lookup"><span data-stu-id="89f4a-136">-or-</span></span>

     <span data-ttu-id="89f4a-137">Se non è presente un file app.config:</span><span class="sxs-lookup"><span data-stu-id="89f4a-137">If there is an app.config file:</span></span>

    1. <span data-ttu-id="89f4a-138">Scegliere **Aggiungi nuovo elemento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="89f4a-138">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="89f4a-139">Nella finestra di dialogo **Aggiungi nuovo elemento** scegliere **File di configurazione dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="89f4a-139">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="89f4a-140">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="89f4a-140">Click **Add**.</span></span>

2. <span data-ttu-id="89f4a-141">Individuare la sezione `<listeners>` all'interno della sezione `<source>` con l'attributo `name` "DefaultSource" che si trova nella sezione `<sources>` .</span><span class="sxs-lookup"><span data-stu-id="89f4a-141">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="89f4a-142">La sezione `<sources>` si trova nella sezione `<system.diagnostics>` all'interno della sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="89f4a-142">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="89f4a-143">Aggiungere l'elemento seguente alla sezione `<listeners>`:</span><span class="sxs-lookup"><span data-stu-id="89f4a-143">Add this element to the `<listeners>` section:</span></span>

    ```xml
    <add name="SimpleLog" />
    ```

4. <span data-ttu-id="89f4a-144">Individuare la sezione `<sharedListeners>` nella sezione `<system.diagnostics>` all'interno della sezione di primo livello `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="89f4a-144">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

5. <span data-ttu-id="89f4a-145">Aggiungere l'elemento seguente alla sezione `<sharedListeners>` :</span><span class="sxs-lookup"><span data-stu-id="89f4a-145">Add this element to that `<sharedListeners>` section:</span></span>

    ```xml
    <add name="SimpleLog" type="SimpleLogStrongName" />
    ```

     <span data-ttu-id="89f4a-146">Modificare il valore di `SimpleLogStrongName` in modo che sia il nome sicuro del listener.</span><span class="sxs-lookup"><span data-stu-id="89f4a-146">Change the value of `SimpleLogStrongName` to be the strong name of the listener.</span></span>

## <a name="see-also"></a><span data-ttu-id="89f4a-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89f4a-147">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="89f4a-148">Utilizzo dei log applicazione</span><span class="sxs-lookup"><span data-stu-id="89f4a-148">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="89f4a-149">Procedura: registrare eccezioni</span><span class="sxs-lookup"><span data-stu-id="89f4a-149">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [<span data-ttu-id="89f4a-150">Procedura: Scrivere messaggi di log</span><span class="sxs-lookup"><span data-stu-id="89f4a-150">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)
- [<span data-ttu-id="89f4a-151">Procedura dettagliata: modifica della posizione di inserimento delle informazioni con My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="89f4a-151">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)

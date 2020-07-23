---
title: 'Procedura: Eseguire il debug di applicazioni di servizio di Windows'
description: Informazioni su come eseguire il debug di applicazioni di servizio Windows, che non sono semplici da eseguire il debug come altri tipi di applicazioni di Visual Studio.
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- Windows NT services, debugging
- Windows Service applications, debugging
- services, debugging
ms.assetid: 63ab0800-0f05-4f1e-88e6-94c73fd920a2
author: ghogen
ms.openlocfilehash: fb58f2ff4f480347f0f233ecd9a619cf287cfdfd
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925761"
---
# <a name="how-to-debug-windows-service-applications"></a><span data-ttu-id="ddb12-103">Procedura: Eseguire il debug di applicazioni di servizio di Windows</span><span class="sxs-lookup"><span data-stu-id="ddb12-103">How to: Debug Windows Service Applications</span></span>
<span data-ttu-id="ddb12-104">Poiché un servizio deve essere eseguito dall'interno del contesto di Gestione controllo servizi e non dall'interno di Visual Studio,</span><span class="sxs-lookup"><span data-stu-id="ddb12-104">A service must be run from within the context of the Services Control Manager rather than from within Visual Studio.</span></span> <span data-ttu-id="ddb12-105">il debug di un servizio non è semplice come quello di altri tipi di applicazioni di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ddb12-105">For this reason, debugging a service is not as straightforward as debugging other Visual Studio application types.</span></span> <span data-ttu-id="ddb12-106">Per eseguire il debug di un servizio, è necessario avviare il servizio e connettere un debugger al processo in cui viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="ddb12-106">To debug a service, you must start the service and then attach a debugger to the process in which it is running.</span></span> <span data-ttu-id="ddb12-107">È quindi possibile eseguire il debug dell'applicazione tramite tutte le funzionalità di debug standard di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ddb12-107">You can then debug your application by using all of the standard debugging functionality of Visual Studio.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="ddb12-108">Non connettersi a un processo a meno che non si conoscano il tipo di processo e le conseguenze di tale operazione, che potrebbe anche terminare il processo.</span><span class="sxs-lookup"><span data-stu-id="ddb12-108">You should not attach to a process unless you know what the process is and understand the consequences of attaching to and possibly killing that process.</span></span> <span data-ttu-id="ddb12-109">Se ad esempio ci si connette al processo WinLogon e si interrompe il debug, il sistema si arresta in quanto non può funzionare senza WinLogon.</span><span class="sxs-lookup"><span data-stu-id="ddb12-109">For example, if you attach to the WinLogon process and then stop debugging, the system will halt because it can’t operate without WinLogon.</span></span>  
  
 <span data-ttu-id="ddb12-110">È possibile connettere il debugger solo a un servizio in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ddb12-110">You can attach the debugger only to a running service.</span></span> <span data-ttu-id="ddb12-111">Il processo di connessione interrompe il funzionamento corrente del servizio, in realtà non arresta né sospende l'elaborazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="ddb12-111">The attachment process interrupts the current functioning of your service; it doesn’t actually stop or pause the service's processing.</span></span> <span data-ttu-id="ddb12-112">Ciò significa che se il servizio è in esecuzione quando inizia il debug, tecnicamente si trova ancora nello stato Avviato all'avvio del debug, ma l'elaborazione è sospesa.</span><span class="sxs-lookup"><span data-stu-id="ddb12-112">That is, if your service is running when you begin debugging, it is still technically in the Started state as you debug it, but its processing has been suspended.</span></span>  
  
 <span data-ttu-id="ddb12-113">Dopo aver effettuato la connessione al processo, sarà possibile impostare i punti di interruzione e usarli per eseguire il debug del codice.</span><span class="sxs-lookup"><span data-stu-id="ddb12-113">After attaching to the process, you can set breakpoints and use these to debug your code.</span></span> <span data-ttu-id="ddb12-114">Quando si chiude la finestra di dialogo usata per effettuare la connessione al processo, si entra in modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="ddb12-114">Once you exit the dialog box you use to attach to the process, you are effectively in debug mode.</span></span> <span data-ttu-id="ddb12-115">È possibile usare Gestione controllo servizi per avviare, arrestare, sospendere e riprendere il servizio raggiungendo così i punti di interruzione impostati.</span><span class="sxs-lookup"><span data-stu-id="ddb12-115">You can use the Services Control Manager to start, stop, pause and continue your service, thus hitting the breakpoints you've set.</span></span> <span data-ttu-id="ddb12-116">Al termine del debug, è possibile rimuovere il servizio fittizio.</span><span class="sxs-lookup"><span data-stu-id="ddb12-116">You can later remove this dummy service after debugging is successful.</span></span>  
  
 <span data-ttu-id="ddb12-117">Questo articolo descrive il debug di un servizio in esecuzione nel computer locale, ma è possibile anche eseguire il debug di servizi Windows in esecuzione in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="ddb12-117">This article covers debugging a service that's running on the local computer, but you can also debug Windows Services that are running on a remote computer.</span></span> <span data-ttu-id="ddb12-118">Vedere [Remote Debugging](/visualstudio/debugger/debug-installed-app-package).</span><span class="sxs-lookup"><span data-stu-id="ddb12-118">See [Remote Debugging](/visualstudio/debugger/debug-installed-app-package).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ddb12-119">Il debug del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> può risultare difficile in quanto Gestione controllo servizi impone un limite di 30 secondi per tutti i tentativi di avvio di un servizio.</span><span class="sxs-lookup"><span data-stu-id="ddb12-119">Debugging the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method can be difficult because the Services Control Manager imposes a 30-second limit on all attempts to start a service.</span></span> <span data-ttu-id="ddb12-120">Per altre informazioni, vedere [Risoluzione dei problemi: Debug dei servizi Windows](troubleshooting-debugging-windows-services.md).</span><span class="sxs-lookup"><span data-stu-id="ddb12-120">For more information, see [Troubleshooting: Debugging Windows Services](troubleshooting-debugging-windows-services.md).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="ddb12-121">Per ottenere informazioni significative per il debug, il debugger di Visual Studio deve trovare il file di simboli per i file binari sottoposti a debug.</span><span class="sxs-lookup"><span data-stu-id="ddb12-121">To get meaningful information for debugging, the Visual Studio debugger needs to find symbol files for the binaries that are being debugged.</span></span> <span data-ttu-id="ddb12-122">Se si esegue il debug di un servizio compilato in Visual Studio, i file di simboli (con estensione PDB) si trovano nella stessa cartella dell'eseguibile o della libreria e il debugger li carica automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ddb12-122">If you are debugging a service that you built in Visual Studio, the symbol files (.pdb files) are in the same folder as the executable or library, and the debugger loads them automatically.</span></span> <span data-ttu-id="ddb12-123">Se si esegue il debug di un servizio che non è stato compilato, è necessario prima trovare i simboli per il servizio e assicurarsi che possano essere individuati dal debugger.</span><span class="sxs-lookup"><span data-stu-id="ddb12-123">If you are debugging a service that you didn't build, you should first find symbols for the service and make sure they can be found by the debugger.</span></span> <span data-ttu-id="ddb12-124">Vedere [Specificare file di simboli (con estensione pdb) e di origine nel debugger di Visual Studio](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger).</span><span class="sxs-lookup"><span data-stu-id="ddb12-124">See [Specify Symbol (.pdb) and Source Files in the Visual Studio Debugger](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger).</span></span> <span data-ttu-id="ddb12-125">Se si esegue il debug di un processo di sistema o è necessario avere i simboli per le chiamate di sistema nei servizi, aggiungere i server dei simboli Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ddb12-125">If you're debugging a system process or want to have symbols for system calls in your services, you should add the Microsoft Symbol Servers.</span></span> <span data-ttu-id="ddb12-126">Vedere [Simboli di debug](/windows/desktop/DxTechArts/debugging-with-symbols).</span><span class="sxs-lookup"><span data-stu-id="ddb12-126">See [Debugging Symbols](/windows/desktop/DxTechArts/debugging-with-symbols).</span></span>  
  
### <a name="to-debug-a-service"></a><span data-ttu-id="ddb12-127">Per eseguire il debug di un servizio</span><span class="sxs-lookup"><span data-stu-id="ddb12-127">To debug a service</span></span>  
  
1. <span data-ttu-id="ddb12-128">Compilare il servizio nella configurazione di debug.</span><span class="sxs-lookup"><span data-stu-id="ddb12-128">Build your service in the Debug configuration.</span></span>  
  
2. <span data-ttu-id="ddb12-129">Installare il servizio.</span><span class="sxs-lookup"><span data-stu-id="ddb12-129">Install your service.</span></span> <span data-ttu-id="ddb12-130">Per altre informazioni, vedere [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="ddb12-130">For more information, see [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span></span>  
  
3. <span data-ttu-id="ddb12-131">Avviare il servizio da **Gestione controllo servizi**, da **Esplora server** o dal codice.</span><span class="sxs-lookup"><span data-stu-id="ddb12-131">Start your service, either from **Services Control Manager**, **Server Explorer**, or from code.</span></span> <span data-ttu-id="ddb12-132">Per altre informazioni, vedere [Procedura: Avviare servizi](how-to-start-services.md).</span><span class="sxs-lookup"><span data-stu-id="ddb12-132">For more information, see [How to: Start Services](how-to-start-services.md).</span></span>  
  
4. <span data-ttu-id="ddb12-133">Avviare Visual Studio con credenziali amministrative, in modo che sia possibile connettersi a processi di sistema.</span><span class="sxs-lookup"><span data-stu-id="ddb12-133">Start Visual Studio with administrative credentials so you can attach to system processes.</span></span>  
  
5. <span data-ttu-id="ddb12-134">(Facoltativo) Nella barra dei menu di Visual Studio scegliere **Strumenti**, **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="ddb12-134">(Optional) On the Visual Studio menu bar, choose **Tools**, **Options**.</span></span> <span data-ttu-id="ddb12-135">Nella finestra di dialogo **Opzioni** scegliere **Debug**, **Simboli**, selezionare la casella di controllo **Server dei simboli Microsoft** e quindi scegliere il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddb12-135">In the **Options** dialog box, choose **Debugging**, **Symbols**, select the **Microsoft Symbol Servers** check box, and then choose the **OK** button.</span></span>  
  
6. <span data-ttu-id="ddb12-136">Nella barra dei menu scegliere **Connetti a processo** dal menu **Debug** o **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="ddb12-136">On the menu bar, choose **Attach to Process** from the **Debug** or **Tools** menu.</span></span> <span data-ttu-id="ddb12-137">(scelta rapida da tastiera: CTRL+ALT+P).</span><span class="sxs-lookup"><span data-stu-id="ddb12-137">(Keyboard: Ctrl+Alt+P)</span></span>  
  
     <span data-ttu-id="ddb12-138">Verrà visualizzata la finestra di dialogo **Processi**.</span><span class="sxs-lookup"><span data-stu-id="ddb12-138">The **Processes** dialog box appears.</span></span>  
  
7. <span data-ttu-id="ddb12-139">Selezionare la casella di controllo **Mostra processi di tutti gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="ddb12-139">Select the **Show processes from all users** check box.</span></span>  
  
8. <span data-ttu-id="ddb12-140">Nella sezione **Processi disponibili** scegliere il processo per il servizio e quindi scegliere **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="ddb12-140">In the **Available Processes** section, choose the process for your service, and then choose **Attach**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="ddb12-141">Il processo avrà lo stesso nome del file eseguibile del servizio.</span><span class="sxs-lookup"><span data-stu-id="ddb12-141">The process will have the same name as the executable file for your service.</span></span>  
  
     <span data-ttu-id="ddb12-142">Verrà visualizzata la finestra di dialogo **Connetti a processo** .</span><span class="sxs-lookup"><span data-stu-id="ddb12-142">The **Attach to Process** dialog box appears.</span></span>  
  
9. <span data-ttu-id="ddb12-143">Scegliere le opzioni appropriate e quindi scegliere **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ddb12-143">Choose the appropriate options, and then choose **OK** to close the dialog box.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ddb12-144">A questo punto si è in modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="ddb12-144">You are now in debug mode.</span></span>  
  
10. <span data-ttu-id="ddb12-145">Impostare i punti di interruzione da usare nel codice.</span><span class="sxs-lookup"><span data-stu-id="ddb12-145">Set any breakpoints you want to use in your code.</span></span>  
  
11. <span data-ttu-id="ddb12-146">Accedere a Gestione controllo servizi e modificare il servizio, specificando i comandi per arrestare, sospendere e riprendere il servizio, in modo da raggiungere i punti di interruzione impostati.</span><span class="sxs-lookup"><span data-stu-id="ddb12-146">Access the Services Control Manager and manipulate your service, sending stop, pause, and continue commands to hit your breakpoints.</span></span> <span data-ttu-id="ddb12-147">Per altre informazioni sull'esecuzione di Gestione controllo servizi, vedere [Procedura: Avviare servizi](how-to-start-services.md).</span><span class="sxs-lookup"><span data-stu-id="ddb12-147">For more information about running the Services Control Manager, see [How to: Start Services](how-to-start-services.md).</span></span> <span data-ttu-id="ddb12-148">Vedere anche [Risoluzione dei problemi: Debug dei servizi Windows](troubleshooting-debugging-windows-services.md).</span><span class="sxs-lookup"><span data-stu-id="ddb12-148">Also, see [Troubleshooting: Debugging Windows Services](troubleshooting-debugging-windows-services.md).</span></span>  
  
## <a name="debugging-tips-for-windows-services"></a><span data-ttu-id="ddb12-149">Suggerimenti per il debug dei servizi Windows</span><span class="sxs-lookup"><span data-stu-id="ddb12-149">Debugging Tips for Windows Services</span></span>  
 <span data-ttu-id="ddb12-150">La connessione al processo di un servizio consente di eseguire il debug della maggior parte del codice del servizio, ma non di tutto.</span><span class="sxs-lookup"><span data-stu-id="ddb12-150">Attaching to the service's process allows you to debug most, but not all, the code for that service.</span></span> <span data-ttu-id="ddb12-151">Poiché, ad esempio, il servizio è già stato avviato, non è possibile eseguire il debug del codice nel metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> del servizio o del codice nel metodo `Main` usato per caricare il servizio.</span><span class="sxs-lookup"><span data-stu-id="ddb12-151">For example, because the service has already been started, you cannot debug the code in the service's <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method or the code in the `Main` method that is used to load the service this way.</span></span> <span data-ttu-id="ddb12-152">Un modo per aggirare questa limitazione consiste nel creare un secondo servizio temporaneo nell'applicazione di servizio che esiste solo per il debug.</span><span class="sxs-lookup"><span data-stu-id="ddb12-152">One way to work around this limitation is to create a temporary second service in your service application that exists only to aid in debugging.</span></span> <span data-ttu-id="ddb12-153">È possibile installare entrambi i servizi, quindi avviare il servizio fittizio per caricare il processo del servizio.</span><span class="sxs-lookup"><span data-stu-id="ddb12-153">You can install both services, and then start this dummy service to load the service process.</span></span> <span data-ttu-id="ddb12-154">Una volta che il servizio temporaneo ha avviato il processo, usare il menu **Debug** in Visual Studio per connettersi al processo del servizio.</span><span class="sxs-lookup"><span data-stu-id="ddb12-154">Once the temporary service has started the process, you can use the **Debug** menu in Visual Studio to attach to the service process.</span></span>  
  
 <span data-ttu-id="ddb12-155">Provare ad aggiungere le chiamate al metodo <xref:System.Threading.Thread.Sleep%2A> per ritardare l'azione finché non si è in grado di connettersi al processo.</span><span class="sxs-lookup"><span data-stu-id="ddb12-155">Try adding calls to the <xref:System.Threading.Thread.Sleep%2A> method to delay action until you’re able to attach to the process.</span></span>  
  
 <span data-ttu-id="ddb12-156">Provare a modificare il programma in un'applicazione console normale.</span><span class="sxs-lookup"><span data-stu-id="ddb12-156">Try changing the program to a regular console application.</span></span> <span data-ttu-id="ddb12-157">A tale scopo, riscrivere il metodo `Main` come segue in modo che possa essere eseguito come servizio Windows e come applicazione console, a seconda della modalità di avvio.</span><span class="sxs-lookup"><span data-stu-id="ddb12-157">To do this, rewrite the `Main` method as follows so it can run both as a Windows Service and as a console application, depending on how it's started.</span></span>  
  
#### <a name="how-to-run-a-windows-service-as-a-console-application"></a><span data-ttu-id="ddb12-158">Procedura: eseguire un servizio Windows come applicazione console</span><span class="sxs-lookup"><span data-stu-id="ddb12-158">How to: Run a Windows Service as a console application</span></span>  
  
1. <span data-ttu-id="ddb12-159">Aggiungere un metodo al servizio che esegue i metodi <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A>:</span><span class="sxs-lookup"><span data-stu-id="ddb12-159">Add a method to your service that runs the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods:</span></span>  
  
    ```csharp  
    internal void TestStartupAndStop(string[] args)  
    {  
        this.OnStart(args);  
        Console.ReadLine();  
        this.OnStop();  
    }  
    ```  
  
2. <span data-ttu-id="ddb12-160">Riscrivere il metodo `Main` come segue:</span><span class="sxs-lookup"><span data-stu-id="ddb12-160">Rewrite the `Main` method as follows:</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        if (Environment.UserInteractive)  
        {  
            MyNewService service1 = new MyNewService(args);  
            service1.TestStartupAndStop(args);  
        }  
        else  
        {  
            // Put the body of your old Main method here.  
        }  
    }
    ```  
  
3. <span data-ttu-id="ddb12-161">Nella scheda **Applicazione** delle proprietà del progetto impostare il **Tipo di output** su **Applicazione console**.</span><span class="sxs-lookup"><span data-stu-id="ddb12-161">In the **Application** tab of the project's properties, set the **Output type** to **Console Application**.</span></span>  
  
4. <span data-ttu-id="ddb12-162">Scegliere **Avvia debug** (F5).</span><span class="sxs-lookup"><span data-stu-id="ddb12-162">Choose **Start Debugging** (F5).</span></span>  
  
5. <span data-ttu-id="ddb12-163">Per eseguire nuovamente il programma come servizio Windows, installarlo e avviarlo come di consueto per un servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="ddb12-163">To run the program as a Windows Service again, install it and start it as usual for a Windows Service.</span></span> <span data-ttu-id="ddb12-164">Non è necessario annullare queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="ddb12-164">It's not necessary to reverse these changes.</span></span>  
  
 <span data-ttu-id="ddb12-165">In alcuni casi, ad esempio quando si vuole eseguire il debug di un problema che si verifica solo all'avvio del sistema, è necessario usare il debugger di Windows.</span><span class="sxs-lookup"><span data-stu-id="ddb12-165">In some cases, such as when you want to debug an issue that occurs only on system startup, you have to use the Windows debugger.</span></span> <span data-ttu-id="ddb12-166">[Scaricare Windows Driver Kit (WDK)](/windows-hardware/drivers/download-the-wdk) e vedere [Esecuzione del debug dei servizi Windows](https://support.microsoft.com/kb/824344).</span><span class="sxs-lookup"><span data-stu-id="ddb12-166">[Download the Windows Driver Kit (WDK)](/windows-hardware/drivers/download-the-wdk) and see [How to debug Windows Services](https://support.microsoft.com/kb/824344).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddb12-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ddb12-167">See also</span></span>

- [<span data-ttu-id="ddb12-168">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="ddb12-168">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="ddb12-169">Procedura: installare e disinstallare servizi</span><span class="sxs-lookup"><span data-stu-id="ddb12-169">How to: Install and Uninstall Services</span></span>](how-to-install-and-uninstall-services.md)
- [<span data-ttu-id="ddb12-170">Procedura: Avviare servizi</span><span class="sxs-lookup"><span data-stu-id="ddb12-170">How to: Start Services</span></span>](how-to-start-services.md)
- [<span data-ttu-id="ddb12-171">Debug di un servizio</span><span class="sxs-lookup"><span data-stu-id="ddb12-171">Debugging a Service</span></span>](/windows/desktop/Services/debugging-a-service)

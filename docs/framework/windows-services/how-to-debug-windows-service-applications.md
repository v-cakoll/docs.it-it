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
# <a name="how-to-debug-windows-service-applications"></a>Procedura: Eseguire il debug di applicazioni di servizio di Windows
Poiché un servizio deve essere eseguito dall'interno del contesto di Gestione controllo servizi e non dall'interno di Visual Studio, il debug di un servizio non è semplice come quello di altri tipi di applicazioni di Visual Studio. Per eseguire il debug di un servizio, è necessario avviare il servizio e connettere un debugger al processo in cui viene eseguito. È quindi possibile eseguire il debug dell'applicazione tramite tutte le funzionalità di debug standard di Visual Studio.  
  
> [!CAUTION]
> Non connettersi a un processo a meno che non si conoscano il tipo di processo e le conseguenze di tale operazione, che potrebbe anche terminare il processo. Se ad esempio ci si connette al processo WinLogon e si interrompe il debug, il sistema si arresta in quanto non può funzionare senza WinLogon.  
  
 È possibile connettere il debugger solo a un servizio in esecuzione. Il processo di connessione interrompe il funzionamento corrente del servizio, in realtà non arresta né sospende l'elaborazione del servizio. Ciò significa che se il servizio è in esecuzione quando inizia il debug, tecnicamente si trova ancora nello stato Avviato all'avvio del debug, ma l'elaborazione è sospesa.  
  
 Dopo aver effettuato la connessione al processo, sarà possibile impostare i punti di interruzione e usarli per eseguire il debug del codice. Quando si chiude la finestra di dialogo usata per effettuare la connessione al processo, si entra in modalità di debug. È possibile usare Gestione controllo servizi per avviare, arrestare, sospendere e riprendere il servizio raggiungendo così i punti di interruzione impostati. Al termine del debug, è possibile rimuovere il servizio fittizio.  
  
 Questo articolo descrive il debug di un servizio in esecuzione nel computer locale, ma è possibile anche eseguire il debug di servizi Windows in esecuzione in un computer remoto. Vedere [Remote Debugging](/visualstudio/debugger/debug-installed-app-package).  
  
> [!NOTE]
> Il debug del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> può risultare difficile in quanto Gestione controllo servizi impone un limite di 30 secondi per tutti i tentativi di avvio di un servizio. Per altre informazioni, vedere [Risoluzione dei problemi: Debug dei servizi Windows](troubleshooting-debugging-windows-services.md).  
  
> [!WARNING]
> Per ottenere informazioni significative per il debug, il debugger di Visual Studio deve trovare il file di simboli per i file binari sottoposti a debug. Se si esegue il debug di un servizio compilato in Visual Studio, i file di simboli (con estensione PDB) si trovano nella stessa cartella dell'eseguibile o della libreria e il debugger li carica automaticamente. Se si esegue il debug di un servizio che non è stato compilato, è necessario prima trovare i simboli per il servizio e assicurarsi che possano essere individuati dal debugger. Vedere [Specificare file di simboli (con estensione pdb) e di origine nel debugger di Visual Studio](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger). Se si esegue il debug di un processo di sistema o è necessario avere i simboli per le chiamate di sistema nei servizi, aggiungere i server dei simboli Microsoft. Vedere [Simboli di debug](/windows/desktop/DxTechArts/debugging-with-symbols).  
  
### <a name="to-debug-a-service"></a>Per eseguire il debug di un servizio  
  
1. Compilare il servizio nella configurazione di debug.  
  
2. Installare il servizio. Per altre informazioni, vedere [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).  
  
3. Avviare il servizio da **Gestione controllo servizi**, da **Esplora server** o dal codice. Per altre informazioni, vedere [Procedura: Avviare servizi](how-to-start-services.md).  
  
4. Avviare Visual Studio con credenziali amministrative, in modo che sia possibile connettersi a processi di sistema.  
  
5. (Facoltativo) Nella barra dei menu di Visual Studio scegliere **Strumenti**, **Opzioni**. Nella finestra di dialogo **Opzioni** scegliere **Debug**, **Simboli**, selezionare la casella di controllo **Server dei simboli Microsoft** e quindi scegliere il pulsante **OK**.  
  
6. Nella barra dei menu scegliere **Connetti a processo** dal menu **Debug** o **Strumenti**. (scelta rapida da tastiera: CTRL+ALT+P).  
  
     Verrà visualizzata la finestra di dialogo **Processi**.  
  
7. Selezionare la casella di controllo **Mostra processi di tutti gli utenti**.  
  
8. Nella sezione **Processi disponibili** scegliere il processo per il servizio e quindi scegliere **Connetti**.  
  
    > [!TIP]
    > Il processo avrà lo stesso nome del file eseguibile del servizio.  
  
     Verrà visualizzata la finestra di dialogo **Connetti a processo** .  
  
9. Scegliere le opzioni appropriate e quindi scegliere **OK** per chiudere la finestra di dialogo.  
  
    > [!NOTE]
    > A questo punto si è in modalità di debug.  
  
10. Impostare i punti di interruzione da usare nel codice.  
  
11. Accedere a Gestione controllo servizi e modificare il servizio, specificando i comandi per arrestare, sospendere e riprendere il servizio, in modo da raggiungere i punti di interruzione impostati. Per altre informazioni sull'esecuzione di Gestione controllo servizi, vedere [Procedura: Avviare servizi](how-to-start-services.md). Vedere anche [Risoluzione dei problemi: Debug dei servizi Windows](troubleshooting-debugging-windows-services.md).  
  
## <a name="debugging-tips-for-windows-services"></a>Suggerimenti per il debug dei servizi Windows  
 La connessione al processo di un servizio consente di eseguire il debug della maggior parte del codice del servizio, ma non di tutto. Poiché, ad esempio, il servizio è già stato avviato, non è possibile eseguire il debug del codice nel metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> del servizio o del codice nel metodo `Main` usato per caricare il servizio. Un modo per aggirare questa limitazione consiste nel creare un secondo servizio temporaneo nell'applicazione di servizio che esiste solo per il debug. È possibile installare entrambi i servizi, quindi avviare il servizio fittizio per caricare il processo del servizio. Una volta che il servizio temporaneo ha avviato il processo, usare il menu **Debug** in Visual Studio per connettersi al processo del servizio.  
  
 Provare ad aggiungere le chiamate al metodo <xref:System.Threading.Thread.Sleep%2A> per ritardare l'azione finché non si è in grado di connettersi al processo.  
  
 Provare a modificare il programma in un'applicazione console normale. A tale scopo, riscrivere il metodo `Main` come segue in modo che possa essere eseguito come servizio Windows e come applicazione console, a seconda della modalità di avvio.  
  
#### <a name="how-to-run-a-windows-service-as-a-console-application"></a>Procedura: eseguire un servizio Windows come applicazione console  
  
1. Aggiungere un metodo al servizio che esegue i metodi <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A>:  
  
    ```csharp  
    internal void TestStartupAndStop(string[] args)  
    {  
        this.OnStart(args);  
        Console.ReadLine();  
        this.OnStop();  
    }  
    ```  
  
2. Riscrivere il metodo `Main` come segue:  
  
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
  
3. Nella scheda **Applicazione** delle proprietà del progetto impostare il **Tipo di output** su **Applicazione console**.  
  
4. Scegliere **Avvia debug** (F5).  
  
5. Per eseguire nuovamente il programma come servizio Windows, installarlo e avviarlo come di consueto per un servizio Windows. Non è necessario annullare queste modifiche.  
  
 In alcuni casi, ad esempio quando si vuole eseguire il debug di un problema che si verifica solo all'avvio del sistema, è necessario usare il debugger di Windows. [Scaricare Windows Driver Kit (WDK)](/windows-hardware/drivers/download-the-wdk) e vedere [Esecuzione del debug dei servizi Windows](https://support.microsoft.com/kb/824344).  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alle applicazioni di servizio Windows](introduction-to-windows-service-applications.md)
- [Procedura: installare e disinstallare servizi](how-to-install-and-uninstall-services.md)
- [Procedura: Avviare servizi](how-to-start-services.md)
- [Debug di un servizio](/windows/desktop/Services/debugging-a-service)

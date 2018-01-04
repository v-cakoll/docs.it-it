---
title: 'Procedura: eseguire il debug di applicazioni di servizio per Windows'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- Windows NT services, debugging
- Windows Service applications, debugging
- services, debugging
ms.assetid: 63ab0800-0f05-4f1e-88e6-94c73fd920a2
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 86d90e4129f089a77e51e6e58233a1087fe5d0f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-debug-windows-service-applications"></a>Procedura: eseguire il debug di applicazioni di servizio per Windows
Poiché un servizio deve essere eseguito dall'interno del contesto di Gestione controllo servizi e non dall'interno di Visual Studio, il debug di un servizio non è semplice come quello di altri tipi di applicazioni di Visual Studio. Per eseguire il debug di un servizio, è necessario avviare il servizio e connettere un debugger al processo in cui viene eseguito. È quindi possibile eseguire il debug dell'applicazione tramite tutte le funzionalità di debug standard di Visual Studio.  
  
> [!CAUTION]
>  Non connettersi a un processo a meno che non si conoscano il tipo di processo e le conseguenze di tale operazione, che potrebbe anche terminare il processo. Se ad esempio ci si connette al processo WinLogon e si interrompe il debug, il sistema si arresta in quanto non può funzionare senza WinLogon.  
  
 È possibile connettere il debugger solo a un servizio in esecuzione. Il processo di connessione interrompe il funzionamento corrente del servizio, in realtà non arresta né sospende l'elaborazione del servizio. Ciò significa che se il servizio è in esecuzione quando inizia il debug, tecnicamente si trova ancora nello stato Avviato all'avvio del debug, ma l'elaborazione è sospesa.  
  
 Dopo aver effettuato la connessione al processo, sarà possibile impostare i punti di interruzione e usarli per eseguire il debug del codice. Quando si chiude la finestra di dialogo usata per effettuare la connessione al processo, si entra in modalità di debug. È possibile usare Gestione controllo servizi per avviare, arrestare, sospendere e riprendere il servizio raggiungendo così i punti di interruzione impostati. Al termine del debug, è possibile rimuovere il servizio fittizio.  
  
 Questo articolo descrive il debug di un servizio in esecuzione nel computer locale, ma è possibile anche eseguire il debug di servizi Windows in esecuzione in un computer remoto. Vedere [il debug remoto](/visualstudio/debugger/debug-installed-app-package).  
  
> [!NOTE]
>  Il debug del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> può risultare difficile in quanto Gestione controllo servizi impone un limite di 30 secondi per tutti i tentativi di avvio di un servizio. Per ulteriori informazioni, vedere [risoluzione dei problemi: debug dei servizi Windows](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md).  
  
> [!WARNING]
>  Per ottenere informazioni significative per il debug, il debugger di Visual Studio deve trovare il file di simboli per i file binari sottoposti a debug. Se si esegue il debug di un servizio compilato in Visual Studio, i file di simboli (con estensione PDB) si trovano nella stessa cartella dell'eseguibile o della libreria e il debugger li carica automaticamente. Se si esegue il debug di un servizio che non è stato compilato, è necessario prima trovare i simboli per il servizio e assicurarsi che possano essere individuati dal debugger. Vedere [specifica simboli (PDB) e i file di origine](http://msdn.microsoft.com/library/1105e169-5272-4e7c-b3e7-cda1b7798a6b). Se si esegue il debug di un processo di sistema o è necessario avere i simboli per le chiamate di sistema nei servizi, aggiungere i server dei simboli Microsoft. Vedere [i simboli di debug](http://msdn.microsoft.com/windows/desktop/ee416588.aspx).  
  
### <a name="to-debug-a-service"></a>Per eseguire il debug di un servizio  
  
1.  Compilare il servizio nella configurazione di debug.  
  
2.  Installare il servizio. Per altre informazioni, vedere [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
3.  Avviare il servizio, da **Gestione controllo servizi**, **Esplora Server**, o dal codice. Per ulteriori informazioni, vedere [procedura: avviare servizi](../../../docs/framework/windows-services/how-to-start-services.md).  
  
4.  Avviare Visual Studio con credenziali amministrative, in modo che sia possibile connettersi a processi di sistema.  
  
5.  (Facoltativo) Nella barra dei menu di Visual Studio, scegliere **strumenti**, **opzioni**. Nel **opzioni** finestra di dialogo scegliere **debug**, **simboli**, selezionare il **server dei simboli Microsoft** casella di controllo e quindi scegliere il **OK** pulsante.  
  
6.  Nella barra dei menu, scegliere **Connetti a processo** dal **Debug** o **strumenti** menu. (scelta rapida da tastiera: CTRL+ALT+P).  
  
     Il **processi** viene visualizzata la finestra di dialogo.  
  
7.  Selezionare il **Mostra i processi di tutti gli utenti** casella di controllo.  
  
8.  Nel **processi disponibili** sezione, scegliere il processo per il servizio, quindi **collegamento**.  
  
    > [!TIP]
    >  Il processo avrà lo stesso nome del file eseguibile del servizio.  
  
     Verrà visualizzata la finestra di dialogo **Connetti a processo** .  
  
9. Scegliere le opzioni appropriate, quindi **OK** per chiudere la finestra di dialogo.  
  
    > [!NOTE]
    >  A questo punto si è in modalità di debug.  
  
10. Impostare i punti di interruzione da usare nel codice.  
  
11. Accedere a Gestione controllo servizi e modificare il servizio, specificando i comandi per arrestare, sospendere e riprendere il servizio, in modo da raggiungere i punti di interruzione impostati. Per ulteriori informazioni sull'esecuzione di Gestione controllo servizi, vedere [procedura: avviare servizi](../../../docs/framework/windows-services/how-to-start-services.md). Vedere anche [risoluzione dei problemi: debug dei servizi Windows](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md).  
  
## <a name="debugging-tips-for-windows-services"></a>Suggerimenti per il debug dei servizi Windows  
 La connessione al processo di un servizio consente di eseguire il debug della maggior parte del codice del servizio, ma non di tutto. Poiché, ad esempio, il servizio è già stato avviato, non è possibile eseguire il debug del codice nel metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> del servizio o del codice nel metodo `Main` usato per caricare il servizio. Un modo per aggirare questa limitazione consiste nel creare un secondo servizio temporaneo nell'applicazione di servizio che esiste solo per il debug. È possibile installare entrambi i servizi, quindi avviare il servizio fittizio per caricare il processo del servizio. Il servizio temporaneo ha avviato il processo, è possibile utilizzare il **Debug** menu in Visual Studio per connettersi al processo del servizio.  
  
 Provare ad aggiungere le chiamate al metodo <xref:System.Threading.Thread.Sleep%2A> per ritardare l'azione finché non si è in grado di connettersi al processo.  
  
 Provare a modificare il programma in un'applicazione console normale. A tale scopo, riscrivere il metodo `Main` come segue in modo che possa essere eseguito come servizio Windows e come applicazione console, a seconda della modalità di avvio.  
  
#### <a name="how-to-run-a-windows-service-as-a-console-application"></a>Procedura: eseguire un servizio Windows come applicazione console  
  
1.  Aggiungere un metodo al servizio che esegue i metodi <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A>:  
  
    ```  
    internal void TestStartupAndStop(string[] args)  
    {  
        this.OnStart(args);  
        Console.ReadLine();  
        this.OnStop();  
    }  
    ```  
  
2.  Riscrivere il metodo `Main` come segue:  
  
    ```  
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
    ```  
  
3.  Nel **applicazione** scheda delle proprietà del progetto, impostare il **tipo di Output** a **applicazione Console**.  
  
4.  Scegliere **avviare il debug** (F5).  
  
5.  Per eseguire nuovamente il programma come servizio Windows, installarlo e avviarlo come di consueto per un servizio Windows. Non è necessario annullare queste modifiche.  
  
 In alcuni casi, ad esempio quando si vuole eseguire il debug di un problema che si verifica solo all'avvio del sistema, è necessario usare il debugger di Windows. Installare [strumenti di debug per Windows](http://msdn.microsoft.com/windows/hardware/hh852365) e vedere [come eseguire il debug di servizi Windows](http://support.microsoft.com/kb/824344).  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Procedura: installare e disinstallare servizi](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [Procedura: avviare servizi](../../../docs/framework/windows-services/how-to-start-services.md)  
 [Debug di un servizio](http://msdn.microsoft.com/library/windows/desktop/ms682546.aspx)

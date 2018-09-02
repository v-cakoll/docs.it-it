---
title: Esecuzione del debug dei flussi di lavoro
ms.date: 03/30/2017
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
ms.openlocfilehash: 17cee1f1b509e777edd3f08c55d473d768b19b55
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463538"
---
# <a name="debugging-workflows"></a>Esecuzione del debug dei flussi di lavoro
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] offre diverse opzioni per eseguire il debug dei flussi di lavoro in esecuzione dall'ambiente di sviluppo. Il debug dei flussi di lavoro può essere eseguito nell'utilità di progettazione, in XAML e nel codice.  
  
## <a name="debugging-in-the-workflow-designer"></a>Debug nell'utilità di progettazione del flusso di lavoro  
 I punti di interruzione possono essere impostati nelle attività nella finestra di progettazione del flusso di lavoro sia evidenziando l'attività e premendo **F9** oppure usando i menu di scelta rapida dell'attività. L'esecuzione del flusso di lavoro si interrompe quindi quando l'host del flusso di lavoro viene eseguito in modalità di debug. Nella schermata seguente l'esecuzione del flusso di lavoro viene sospesa in un punto di interruzione. Per altre informazioni, vedere [debug dei flussi di lavoro con la finestra di progettazione del flusso di lavoro](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer).  
  
## <a name="debugging-in-xaml"></a>Debug in XAML  
 Se un flusso di lavoro viene sospeso in un punto di interruzione nella finestra di progettazione, il flusso di lavoro può essere sottoposto a debug anche in XAML. Per visualizzare il punto di esecuzione in XAML, selezionare **visualizzazione XAML** nella finestra di progettazione del flusso di lavoro durante l'esecuzione del flusso di lavoro viene sospesa. Il debug può essere nuovamente avviato dalla finestra di progettazione riaprendo il flusso di lavoro nella finestra da Esplora soluzioni. Per altre informazioni, vedere [procedura: eseguire il Debug di XAML con la finestra di progettazione del flusso di lavoro](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer).  
  
## <a name="debugging-in-code"></a>Debug nel codice  
 I punti di interruzione del codice possono essere usati nello stesso modo in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] e in altre applicazioni imperative. Fare clic sul margine sinistro del riquadro del codice per creare un punto di interruzione, codice o premi **F9** per inserire un punto di interruzione in corrispondenza della posizione del cursore.  
  
## <a name="attaching-to-a-workflow-process"></a>Connessione a un processo del flusso di lavoro  
 Il debug del flusso di lavoro è supportato anche usando l'infrastruttura di Visual Studio per la connessione a un processo. In questo modo, l'autore del flusso di lavoro può eseguire il debug di un flusso di lavoro in esecuzione in un ambiente host diverso, ad esempio Internet Information Services (IIS) 7.0.  
  
## <a name="remote-debugging"></a>Remote Debugging  
 Il debug remoto di Windows Workflow Foundation (WF) funziona esattamente come il debug remoto per gli altri componenti di Visual Studio. Per informazioni sul debug remoto, vedere [procedura: attivare il debug remoto](https://go.microsoft.com/fwlink/?LinkId=196257).  
  
> [!NOTE]
>  Se l'applicazione del flusso di lavoro ha come destinazione x86 architettura ed è ospitato in un computer che esegue un sistema operativo a 64 bit, il debug remoto non funzionerà a meno che non è installato Visual Studio nel computer remoto o la destinazione per l'applicazione del flusso di lavoro viene modificata in **Qualsiasi CPU**.  
  
## <a name="extending-the-workflow-debugging-service"></a>Estensione del servizio di debug del flusso di lavoro  
 Il servizio del debugger del flusso di lavoro è ora pubblico e può essere usato per creare applicazioni personalizzate quali monitoraggio, simulazione e debug in una finestra di progettazione riallocata. Per altre informazioni, vedere l'argomento <xref:System.Activities.Presentation.Debug.DebuggerService>.

---
title: 'Attività 1: creare una nuova applicazione Windows Presentation Foundation'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 5576d6f893aa405d454758387334b85a473b0c73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>Attività 1: creare una nuova applicazione Windows Presentation Foundation
In questa attività è creare un'applicazione Windows Presentation Foundation (WPF) vuota usando il modello di Visual Studio dell'applicazione WPF e aggiungere i riferimenti appropriati [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] gli assembly del flusso di lavoro.  
  
### <a name="to-create-the-wpf-application-project"></a>Per creare il progetto applicazione WPF  
  
1.  Aprire Visual Studio e scegliere il **File** dal menu **New**, quindi fare clic su **progetto**.  
  
2.  Nel **nuovo progetto** finestra di dialogo Seleziona **Visual c#** o **Visual Basic** dal **modelli installati** riquadro sul lato sinistro di la casella. Se la lingua di preferenza non viene visualizzato, cercarlo in **altri linguaggi**.  
  
3.  Selezionare **Windows** nel **modelli installati** riquadro.  
  
4.  Nel riquadro superiore, verificare che (il valore predefinito) **.NET Framework 4** è stata selezionata nella casella di riepilogo a discesa, quindi fare clic **applicazione WPF**.  
  
5.  Impostare il nome del progetto **HostingApplication** nella parte inferiore della finestra.  
  
6.  Impostare il nome della soluzione **RehostingTheDesigner**.  
  
7.  Fare clic su **OK** per creare il progetto di applicazione. Visual Studio crea una UI WPF di base per l'applicazione e include il XAML appropriato e un file code-behind.  
  
8.  Aggiungere riferimenti a **WorkflowModel** assembly. A tale scopo, in **Esplora**, fare doppio clic su di **HostingApplication** del progetto e selezionare **Aggiungi riferimento**.  
  
9. Nel **Aggiungi riferimento** la finestra di dialogo, fare clic su di **.NET** scheda, tenere premuto il tasto CTRL, selezionare gli assembly seguenti e quindi fare clic su **OK**:  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. Fare clic su **OK**.  
  
11. Vedere [attività 2: ospitare la finestra di progettazione del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) per imparare a ospitare il disegno della finestra di progettazione del flusso di lavoro.  
  
## <a name="see-also"></a>Vedere anche  
 [Riallocazione di Progettazione flussi di lavoro](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [Attività 2: Ospitare Progettazione flussi di lavoro](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)

---
title: 'Attività 1: Creare una nuova applicazione Windows Presentation Foundation'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: dae523714862ed36d36e65b51be62acff9b17f51
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193401"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>Attività 1: Creare una nuova applicazione Windows Presentation Foundation
In questa attività verranno creare un'applicazione Windows Presentation Foundation (WPF) vuota usando il modello di Visual Studio dell'applicazione WPF e aggiungere i riferimenti appropriati [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] gli assembly del flusso di lavoro.  
  
### <a name="to-create-the-wpf-application-project"></a>Per creare il progetto applicazione WPF  
  
1.  Aprire Visual Studio e scegliere il **File** dal menu **New**e quindi fare clic su **progetto**.  
  
2.  Nel **nuovo progetto** finestra di dialogo Seleziona **Visual C#**  oppure **Visual Basic** dal **modelli installati** riquadro a sinistra lato della casella. Se non viene visualizzato il linguaggio di propria scelta, cercarlo in **altri linguaggi**.  
  
3.  Selezionare **Windows** nel **modelli installati** riquadro.  
  
4.  Verificare che nel riquadro superiore (il valore predefinito) **.NET Framework 4** è stata selezionata nella casella di riepilogo a discesa e quindi selezionare **applicazione WPF**.  
  
5.  Impostare il nome del progetto in cui **HostingApplication** nella parte inferiore della finestra.  
  
6.  Impostare il nome della soluzione **RehostingTheDesigner**.  
  
7.  Fare clic su **OK** per creare il progetto di applicazione. Visual Studio crea una UI WPF di base per l'applicazione e include i file di code-behind e XAML appropriato.  
  
8.  Aggiungere riferimenti agli **WorkflowModel** assembly. A questo scopo, nella **Esplora soluzioni**, fare doppio clic il **HostingApplication** del progetto e selezionare **Aggiungi riferimento**.  
  
9. Nel **Aggiungi riferimento** finestra di dialogo, fare clic sulla **.NET** scheda, tenere premuto il tasto CTRL, selezionare gli assembly seguenti e quindi fare clic su **OK**:  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. Fare clic su **OK**.  
  
11. Vedere [attività 2: Ospitare la finestra di progettazione del flusso di lavoro](task-2-host-the-workflow-designer.md) per informazioni su come ospitare il canvas di progettazione di progettazione del flusso di lavoro.  
  
## <a name="see-also"></a>Vedere anche

- [Riallocazione dell'utilità di progettazione del flusso di lavoro](rehosting-the-workflow-designer.md)
- [Attività 2: Ospitare Progettazione flussi di lavoro](task-2-host-the-workflow-designer.md)

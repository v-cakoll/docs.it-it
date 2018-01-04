---
title: "Attività 1: creare una nuova applicazione Windows Presentation Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a207b09ff7124bb161678627f365a6fa4021a38d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>Attività 1: creare una nuova applicazione Windows Presentation Foundation
In questa attività verrà creata un'applicazione [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] vuota tramite il modello di Visual Studio dell'applicazione WPF e verranno aggiunti riferimenti agli assembly del flusso di lavoro di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] appropriati.  
  
### <a name="to-create-the-wpf-application-project"></a>Per creare il progetto applicazione WPF  
  
1.  Aprire [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] e scegliere il **File** dal menu **New**e quindi fare clic su **progetto**.  
  
2.  Nel **nuovo progetto** finestra di dialogo Seleziona **Visual c#** o **Visual Basic** dal **modelli installati** riquadro sul lato sinistro di la casella. Se la lingua di preferenza non viene visualizzato, cercarlo in **altri linguaggi**.  
  
3.  Selezionare **Windows** nel **modelli installati** riquadro.  
  
4.  Nel riquadro superiore, verificare che (il valore predefinito) **.NET Framework 4** è stata selezionata nella casella di riepilogo a discesa, quindi fare clic **applicazione WPF**.  
  
5.  Impostare il nome del progetto **HostingApplication** nella parte inferiore della finestra.  
  
6.  Impostare il nome della soluzione **RehostingTheDesigner**.  
  
7.  Fare clic su **OK** per creare il progetto di applicazione. [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] consente di creare un'interfaccia utente WPF di base per l'applicazione e dispone di file XAML e code-behind appropriati.  
  
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

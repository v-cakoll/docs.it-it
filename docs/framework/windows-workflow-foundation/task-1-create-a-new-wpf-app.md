---
title: 'Attività 1: creare una nuova applicazione Windows Presentation Foundation'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 3205840da575041b449eb841fc8084e89937fca7
ms.sourcegitcommit: 10db6551ea3c971470cf5d2cc21ba1cbcefe5c55
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2019
ms.locfileid: "72031891"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>Attività 1: creare una nuova applicazione Windows Presentation Foundation

In questa attività verrà creata un'applicazione Windows Presentation Foundation (WPF) vuota utilizzando il modello di Visual Studio dell'applicazione WPF e verranno aggiunti riferimenti agli assembly del flusso di lavoro [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] appropriati.  
  
## <a name="to-create-the-wpf-application-project"></a>Per creare il progetto applicazione WPF

1. Aprire Visual Studio e scegliere **nuovo**dal menu **file** , quindi fare clic su **progetto**.

2. Nella finestra di dialogo **nuovo progetto** selezionare **Visual C#**  o **Visual Basic** dal riquadro **modelli installati** sul lato sinistro della casella. Se il linguaggio scelto non viene visualizzato, cercare in **altre lingue**.

3. Selezionare **Windows** nel riquadro **modelli installati** .

4. Nel riquadro superiore, verificare che sia selezionato il valore predefinito **.NET Framework 4** nell'elenco a discesa, quindi selezionare **applicazione WPF**.

5. Impostare il nome del progetto su **HostingApplication** nella parte inferiore della finestra.

6. Impostare il nome della soluzione su **RehostingTheDesigner**.

7. Fare clic su **OK** per creare il progetto di applicazione. Visual Studio crea un'interfaccia utente WPF di base per l'applicazione e include i file XAML e code-behind appropriati.

8. Aggiungere riferimenti agli assembly **WorkflowModel** . A tale scopo, in **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **HostingApplication** e scegliere **Aggiungi riferimento**.

9. Nella finestra di dialogo **Aggiungi riferimento** fare clic sulla scheda **.NET** , tenere premuto il tasto CTRL, selezionare gli assembly seguenti e quindi fare clic su **OK**:

    - System.Activities
    - System.Activities.Presentation
    - System.Activities.Core.Presentation

10. Vedere [attività 2: ospitare la progettazione flussi di lavoro](task-2-host-the-workflow-designer.md) per informazioni su come ospitare l'area di progettazione di progettazione flussi di lavoro.

## <a name="see-also"></a>Vedere anche

- [Riallocazione di Progettazione flussi di lavoro](rehosting-the-workflow-designer.md)
- [Attività 2: Ospitare Progettazione flussi di lavoro](task-2-host-the-workflow-designer.md)

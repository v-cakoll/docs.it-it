---
title: 'Procedura: Creare un modello di attività personalizzato'
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: 4ec84658dbe3039a4d7d714f8da183e6a5eb6ca4
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989708"
---
# <a name="how-to-create-a-custom-activity-template"></a>Procedura: Creare un modello di attività personalizzato

I modelli di attività personalizzati vengono usati per personalizzare la configurazione delle attività, incluse CompositeActivity personalizzate, in modo che gli utenti non debbano creare individualmente ciascuna attività e configurare manualmente le relative proprietà e altre impostazioni. Questi modelli personalizzati possono essere resi disponibili nella **casella degli strumenti** [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in o da una finestra di progettazione ospitata nuovamente, da cui gli utenti possono trascinarli nell'area di progettazione preconfigurata. [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]viene fornito con esempi di modelli di questo tipo: [SendAndReceiveReply Template Designer](/visualstudio/workflow-designer/sendandreceivereply-template-designer) e [ReceiveAndSendReply Template Designer](/visualstudio/workflow-designer/receiveandsendreply-template-designer) nella categoria [Messaging Activity Designer](/visualstudio/workflow-designer/messaging-activity-designers) .

 Nella prima procedura di questo argomento viene descritto come creare un modello di attività personalizzato per un'attività **delay** e la seconda procedura descrive brevemente come renderlo disponibile in un [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] per verificare il corretto funzionamento del modello personalizzato.

 I modelli di attività personalizzati devono implementare l'oggetto <xref:System.Activities.Presentation.IActivityTemplateFactory>. L'interfaccia dispone di un singolo metodo <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> con il quale è possibile creare e configurare le istanze dell'attività usate nel modello.

## <a name="to-create-a-template-for-the-delay-activity"></a>Per creare un modello per l'attività Delay

1. Avviare Visual Studio 2010.

2. Nel menu **File** scegliere **Nuovo** e quindi selezionare **Progetto**.

     Verrà visualizzata la finestra di dialogo **Nuovo progetto** .

3. Nel riquadro **Tipi progetto** selezionare flusso di **lavoro** da progetti **visivi C#**  o **Visual Basic** raggruppamenti a seconda delle preferenze della lingua.

4. Nel riquadro **modelli** selezionare **libreria attività**.

5. Nella casella **nome** immettere `DelayActivityTemplate`.

6. Accettare le impostazioni predefinite nelle caselle di testo **percorso** e **Nome soluzione** , quindi fare clic su **OK**.

7. Fare clic con il pulsante destro del mouse sulla directory riferimenti del progetto DelayActivityTemplate in **Esplora soluzioni** e scegliere **Aggiungi riferimento** per aprire la finestra di dialogo **Aggiungi riferimento** .

8. Passare alla scheda **.NET** e selezionare **PresentationFramework** dalla colonna **nome componente** a sinistra e fare clic su **OK** per aggiungere un riferimento al file presentationframework. dll.

9. Ripetere questa procedura per aggiungere riferimenti ai file System.Activities.Presentation.dll e WindowsBase.dll.

10. Fare clic con il pulsante destro del mouse sul progetto DelayActivityTemplate in **Esplora soluzioni** e scegliere **Aggiungi** , quindi **nuovo elemento** per aprire la finestra di dialogo **Aggiungi nuovo elemento** .

11. Selezionare il modello di **classe** , denominarlo MyDelayTemplate e quindi fare clic su **OK**.

12. Aprire il file MyDelayTemplate.cs e aggiungere le istruzioni seguenti.

    ```csharp
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. Implementare <xref:System.Activities.Presentation.IActivityTemplateFactory> con la classe `MyDelayActivity` con il codice seguente. In questo modo viene configurata una durata del ritardo di 10 secondi.

    ```csharp
    public sealed class MyDelayActivity : IActivityTemplateFactory
    {
        public Activity Create(System.Windows.DependencyObject target)
        {
            return new System.Activities.Statements.Delay
            {
                DisplayName = "DelayActivityTemplate",
                Duration = new TimeSpan(0, 0, 10)

            };
        }
    }
    ```

14. Selezionare **Compila soluzione** dal menu **Compila** per generare il file DelayActivityTemplate. dll.

### <a name="to-make-the-template-available-in-a-workflow-designer"></a>Per rendere disponibile il modello in Progettazione flussi di lavoro

1. Fare clic con il pulsante destro del mouse sulla soluzione DelayActivityTemplate in **Esplora soluzioni** e scegliere **Aggiungi** , quindi **nuovo progetto** per aprire la finestra di dialogo **Aggiungi nuovo progetto** .

2. Selezionare il modello **applicazione console flusso di lavoro** , `CustomActivityTemplateApp`denominarlo e quindi fare clic su **OK**.

3. Fare clic con il pulsante destro del mouse sulla directory riferimenti del progetto CustomActivityTemplateApp in **Esplora soluzioni** e scegliere **Aggiungi riferimento** per aprire la finestra di dialogo **Aggiungi riferimento** .

4. Passare alla scheda **progetti** e selezionare **DelayActivityTemplate** nella colonna **nome progetto** a sinistra e fare clic su **OK** per aggiungere un riferimento al file DelayActivityTemplate. dll creato nella prima procedura.

5. Fare clic con il pulsante destro del mouse sul progetto CustomActivityTemplateApp in **Esplora soluzioni** e scegliere **Compila** per compilare l'applicazione.

6. Fare clic con il pulsante destro del mouse sul progetto CustomActivityTemplateApp in **Esplora soluzioni** e scegliere **Imposta come progetto di avvio**.

7. Selezionare **Avvia senza eseguire debug** dal menu **debug** e premere un tasto qualsiasi per continuare quando richiesto dalla finestra cmd. exe.

8. Aprire il file Workflow1. XAML e aprire la **casella degli strumenti**.

9. Individuare il modello **MyDelayActivity** nella categoria **DelayActivityTemplate** . Trascinarlo nell'area di progettazione. Verificare che nella finestra **Proprietà** la `Duration` proprietà sia stata impostata su 10 secondi.

## <a name="example"></a>Esempio
 Il file MyDelayActivity.cs deve contenere il codice seguente.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

//Namespaces added
using System.Activities;
using System.Activities.Statements;
using System.Activities.Presentation;
using System.Windows;

namespace DelayActivityTemplate
{
    public sealed class MyDelayActivity : IActivityTemplateFactory
    {
        public Activity Create(System.Windows.DependencyObject target)
        {
            return new System.Activities.Statements.Delay
            {
                DisplayName = "DelayActivityTemplate",
                Duration = new TimeSpan(0, 0, 10)

            };
        }
    }
}
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.Presentation.IActivityTemplateFactory>
- [Personalizzazione della fase di progettazione del flusso di lavoro](customizing-the-workflow-design-experience.md)

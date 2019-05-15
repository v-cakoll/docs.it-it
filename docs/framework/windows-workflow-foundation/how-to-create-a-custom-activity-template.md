---
title: 'Procedura: Creare un modello di attività personalizzato'
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: f54a625fbe5497406645ea29f824d361c0392eb3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637722"
---
# <a name="how-to-create-a-custom-activity-template"></a>Procedura: Creare un modello di attività personalizzato

I modelli di attività personalizzati vengono usati per personalizzare la configurazione delle attività, incluse CompositeActivity personalizzate, in modo che gli utenti non debbano creare individualmente ciascuna attività e configurare manualmente le relative proprietà e altre impostazioni. Questi modelli personalizzati possono essere rese disponibili nel **casella degli strumenti** nel [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] o da una finestra di progettazione riallocata dalla quale gli utenti possono trascinarli nell'area di progettazione preconfigurata. [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] viene fornito con efficaci esempi di tali modelli: il [progettazione del modello SendAndReceiveReply](/visualstudio/workflow-designer/sendandreceivereply-template-designer) e il [progettazione del modello ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer) nel [messaggistica gli ActivityDesigner](/visualstudio/workflow-designer/messaging-activity-designers) categoria.

 La prima procedura in questo argomento viene descritto come creare un modello di attività personalizzata per un **ritardo** attività e la seconda procedura viene descritto brevemente come renderlo disponibile in un [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] per verificare che il modello personalizzato funzioni.

 I modelli di attività personalizzati devono implementare l'oggetto <xref:System.Activities.Presentation.IActivityTemplateFactory>. L'interfaccia dispone di un singolo metodo <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> con il quale è possibile creare e configurare le istanze dell'attività usate nel modello.

## <a name="to-create-a-template-for-the-delay-activity"></a>Per creare un modello per l'attività Delay

1. Avviare Visual Studio 2010.

2. Nel menu **File** scegliere **Nuovo** e quindi selezionare **Progetto**.

     Verrà visualizzata la finestra di dialogo **Nuovo progetto** .

3. Nel **tipi di progetto** riquadro, selezionare **flusso di lavoro** dal **Visual c#** progetti o **Visual Basic** raggruppamenti in base il preferenze della lingua.

4. Nel **modelli** riquadro, selezionare **libreria attività**.

5. Nel **Name** immettere `DelayActivityTemplate`.

6. Accettare i valori predefiniti in di **posizione** e **Nome soluzione** caselle di testo e quindi fare clic su **OK**.

7. Fare doppio clic su directory riferimenti del progetto DelayActivityTemplate in **Esplora soluzioni** e scegliere **Aggiungi riferimento** per aprire il **Aggiungi riferimento** nella finestra di dialogo.

8. Andare alla **.NET** scheda e selezionare **PresentationFramework** dal **Component Name** colonna a sinistra e fare clic su **OK** per aggiungere un riferimento al file PresentationFramework. dll.

9. Ripetere questa procedura per aggiungere riferimenti ai file System.Activities.Presentation.dll e WindowsBase.dll.

10. Pulsante destro del mouse sul progetto DelayActivityTemplate in **Esplora soluzioni** e scegliere **Add** e quindi **nuovo elemento** per aprire la **Aggiungi nuovo elemento**finestra di dialogo.

11. Selezionare il **classe** modello, denominarlo MyDelayTemplate e quindi fare clic su **OK**.

12. Aprire il file MyDelayTemplate.cs e aggiungere le istruzioni seguenti.

    ```
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. Implementare <xref:System.Activities.Presentation.IActivityTemplateFactory> con la classe `MyDelayActivity` con il codice seguente. In questo modo viene configurata una durata del ritardo di 10 secondi.

    ```
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

14. Selezionare **Compila soluzione** dalle **compilazione** menu per generare il file Delayactivitytemplate DLL.

### <a name="to-make-the-template-available-in-a-workflow-designer"></a>Per rendere disponibile il modello in Progettazione flussi di lavoro

1. Pulsante destro del mouse sulla soluzione DelayActivityTemplate in **Esplora soluzioni** e scegliere **Add** e quindi **nuovo progetto** per aprire la **Aggiungi nuovo progetto** finestra di dialogo.

2. Selezionare il **applicazione Console flusso di lavoro** modello, denominarla `CustomActivityTemplateApp`, quindi fare clic su **OK**.

3. Fare doppio clic su directory riferimenti del progetto CustomActivityTemplateApp in **Esplora soluzioni** e scegliere **Aggiungi riferimento** per aprire il **Aggiungi riferimento** finestra di dialogo casella.

4. Andare alla **progetti** scheda e selezionare **DelayActivityTemplate** dal **nome progetto** colonna a sinistra e fare clic su **OK** per aggiungere un Fare riferimento al file Delayactivitytemplate creata nella prima procedura.

5. Pulsante destro del mouse sul progetto CustomActivityTemplateApp in **Esplora soluzioni** e scegliere **compilazione** per compilare l'applicazione.

6. Pulsante destro del mouse sul progetto CustomActivityTemplateApp in **Esplora soluzioni** e scegliere **imposta come progetto di avvio**.

7. Selezionare **Avvia senza eseguire debug** dalle **Debug** menu di scelta e premere qualsiasi tasto per continuare quando richiesto dalla finestra cmd.exe.

8. Aprire il file Workflow1.xaml e aprire il **casella degli strumenti**.

9. Individuare il **MyDelayActivity** modello nel **DelayActivityTemplate** categoria. Trascinarlo nell'area di progettazione. Confermare la **proprietà** finestra che la `Duration` proprietà è stata impostata su 10 secondi.

## <a name="example"></a>Esempio
 Il file MyDelayActivity.cs deve contenere il codice seguente.

```
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

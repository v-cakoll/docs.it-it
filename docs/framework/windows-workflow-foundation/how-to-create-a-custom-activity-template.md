---
title: "Procedura: Creare un modello di attività personalizzato"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2ae81b96a348712af58c5e8527f0f04a59689368
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-custom-activity-template"></a>Procedura: Creare un modello di attività personalizzato
I modelli di attività personalizzati vengono usati per personalizzare la configurazione delle attività, incluse CompositeActivity personalizzate, in modo che gli utenti non debbano creare individualmente ciascuna attività e configurare manualmente le relative proprietà e altre impostazioni. Questi modelli personalizzati possono essere resi disponibili nel **della casella degli strumenti** sul [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] o da una finestra di progettazione ospitata nuovamente, da cui gli utenti possono trascinarli nell'area di progettazione preconfigurata. [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]viene fornito con ottimi esempi di tali modelli: il [Progettazione modelli SendAndReceiveReply](/visualstudio/workflow-designer/sendandreceivereply-template-designer) e [progettazione del modello ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer) nel [progettazioni delle attività di messaggistica](/visualstudio/workflow-designer/messaging-activity-designers) categoria.  
  
 La prima procedura in questo argomento viene descritto come creare un modello di attività personalizzata per un **ritardo** attività mentre la seconda procedura viene descritto brevemente come renderlo disponibile in un [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] per verificare che il modello personalizzato funzioni.  
  
 I modelli di attività personalizzati devono implementare l'oggetto <xref:System.Activities.Presentation.IActivityTemplateFactory>. L'interfaccia dispone di un singolo metodo <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> con il quale è possibile creare e configurare le istanze dell'attività usate nel modello.  
  
### <a name="to-create-a-template-for-the-delay-activity"></a>Per creare un modello per l'attività Delay  
  
1.  Avviare [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Nel **File** dal menu **New**, quindi selezionare **progetto**.  
  
     Verrà visualizzata la finestra di dialogo **Nuovo progetto** .  
  
3.  Nel **tipi di progetto** riquadro, selezionare **flusso di lavoro** da uno di **Visual c#** progetti o **Visual Basic** raggruppamenti in base il preferenze della lingua.  
  
4.  Nel **modelli** riquadro, selezionare **libreria attività**.  
  
5.  Nel **nome** immettere `DelayActivityTemplate`.  
  
6.  Accettare le impostazioni predefinite di **percorso** e **Nome soluzione** caselle di testo e quindi fare clic su **OK**.  
  
7.  Fare clic sulla directory riferimenti del progetto DelayActivityTemplate in **Esplora** e scegliere **Aggiungi riferimento** per aprire la **Aggiungi riferimento** la finestra di dialogo.  
  
8.  Passare al **.NET** e selezionare **PresentationFramework** dal **nome componente** colonna a sinistra e fare clic su **OK** per aggiungere un riferimento al file PresentationFramework.dll.  
  
9. Ripetere questa procedura per aggiungere riferimenti ai file System.Activities.Presentation.dll e WindowsBase.dll.  
  
10. Fare clic sul progetto DelayActivityTemplate in **Esplora** e scegliere **Aggiungi** e quindi **nuovo elemento** per aprire la **Aggiungi nuovo elemento**la finestra di dialogo.  
  
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
  
14. Selezionare **Compila soluzione** dal **compilare** menu per generare il file DelayActivityTemplate.dll.  
  
### <a name="to-make-the-template-available-in-a-workflow-designer"></a>Per rendere disponibile il modello in Progettazione flussi di lavoro  
  
1.  Pulsante destro del mouse sulla soluzione DelayActivityTemplate in **Esplora** e scegliere **Aggiungi** e quindi **nuovo progetto** per aprire la **Aggiungi nuovo progetto** la finestra di dialogo.  
  
2.  Selezionare il **applicazione Console flusso di lavoro** modello, il nome `CustomActivityTemplateApp`, quindi fare clic su **OK**.  
  
3.  Fare clic sulla directory riferimenti del progetto CustomActivityTemplateApp in **Esplora** e scegliere **Aggiungi riferimento** per aprire la **Aggiungi riferimento** finestra di dialogo casella.  
  
4.  Passare al **progetti** e selezionare **DelayActivityTemplate** dal **nome progetto** colonna a sinistra e fare clic su **OK** per aggiungere un Fare riferimento al file DelayActivityTemplate.dll creato nella prima procedura.  
  
5.  Pulsante destro del mouse sul progetto CustomActivityTemplateApp in **Esplora** e scegliere **compilare** per compilare l'applicazione.  
  
6.  Pulsante destro del mouse sul progetto CustomActivityTemplateApp in **Esplora** e scegliere **imposta come progetto di avvio**.  
  
7.  Selezionare **Avvia senza eseguire debug** dal **Debug** menu e premere un tasto qualsiasi per continuare quando richiesto nella finestra di cmd.exe.  
  
8.  Aprire il file Workflow1 XAML e il **della casella degli strumenti**.  
  
9. Individuare il **MyDelayActivity** modello il **DelayActivityTemplate** categoria. Trascinarlo nell'area di progettazione. Confermare il **proprietà** finestra che la `Duration` proprietà è stata impostata su 10 secondi.  
  
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
 <xref:System.Activities.Presentation.IActivityTemplateFactory>  
 [Personalizzazione della fase di progettazione del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)

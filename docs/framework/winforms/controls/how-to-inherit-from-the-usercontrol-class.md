---
title: 'Procedura: ereditare dalla classe UserControl'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
ms.openlocfilehash: 2c8ef38abb5abc76e7d21e06ab7b76de2dda4885
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533819"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a>Procedura: ereditare dalla classe UserControl
Per combinare le funzionalità di uno o più controlli Windows Form con il codice personalizzato, è possibile creare un *controllo utente*. I controlli utente combinano lo sviluppo rapido del controllo, la funzionalità del controllo standard di Windows Forms e la versatilità di proprietà e metodi personalizzati. Quando si inizia con la creazione di un controllo utente, viene visualizzata una finestra di progettazione in cui è possibile inserire controlli Windows Forms standard. Questi controlli mantengono tutte le funzionalità intrinseche, nonché l'aspetto e il comportamento dei controlli standard. Una volta che questi controlli sono incorporati nel controllo utente, tuttavia, non sono più disponibili tramite codice. Il controllo utente esegue il proprio disegno e gestisce anche tutte le funzionalità di base associate ai controlli.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-user-control"></a>Per creare un controllo utente  
  
1.  Creare un nuovo progetto **Libreria di controlli Windows**.  
  
     Viene creato un nuovo progetto con un controllo utente vuoto.  
  
2.  Trascinare i controlli dalla scheda **Windows Forms** della **Casella degli strumenti** nella finestra di progettazione.  
  
3.  Questi controlli devono essere posizionati e progettati come si desidera che vengano visualizzati nel controllo utente finale. Se si desidera consentire agli sviluppatori di accedere ai controlli costitutivi, è necessario dichiararli come public o esporre in modo selettivo le proprietà del controllo che li costituiscono. Per informazioni dettagliate, [Procedura: Esporre le proprietà dei controlli costitutivi](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md).  
  
4.  Implementare eventuali metodi o proprietà personalizzati da incorporare nel controllo.  
  
5.  Per compilare il progetto ed eseguire il controllo in **UserControl Test Container**, premere F5. Per altre informazioni, vedere [Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di controlli personalizzati](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [Procedura: Ereditare dalla classe Control](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [Procedura: Ereditare da controlli Windows Form esistenti](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [Procedura: Creare controlli per Windows Form](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)

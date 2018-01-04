---
title: 'Procedura: ereditare da controlli di Windows Form esistenti'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6049e5e0f2d79bab8ad90b6e63e91d4d4fa705ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>Procedura: ereditare da controlli di Windows Form esistenti
Se si desidera estendere le funzionalità di un controllo esistente, è possibile creare un controllo derivato da un controllo esistente tramite l'ereditarietà. Quando si eredita da un controllo esistente, si ereditano tutte le funzionalità e le proprietà visive di tale controllo. Ad esempio, se si crea un controllo che eredita da <xref:System.Windows.Forms.Button>, il nuovo controllo avrà un aspetto e funzionano esattamente come standard <xref:System.Windows.Forms.Button> controllo. È quindi possibile estendere o modificare la funzionalità del nuovo controllo tramite l'implementazione di metodi e proprietà personalizzati. In alcuni controlli, è anche possibile modificare l'aspetto visivo del controllo ereditato eseguendo l'override relativo <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-an-inherited-control"></a>Per creare un controllo ereditato  
  
1.  Creare un nuovo progetto di **Applicazione Windows Form**.  
  
2.  Dal menu **Progetto**, scegliere **Aggiungi nuovo elemento**.  
  
     Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.  
  
3.  Nella finestra di dialogo **Aggiungi nuovo elemento**, fare doppio clic su **Controllo personalizzato**.  
  
     Un nuovo controllo personalizzato viene aggiunto al progetto.  
  
4.  Se si usa Visual Basic, nella parte in alto di **Esplora soluzioni**, fare clic su **Mostra tutti i file**. Espandere CustomControl1.vb e quindi aprire Customcontrol1 nell'Editor di codice.  
  
5.  Se si usa C#, aprire CustomControl1.cs nell'Editor di codice.  
  
6.  Individuare la dichiarazione di classe che eredita da <xref:System.Windows.Forms.Control>.  
  
7.  Modificare la classe di base per il controllo da cui si desidera ereditare.  
  
     Ad esempio, se si desidera ereditare <xref:System.Windows.Forms.Button>, modificare la dichiarazione di classe per le operazioni seguenti:  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  Se si usa Visual Basic, salvare e chiudere CustomControl1.Designer.vb. Aprire Customcontrol1.vb nell'Editor di codice.  
  
9. Implementare eventuali metodi o proprietà personalizzati da incorporare nel controllo.  
  
10. Se si desidera modificare l'aspetto grafico del controllo, eseguire l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.  
  
    > [!NOTE]
    >  Si esegue l'override <xref:System.Windows.Forms.Control.OnPaint%2A> non consente di modificare l'aspetto di tutti i controlli. I controlli che hanno tutti il disegno eseguito da Windows (ad esempio, <xref:System.Windows.Forms.TextBox>) non chiamano mai loro <xref:System.Windows.Forms.Control.OnPaint%2A> (metodo) e pertanto non verrà mai utilizzare codice personalizzato. Fare riferimento alla documentazione della Guida per il controllo specifico che si desidera modificare per vedere se il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo è disponibile. Per un elenco di tutti i controlli Windows Forms vedere [Controlli da usare in Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md). Se non dispone di un controllo <xref:System.Windows.Forms.Control.OnPaint%2A> elencato come un metodo di membro, non è possibile modificare l'aspetto eseguendo l'override di questo metodo. Per altre informazioni sul disegno personalizzato, vedere [Disegno e rendering di controlli personalizzati](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
    ```vb  
    Protected Overrides Sub OnPaint(ByVal e As _  
       System.Windows.Forms.PaintEventArgs)  
       MyBase.OnPaint(e)  
       ' Insert code to do custom painting.   
       ' If you want to completely change the appearance of your control,  
       ' do not call MyBase.OnPaint(e).  
    End Sub  
    ```  
  
    ```csharp  
    protected override void OnPaint(PaintEventArgs pe)  
    {  
       base.OnPaint(pe);  
       // Insert code to do custom painting.  
       // If you want to completely change the appearance of your control,  
       // do not call base.OnPaint(pe).  
    }  
    ```  
  
11. Salvare ed eseguire il test del controllo.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di controlli personalizzati](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [Procedura: Ereditare dalla classe Control](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [Procedura: Ereditare dalla classe UserControl](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [Procedura: Creare controlli per Windows Form](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [Procedura dettagliata: Eredità da un controllo Windows Form con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [Procedura dettagliata: eredità da un controllo di Windows Forms con Visual C#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

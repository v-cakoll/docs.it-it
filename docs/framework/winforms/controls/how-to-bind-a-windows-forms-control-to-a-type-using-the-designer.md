---
title: 'Procedura: associare un controllo Windows Form a un tipo mediante la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a25b0dc81a6511698394eb86343f09051befc87f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a>Procedura: associare un controllo Windows Form a un tipo mediante la finestra di progettazione
Quando si compilano controlli che interagiscono con i dati, a volte è necessario associare un controllo a un tipo anziché a un oggetto. Di solito è necessario associare un controllo a un tipo in fase di progettazione, quando i dati potrebbero non essere disponibili, ma i controlli associati ai dati devono comunque visualizzare i dati provenienti dall'interfaccia pubblica di un tipo. Le procedure seguenti viene illustrato come creare un nuovo <xref:System.Windows.Forms.BindingSource> che è associato a un tipo e quindi come associare una delle proprietà del tipo per il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà di un <xref:System.Windows.Forms.TextBox>.  
  
### <a name="to-bind-the-bindingsource-to-a-type"></a>Per associare BindingSource a un tipo  
  
1.  Creare un nuovo progetto Windows Forms.  
  
     Per altre informazioni, vedere [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  In **progettazione** visualizzare, trascinare un <xref:System.Windows.Forms.BindingSource> componente al form.  
  
3.  Nel **proprietà** finestra, fare clic sulla freccia per la <xref:System.Windows.Forms.BindingSource.DataSource%2A> proprietà.  
  
4.  Nell'**editor di tipo con interfaccia utente DataSource** fare clic su **Aggiungi origine dati progetto**.  
  
5.  Nella pagina **Selezionare un tipo di origine dati** selezionare **Oggetto** e fare clic su **Avanti**.  
  
6.  Selezionare il tipo da associare:  
  
    -   Se il tipo da associare è nel progetto corrente o l'assembly che contiene il tipo è già stato aggiunto come riferimento, espandere i nodi per trovare il tipo desiderato e quindi selezionarlo.  
  
         oppure  
  
    -   Se il tipo da associare è in un altro assembly, attualmente non presente nell'elenco di riferimenti, fare clic su **Aggiungi riferimento**, quindi fare clic sulla scheda **Progetti**. Selezionare il progetto che contiene l'oggetto business desiderato e fare clic su **OK**. Il progetto verrà visualizzato nell'elenco di assembly e sarà possibile espandere i nodi per trovare il tipo desiderato e quindi selezionarlo.  
  
        > [!NOTE]
        >  Se si vuole associare un tipo in un framework o assembly Microsoft, deselezionare la casella di controllo **Nascondi assembly che iniziano con Microsoft o System**.  
  
7.  Scegliere **Avanti**e quindi fare clic su **Fine**.  
  
### <a name="to-bind-the-control-to-the-bindingsource"></a>Per associare il controllo a BindingSource  
  
1.  Aggiungere un tipo <xref:System.Windows.Forms.TextBox> al form.  
  
2.  Nella finestra **Proprietà** espandere il nodo **(DataBindings)** .  
  
3.  Fare clic sulla freccia accanto al <xref:System.Windows.Forms.TextBox.Text%2A> proprietà.  
  
4.  Nel **editor del tipo di interfaccia utente DataSource**, espandere il nodo per il <xref:System.Windows.Forms.BindingSource> aggiunto in precedenza e selezionare la proprietà del tipo associato che si desidera associare il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà del <xref:System.Windows.Forms.TextBox>.  
  
## <a name="see-also"></a>Vedere anche  
 [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Procedura: Associare un controllo di Windows Form a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 [Associare controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)

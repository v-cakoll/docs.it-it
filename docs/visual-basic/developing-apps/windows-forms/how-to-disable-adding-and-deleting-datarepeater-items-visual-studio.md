---
title: 'Procedura: disabilitare l''aggiunta e l''eliminazione di elementi DataRepeater (Visual Studio)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, disabling delete
- DataRepeater, disabling add
ms.assetid: 298d8f60-ddfe-4361-ab66-cf76d0df5220
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1b15fe6fb5190855126ffa60ac488aaa74ad9b5a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-disable-adding-and-deleting-datarepeater-items-visual-studio"></a>Procedura: disabilitare l'aggiunta e l'eliminazione di elementi DataRepeater (Visual Studio)
Per impostazione predefinita, gli utenti possono aggiungere ed eliminare elementi in un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Gli utenti possono aggiungere un nuovo elemento premendo CTRL + N quando un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> ha lo stato attivo o facendo clic di **AddNewItem** pulsante il <xref:System.Windows.Forms.BindingNavigator> controllo. Gli utenti possono eliminare un elemento premendo CANC quando un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> ha lo stato attivo o facendo clic di **DeleteItem** pulsante il <xref:System.Windows.Forms.BindingNavigator> controllo.  
  
 È possibile disabilitare l'aggiunta e/o l'eliminazione in fase di progettazione o in fase di esecuzione.  
  
### <a name="to-disable-adding-and-deleting-at-design-time"></a>Per disabilitare l'aggiunta ed eliminazione in fase di progettazione  
  
1.  In Progettazione Windows Form, selezionare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
    > [!NOTE]
    >  È necessario selezionare la sezione inferiore del controllo. Se si seleziona l'area del modello di elemento, verrà visualizzato un set diverso di proprietà.  
  
2.  Nella finestra Proprietà impostare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> proprietà **False**.  
  
3.  Impostare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> proprietà **False**.  
  
4.  In Progettazione Windows Form, selezionare il <xref:System.Windows.Forms.BindingNavigator> controllare e quindi scegliere il **AddNewItem** pulsante (il pulsante con un segno più).  
  
5.  Nella finestra Proprietà impostare il <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> proprietà **False**.  
  
6.  In Progettazione Windows Form, selezionare il <xref:System.Windows.Forms.BindingNavigator> controllare e quindi scegliere il **DeleteItem** pulsante (il pulsante con una X rossa su di esso).  
  
7.  Nella finestra Proprietà impostare il <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> proprietà **False**.  
  
8.  Nella barra dei componenti, selezionare il <xref:System.Windows.Forms.BindingSource> a cui il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> è associato.  
  
9. Nella finestra Proprietà impostare il <xref:System.Windows.Forms.BindingSource.AllowNew%2A> proprietà **False**.  
  
10. In Progettazione Windows Form, fare doppio clic su di **DeleteItem** pulsante per aprire l'Editor di codice.  
  
11. Nell'elenco a discesa degli eventi, selezionare il `BindingNavigatorDeleteItem_EnabledChanged` evento.  
  
12. Aggiungere il codice seguente al gestore eventi `BindingNavigatorDeleteItem_EnabledChanged` :  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  Questo passaggio è necessario affinché <xref:System.Windows.Forms.BindingSource> abiliti il pulsante **DeleteItem** pulsante a ogni modifica del record corrente.  
  
### <a name="to-disable-adding-and-deleting-at-run-time"></a>Per disabilitare l'aggiunta ed eliminazione in fase di esecuzione  
  
1.  In Progettazione Windows Form, fare doppio clic sul form per aprire l'editor di codice.  
  
2.  Aggiungere il codice seguente all'evento `Form_Load` :  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.vb)]  
  
3.  Aggiungere il codice seguente al gestore eventi `BindingNavigatorDeleteItem_EnabledChanged` :  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  Questo passaggio è necessario affinché <xref:System.Windows.Forms.BindingSource> abiliti il pulsante **DeleteItem** pulsante a ogni modifica del record corrente.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)

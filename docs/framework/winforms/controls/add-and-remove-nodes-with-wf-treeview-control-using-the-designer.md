---
title: 'Procedura: aggiungere e rimuovere nodi nel controllo TreeView Windows Form mediante la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f6295f915e9204e9996d8902b07a3dfc4c5c2ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>Procedura: aggiungere e rimuovere nodi nel controllo TreeView Windows Form mediante la finestra di progettazione
Perché il Windows Form <xref:System.Windows.Forms.TreeView> controllo vengono visualizzati i nodi in modo gerarchico, quando si aggiunge un nodo è necessario prestare attenzione al nodo padre.  
  
 La procedura seguente richiede un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.TreeView> controllo. Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a>Per aggiungere o rimuovere nodi nella finestra di progettazione  
  
1.  Selezionare il controllo <xref:System.Windows.Forms.TreeView>.  
  
2.  Nel **proprietà** finestra, fare clic su di **i puntini di sospensione** (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al pulsante il <xref:System.Windows.Forms.TreeView.Nodes%2A> proprietà.  
  
     Il **Editor TreeNode** viene visualizzato.  
  
3.  Per aggiungere nodi, deve essere presente un nodo radice; Se non esiste, è innanzitutto necessario aggiungere una radice facendo clic di **Aggiungi radice** pulsante. È quindi possibile aggiungere i nodi figlio, selezionando la radice o qualsiasi altro nodo e scegliendo il **Aggiungi figlio** pulsante.  
  
4.  Per eliminare i nodi, selezionare il nodo da eliminare, quindi scegliere il **eliminare** pulsante.  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [Panoramica sul controllo TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [Procedura: Impostare icone per il controllo TreeView di Windows Form](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)  
 [Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Form](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [Procedura: Individuare il nodo di TreeView scelto](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)

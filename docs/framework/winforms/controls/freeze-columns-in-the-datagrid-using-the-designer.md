---
title: 'Procedura: bloccare le colonne nel controllo DataGridView di Windows Form utilizzando la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 049dd4952dc8af2c0f56567d8f2f53f5be5928ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: bloccare le colonne nel controllo DataGridView di Windows Form utilizzando la finestra di progettazione
Quando gli utenti visualizzano i dati contenuti in un controllo <xref:System.Windows.Forms.DataGridView> Windows Form, a volte devono fare spesso riferimento a una sola colonna o a un set di colonne. Ad esempio, quando si visualizza una tabella di informazioni sui clienti che contiene molte colonne, è utile per poter visualizzare il nome del cliente in qualsiasi momento mentre le altre colonne scorrono all'esterno dell'area visibile.  
  
 A tale scopo, è possibile bloccare le colonne nel controllo. Quando si blocca una colonna, vengono bloccate anche tutte le colonne alla sua sinistra (o alla sua destra, nelle lingue scritte da destra a sinistra). Le colonne bloccate rimangono ferme mentre tutte le altre colonne possono scorrere. Se viene abilitato il riordinamento delle colonne, le colonne bloccate vengono considerate come un gruppo distinto dalle colonne non bloccate. Gli utenti possono riposizionare le colonne in entrambi i gruppi, ma non possono spostare una colonna da un gruppo all'altro.  
  
 La procedura seguente richiede un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo. Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-freeze-a-column-using-the-designer"></a>Per bloccare una colonna utilizzando la finestra di progettazione  
  
1.  Fare clic sul glifo smart tag (![Smart Tag glifo](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del <xref:System.Windows.Forms.DataGridView> controllare e quindi selezionare **Modifica colonne**.  
  
2.  Selezionare una colonna dal **colonne selezionate** elenco.  
  
3.  Nel **proprietà colonna** griglia, impostare il <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> proprietà `true`.  
  
    > [!NOTE]
    >  È inoltre possibile bloccare una colonna quando viene aggiunta selezionando il **Frozen** casella il **Aggiungi colonna** la finestra di dialogo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>  
 [Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [Procedura: Abilitare il riordinamento delle colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 [Procedura: visualizzare il testo da destra a sinistra in Windows Form per la globalizzazione](http://msdn.microsoft.com/en-us/f0663385-2354-4c65-8676-706422283b14)  
 [Procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Procedura: Aggiungere controlli a un Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)

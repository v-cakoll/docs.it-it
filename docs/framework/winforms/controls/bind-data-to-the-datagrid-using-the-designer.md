---
title: 'Procedura: associare dati al controllo DataGridView di Windows Form utilizzando la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a3c7422bc83c7ee1f09bac05333799708cd2f2f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: associare dati al controllo DataGridView di Windows Form utilizzando la finestra di progettazione
È possibile utilizzare la finestra di progettazione per connettere un <xref:System.Windows.Forms.DataGridView> controllo alle origini dati di tipi diversi, tra cui database, oggetti business o i servizi Web. Quando si associa il controllo a un'origine dati tramite la finestra di progettazione, il controllo viene automaticamente associato a un <xref:System.Windows.Forms.BindingSource> componente che rappresenta l'origine dati. Inoltre vengono generate automaticamente colonne nel controllo, in modo corrispondente alle informazioni di schema fornite dall'origine dati.  
  
 Dopo la generazione delle colonne, è possibile modificarle in base alle esigenze. Ad esempio è possibile rimuovere o nascondere le colonne che non si vuole visualizzare, riorganizzare le colonne o cambiare i tipi di colonna. Per informazioni sulla modifica delle colonne, vedere gli argomenti elencati nella sezione Vedere anche.  
  
 È anche possibile associare più <xref:System.Windows.Forms.DataGridView> controlli alle tabelle correlate per creare relazioni master-details. In questa configurazione un controllo visualizza una tabella padre e un altro controllo visualizza solo le righe di una tabella figlio che sono correlate alla riga corrente nella tabella padre. Per altre informazioni, vedere [Procedura: Visualizzare dati correlati in un'applicazione Windows Forms](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).  
  
 La procedura seguente richiede un **applicazione Windows** progetto con un modulo che contiene un <xref:System.Windows.Forms.DataGridView> i due controlli per una relazione master-details. Per informazioni su come avviare un progetto di questo tipo, vedere [Procedura: Creare un progetto di applicazione Windows.](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [Procedura: Aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-bind-the-control-to-a-data-source"></a>Per associare il controllo a un'origine dati  
  
1.  Fare clic sul glifo smart tag (![Smart Tag glifo](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del <xref:System.Windows.Forms.DataGridView> controllo.  
  
2.  Fare clic sulla freccia a discesa dell'opzione **Scegli origine dati**.  
  
3.  Se il progetto non contiene già un'origine dati, fare clic su **Aggiungi origine dati progetto** e seguire i passaggi indicati dalla procedura guidata.  
  
     Per altre informazioni, vedere [Configurazione guidata origine dati](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f). La nuova origine dati sarà visualizzata nella finestra di riepilogo a discesa **Scegli origine dati**. Se la nuova origine dati contiene un solo membro, ad esempio una singola tabella di database, il controllo verrà associato automaticamente a tale membro. In caso contrario, andare al passaggio successivo.  
  
4.  Espandere i nodi **Altre origini dati** e **Origini dati del progetto** se non sono ancora espansi e quindi selezionare l'origine dati a cui associare il controllo.  
  
5.  Se l'origine dati contiene più di un membro, ad esempio se è stato creato un <xref:System.Data.DataSet?displayProperty=nameWithType> che contiene più tabelle, espandere l'origine dati e quindi selezionare il membro specifico da associare.  
  
6.  Per creare una relazione master-Details, nel **Scegli origine dati** finestra di riepilogo a discesa per un secondo <xref:System.Windows.Forms.DataGridView> controllare, espandere il <xref:System.Windows.Forms.BindingSource> creato per la tabella padre e quindi selezionare la tabella figlio correlata dall'elenco visualizzati.  
  
    > [!NOTE]
    >  Se il progetto include già un'origine dati, è possibile anche usare la finestra **Origini dati** per creare un modulo dati. Per altre informazioni, vedere [Finestra Origini dati](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 [Procedura: Connettersi ai dati di un database](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556)  
 [Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [Procedura: Modificare l'ordine delle colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 [Procedura: Modificare il tipo di una colonna DataGridView di Windows Form usando la finestra di progettazione](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 [Procedura: Bloccare le colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 [Procedura: Nascondere le colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 [Procedura: Rendere le colonne di sola lettura nel controllo DataGridView di Windows Form usando la finestra di progettazione](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 [Procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Procedura: Aggiungere controlli a un Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [Finestra Origini dati](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)  
 [Procedura: Visualizzare dati correlati in un'applicazione Windows Forms](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)

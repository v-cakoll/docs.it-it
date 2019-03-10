---
title: 'Procedura: Associare dati al controllo DataGridView Windows Form usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
ms.openlocfilehash: 8c90366111957f27a6bd86035013eba00426f46b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718506"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: Associare dati al controllo DataGridView Windows Form usando la finestra di progettazione
È possibile usare la finestra di progettazione per la connessione una <xref:System.Windows.Forms.DataGridView> controllo alle origini dati di molti tipi diversi, tra cui database, oggetti business o i servizi Web. Quando si associa il controllo a un'origine dati tramite la finestra di progettazione, il controllo viene automaticamente associato a un <xref:System.Windows.Forms.BindingSource> componente che rappresenta l'origine dati. Inoltre vengono generate automaticamente colonne nel controllo, in modo corrispondente alle informazioni di schema fornite dall'origine dati.  
  
 Dopo la generazione delle colonne, è possibile modificarle in base alle esigenze. Ad esempio è possibile rimuovere o nascondere le colonne che non si vuole visualizzare, riorganizzare le colonne o cambiare i tipi di colonna. Per informazioni sulla modifica delle colonne, vedere gli argomenti elencati nella sezione Vedere anche.  
  
 È anche possibile associare più <xref:System.Windows.Forms.DataGridView> controlli alle tabelle correlate per creare relazioni master/dettaglio. In questa configurazione un controllo visualizza una tabella padre e un altro controllo visualizza solo le righe di una tabella figlio che sono correlate alla riga corrente nella tabella padre. Per altre informazioni, vedere [Procedura: Visualizzare correlati i dati in una Windows Forms Application](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120)).  
  
 La procedura seguente richiede un **applicazione di Windows** progetto con un modulo che contiene un <xref:System.Windows.Forms.DataGridView> o due controlli per una relazione master/dettaglio. Per informazioni sull'avvio di un progetto, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-bind-the-control-to-a-data-source"></a>Per associare il controllo a un'origine dati  
  
1.  Fare clic sul glifo dello smart tag (![glifo Smart Tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del <xref:System.Windows.Forms.DataGridView> controllo.  
  
2.  Fare clic sulla freccia a discesa dell'opzione **Scegli origine dati**.  
  
3.  Se il progetto non contiene già un'origine dati, fare clic su **Aggiungi origine dati progetto** e seguire i passaggi indicati dalla procedura guidata.  
  
     Per altre informazioni, vedere [Configurazione guidata origine dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/w4dd7z6t(v=vs.120)). La nuova origine dati sarà visualizzata nella finestra di riepilogo a discesa **Scegli origine dati**. Se la nuova origine dati contiene un solo membro, ad esempio una singola tabella di database, il controllo verrà associato automaticamente a tale membro. In caso contrario, andare al passaggio successivo.  
  
4.  Espandere i nodi **Altre origini dati** e **Origini dati del progetto** se non sono ancora espansi e quindi selezionare l'origine dati a cui associare il controllo.  
  
5.  Se l'origine dati contiene più di un membro, ad esempio se è stato creato un <xref:System.Data.DataSet?displayProperty=nameWithType> che contiene più tabelle, espandere l'origine dati e quindi selezionare il membro specifico da associare.  
  
6.  Per creare una relazione master/dettaglio, nelle **Scegli origine dati** finestra di riepilogo a discesa per un secondo <xref:System.Windows.Forms.DataGridView> controllare, espandere il <xref:System.Windows.Forms.BindingSource> creato per la tabella padre e quindi selezionare la tabella figlio correlata dall'elenco illustrato.  
  
    > [!NOTE]
    >  Se il progetto include già un'origine dati, è possibile anche usare la finestra **Origini dati** per creare un modulo dati. Per altre informazioni, vedere [Finestra Origini dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120)).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- [Procedura: Connettersi ai dati in un Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))
- [Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView Windows Form usando la finestra di progettazione](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Procedura: Modificare l'ordine delle colonne nel controllo DataGridView Windows Form usando la finestra di progettazione](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)
- [Procedura: Modificare il tipo di una colonna DataGridView di Windows Form usando la finestra di progettazione](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)
- [Procedura: Bloccare le colonne nel controllo DataGridView Windows Form usando la finestra di progettazione](freeze-columns-in-the-datagrid-using-the-designer.md)
- [Procedura: Nascondere colonne nel controllo DataGridView Windows Form usando la finestra di progettazione](hide-columns-in-the-datagrid-using-the-designer.md)
- [Procedura: Rendere le colonne di sola lettura nel controllo DataGridView Windows Form usando la finestra di progettazione](make-columns-read-only-in-the-datagrid-using-the-designer.md)
- [Procedura: Creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md)
- [Finestra Origini dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))
- [Procedura: Visualizzare i dati correlati in una Windows Forms Application](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))

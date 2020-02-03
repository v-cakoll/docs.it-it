---
title: Cenni preliminari sul controllo DataGrid
ms.date: 03/30/2017
f1_keywords:
- DataGrid
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- columns [Windows Forms], DataGrid control
- data sources [Windows Forms], binding to DataGrid control
- tables [Windows Forms], binding to DataGrid control
- DataGrid control [Windows Forms], data binding
- DataGrid control [Windows Forms], about DataGrid control
- parent tables in DataGrid control
- tables [Windows Forms], displaying in DataGrid control
- data grids [Windows Forms], about data grids
- multiple tables in DataGrid control
- data [Windows Forms], resorting
- data [Windows Forms], navigating
- parent table navigation in DataGrid
- child tables [Windows Forms], dataGrid control
ms.assetid: 85604bce-bc03-49d9-9030-dda8896c44b1
ms.openlocfilehash: df559926dbc9141276f0a03deb99e340fd7212da
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742573"
---
# <a name="datagrid-control-overview-windows-forms"></a>Cenni preliminari sul controllo DataGrid (Windows Form)

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

Il controllo <xref:System.Windows.Forms.DataGrid> Windows Forms visualizza i dati in una serie di righe e colonne. Il caso più semplice è quando la griglia è associata a un'origine dati con una singola tabella che non contiene relazioni. In questo caso, i dati vengono visualizzati in semplici righe e colonne, come in un foglio di calcolo. Per altre informazioni sul data binding ad altri controlli, vedere [Data binding e Windows Form](../data-binding-and-windows-forms.md).

Se <xref:System.Windows.Forms.DataGrid> è associato a dati con più tabelle correlate e se è abilitata l'esplorazione della griglia, la griglia visualizzerà degli espansori in ogni riga. Con un espansore, l'utente può spostarsi da una tabella padre a una tabella figlio. Facendo clic su un nodo, viene visualizzata la tabella figlio e, facendo clic su un pulsante Indietro, viene visualizzata la tabella padre originale. In questo modo, nella griglia vengono visualizzate le relazioni gerarchiche tra le tabelle.

La schermata seguente mostra un DataGrid associato a dati con più tabelle:

![Un'app WinForms che mostra un DataGrid associato a dati con più tabelle.](./media/datagrid-control-overview-windows-forms/datagrid-bound-multiple-tables.gif)

<xref:System.Windows.Forms.DataGrid> può fornire un'interfaccia utente per un set di dati, la navigazione tra tabelle correlate e funzionalità avanzate di formattazione e modifica.

La visualizzazione e la manipolazione dei dati sono funzioni separate: il controllo gestisce l'interfaccia utente, mentre gli aggiornamenti dei dati vengono gestiti dall'architettura di data binding Windows Forms e dai provider di dati .NET Framework. Quindi più controlli associati alla stessa origine dati resteranno sincronizzati.

> [!NOTE]
> Se si ha familiarità con il controllo DataGrid in Visual Basic 6.0, si noteranno alcune differenze significative nel controllo <xref:System.Windows.Forms.DataGrid> Windows Form.

Quando la griglia è associata a un <xref:System.Data.DataSet>, le colonne e le righe vengono automaticamente create, formattate e compilate. Per altre informazioni, vedere [Data binding e Windows Form](../data-binding-and-windows-forms.md). Dopo la generazione del controllo <xref:System.Windows.Forms.DataGrid>, è possibile aggiungere, eliminare, riorganizzare e formattare le colonne e le righe in base alle proprie esigenze.

## <a name="binding-data-to-the-control"></a>Data binding al controllo

Per funzionare, il controllo <xref:System.Windows.Forms.DataGrid> deve essere associato a un'origine dati usando le proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> in fase di progettazione o il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>in fase di esecuzione. Questa associazione associa <xref:System.Windows.Forms.DataGrid> a un oggetto origine dati di cui è stata creata un'istanza, ad esempio <xref:System.Data.DataSet> o <xref:System.Data.DataTable>. Il controllo <xref:System.Windows.Forms.DataGrid> mostra i risultati delle azioni eseguite sui dati. La maggior parte delle azioni specifiche dei dati non viene eseguita tramite <xref:System.Windows.Forms.DataGrid>, ma tramite l'origine dati.

Se i dati nel set di dati associato vengono aggiornati con qualsiasi meccanismo, il controllo <xref:System.Windows.Forms.DataGrid> rispecchia le modifiche. Se la griglia dati e gli stili di tabella e colonna hanno la proprietà `ReadOnly` impostata su `false`, i dati nel set di dati possono essere aggiornati tramite il controllo <xref:System.Windows.Forms.DataGrid>.

In <xref:System.Windows.Forms.DataGrid> può essere visualizzata una sola tabella per volta. Se viene definita una relazione padre-figlio tra le tabelle, l'utente può spostarsi tra le tabelle correlate per selezionare la tabella da visualizzare nel controllo <xref:System.Windows.Forms.DataGrid>. Per informazioni sull'associazione di un controllo <xref:System.Windows.Forms.DataGrid> a un'origine dati ADO.NET in fase di progettazione o in fase di esecuzione, vedere [procedura: associare il controllo DataGrid Windows Forms a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).

Le origini dati valide per <xref:System.Windows.Forms.DataGrid> includono:

- Classe <xref:System.Data.DataTable>

- Classe <xref:System.Data.DataView>

- Classe <xref:System.Data.DataSet>

- Classe <xref:System.Data.DataViewManager>

Se l'origine è un set di dati, il set di dati potrebbe essere un oggetto nel form o un oggetto passato al form da un servizio Web XML. È possibile eseguire il binding sia a set di dati tipizzati che non tipizzati.

È anche possibile associare un controllo <xref:System.Windows.Forms.DataGrid> ad altre strutture se gli oggetti nella struttura, ad esempio gli elementi in una matrice, espongono proprietà pubbliche. La griglia visualizzerà tutte le proprietà pubbliche degli elementi nella struttura. Ad esempio, se si associa il controllo <xref:System.Windows.Forms.DataGrid> a una matrice di oggetti Customer, la griglia visualizzerà tutte le proprietà pubbliche di questi oggetti Customer. In alcuni casi, ciò significa che, anche se è possibile eseguire il binding alla struttura, la struttura associata risultante potrebbe non avere utilità pratica. Ad esempio, è possibile eseguire il binding a una matrice di Integer, ma, poiché il tipo di dati `Integer` non supporta una proprietà pubblica, la griglia non può visualizzare i dati.

È possibile eseguire il binding alle seguenti strutture se gli elementi espongono proprietà pubbliche:

- Qualsiasi componente che implementa l'interfaccia <xref:System.Collections.IList>, incluse le matrici unidimensionali.

- Qualsiasi componente che implementa l'interfaccia <xref:System.ComponentModel.IListSource>,

- Qualsiasi componente che implementa l'interfaccia <xref:System.ComponentModel.IBindingList>,

 Per altre informazioni sulle possibili origini dati, vedere [Origini dati supportate da Windows Form](../data-sources-supported-by-windows-forms.md).

## <a name="grid-display"></a>Visualizzazione della griglia

Il controllo <xref:System.Windows.Forms.DataGrid> di solito viene usato per visualizzare una singola tabella di dati da un set di dati. Tuttavia, il controllo può anche essere usato per visualizzare più tabelle, incluse le tabelle correlate. La visualizzazione della griglia viene regolata automaticamente in base all'origine dati. La tabella seguente illustra che cosa viene visualizzato a seconda della configurazione.

|Contenuto del set di dati|Elementi visualizzati|
|--------------------------|-----------------------|
|Una sola tabella.|La tabella viene visualizzata in una griglia.|
|Più tabelle.|La griglia può mostrare una visualizzazione albero in cui gli utenti possono spostarsi per trovare la tabella che vogliono visualizzare.|
|Più tabelle correlate.|La griglia può mostrare una visualizzazione albero con cui selezionare le tabelle oppure è possibile specificare che la griglia mostri la tabella padre. I record nella tabella padre consentono agli utenti di passare alle righe figlio correlate.|

> [!NOTE]
> Le tabelle in un set di dati vengono correlate con <xref:System.Data.DataRelation>. Vedere anche [creare relazioni tra set di impostazioni](/visualstudio/data-tools/relationships-in-datasets).

Quando il controllo <xref:System.Windows.Forms.DataGrid> visualizza una tabella e la proprietà <xref:System.Windows.Forms.DataGrid.AllowSorting%2A> è impostata su `true`, i dati possono essere ripristinati facendo clic sulle intestazioni di colonna. L'utente può inoltre aggiungere righe e modificare le celle.

Le relazioni tra un set di tabelle vengono visualizzate per gli utenti usando una struttura di navigazione padre/figlio. Le tabelle padre sono il livello più elevato di dati e le tabelle figlio sono le tabelle di dati derivate dai singoli elenchi delle tabelle padre. Gli espansori vengono visualizzati in ogni riga padre che contiene una tabella figlio. Facendo clic su un espansore, viene generato un elenco di collegamenti Web alle tabelle figlio. Quando l'utente seleziona un collegamento, viene visualizzata la tabella figlio. Fare clic sull'icona Mostra/Nascondi righe padre (![Icona Mostra/Nascondi righe padre](./media/datagrid-control-overview-windows-forms/show-hide-parent-rows.gif)) consente di nascondere le informazioni sulla tabella padre o di rivisualizzarle se l'utente lo ha precedentemente nascosto. L'utente può fare clic su un pulsante Indietro per tornare alla tabella visualizzata in precedenza.

## <a name="columns-and-rows"></a>Colonne e righe

<xref:System.Windows.Forms.DataGrid> è costituito da una raccolta di oggetti <xref:System.Windows.Forms.DataGridTableStyle> che sono contenuti nella proprietà <xref:System.Windows.Forms.DataGrid> dell'oggetto <xref:System.Windows.Forms.DataGrid.TableStyles%2A>. Uno stile tabella può contenere una raccolta di oggetti <xref:System.Windows.Forms.DataGridColumnStyle> contenuti nella proprietà <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> di <xref:System.Windows.Forms.DataGridTableStyle>. È possibile modificare le proprietà <xref:System.Windows.Forms.DataGrid.TableStyles%2A> e <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> utilizzando gli editor della raccolta accessibili tramite la finestra **Proprietà** .

Qualsiasi <xref:System.Windows.Forms.DataGridTableStyle> associato al controllo <xref:System.Windows.Forms.DataGrid> è accessibile tramite <xref:System.Windows.Forms.GridTableStylesCollection>. <xref:System.Windows.Forms.GridTableStylesCollection> può essere modificato nella finestra di progettazione con l'editor della raccolta <xref:System.Windows.Forms.DataGridTableStyle> o a livello di codice tramite la proprietà <xref:System.Windows.Forms.DataGrid> del controllo <xref:System.Windows.Forms.DataGrid.TableStyles%2A>.

La figura seguente Mostra gli oggetti inclusi nel controllo DataGrid:

![Diagramma che Mostra gli oggetti inclusi nel controllo DataGrid.](./media/datagrid-control-overview-windows-forms/visual-basic-columns.gif)

Gli stili tabella e gli stili colonna vengono sincronizzati con gli oggetti <xref:System.Data.DataTable> e gli oggetti <xref:System.Data.DataColumn> impostandone le proprietà `MappingName` sulle proprietà <xref:System.Data.DataTable.TableName%2A> e <xref:System.Data.DataColumn.ColumnName%2A> appropriate. Quando un oggetto <xref:System.Windows.Forms.DataGridTableStyle> senza stili colonna viene aggiunto a un controllo <xref:System.Windows.Forms.DataGrid> associato a un'origine dati valida e la proprietà <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> dello stile tabella viene impostata su una proprietà <xref:System.Data.DataTable.TableName%2A> valida, viene creata una raccolta di oggetti <xref:System.Windows.Forms.DataGridColumnStyle> per tale stile tabella. Per ogni <xref:System.Data.DataColumn> trovato nella raccolta <xref:System.Data.DataTable.Columns%2A> di <xref:System.Data.DataTable>, un corrispondente <xref:System.Windows.Forms.DataGridColumnStyle> viene aggiunto a <xref:System.Windows.Forms.GridColumnStylesCollection>. È possibile accedere all'oggetto <xref:System.Windows.Forms.GridColumnStylesCollection> attraverso la proprietà <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> di <xref:System.Windows.Forms.DataGridTableStyle>. Le colonne possono essere aggiunte o eliminate dalla griglia applicando il metodo <xref:System.Windows.Forms.GridColumnStylesCollection.Add%2A> o <xref:System.Windows.Forms.GridColumnStylesCollection.Remove%2A> a <xref:System.Windows.Forms.GridColumnStylesCollection>. Per altre informazioni, vedere [Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md) e [Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md).

Una raccolta di tipi di colonna estende la classe <xref:System.Windows.Forms.DataGridColumnStyle> con funzionalità avanzate di modifica e formattazione. Tutti i tipi di colonna ereditano dalla classe base <xref:System.Windows.Forms.DataGridColumnStyle>. La classe creata dipende dalla proprietà <xref:System.Data.DataColumn.DataType%2A> dell'oggetto <xref:System.Data.DataColumn> su cui si basa <xref:System.Web.UI.WebControls.DataGridColumn>. Ad esempio, un oggetto <xref:System.Data.DataColumn> con la proprietà <xref:System.Data.DataColumn.DataType%2A> impostata su <xref:System.Boolean> verrà associato a <xref:System.Windows.Forms.DataGridBoolColumn>. La tabella seguente descrive ciascuno di questi tipi di colonna.

|Tipo di colonna|Descrizione|
|-----------------|-----------------|
|<xref:System.Windows.Forms.DataGridTextBoxColumn>|Accetta e visualizza i dati come stringhe formattate o non formattate. Le funzionalità di modifica sono le stesse usate per modificare dati in un semplice oggetto <xref:System.Windows.Forms.TextBox>. Eredita da <xref:System.Windows.Forms.DataGridColumnStyle>.|
|<xref:System.Windows.Forms.DataGridBoolColumn>|Accetta e visualizza `true`, `false` e i valori null. Eredita da <xref:System.Windows.Forms.DataGridColumnStyle>.|

Facendo doppio clic sul bordo destro di una colonna, la colonna viene ridimensionata per poter visualizzare la didascalia completa e la voce più lunga.

## <a name="table-styles-and-column-styles"></a>Stili di tabella e stili colonna

Subito dopo aver stabilito il formato predefinito del controllo <xref:System.Windows.Forms.DataGrid>, è possibile personalizzare i colori che verranno usati quando nella griglia dati vengono visualizzate determinate tabelle.

Questo risultato viene ottenuto creando istanze della classe <xref:System.Windows.Forms.DataGridTableStyle>. Gli stili tabella specificano la formattazione di determinate tabelle, che è diversa da quella predefinita del controllo <xref:System.Windows.Forms.DataGrid> stesso. Per ogni tabella può essere definito un solo stile per volta.

In alcuni casi, è preferibile che l'aspetto di una colonna specifica sia diverso da quello delle altre colonne di una particolare tabella dati. È possibile creare un set personalizzato di stili di colonna usando la proprietà <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>.

Gli stili colonna sono correlati alle colonne in un set di dati proprio come gli stili tabella sono correlati alle tabelle di dati. Come per ogni tabella può essere definito un solo uno stile per volta, anche per ogni colonna può essere definito un solo stile, in un particolare stile tabella. Questa relazione è definita nella proprietà <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> della colonna.

Se è stato creato uno stile tabella senza aggiungere gli stili di colonna, Visual Studio aggiungerà gli stili di colonna predefiniti quando il form e la griglia vengono creati in fase di esecuzione. Tuttavia, se è stato creato uno stile tabella a cui sono stati aggiunti stili di colonna, Visual Studio non creerà alcun stile di colonna. Inoltre, sarà necessario definire stili colonna a cui assegnare il nome di mapping per visualizzare nella griglia le colonne desiderate.

Poiché, per specificare le colonne incluse nella griglia dati, è necessario assegnare uno stile colonna e alle colonne non è stato assegnato alcuno stile colonna, è possibile includere nel set di dati le colonne di dati non visualizzate nella griglia. Tuttavia, poiché la colonna di dati è inclusa nel set di dati, è possibile modificare a livello di codice i dati non visualizzati.

> [!NOTE]
> In generale, creare gli stili colonna e aggiungerli alla raccolta di stili colonna prima di aggiungere gli stili tabella alla raccolta di stili tabella. Quando si aggiunge uno stile tabella vuoto alla raccolta, gli stili colonna vengono generati automaticamente. Di conseguenza, verrà generata un'eccezione se si cerca di aggiungere nuovi stili colonna con valori <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> duplicati alla raccolta di stili colonna.
>
> In alcuni casi, è preferibile perfezionare una sola colonna tra tante. Ad esempio, il set di dati contiene 50 colonne e ne servono solo 49. In questo caso, è più semplice importare tutte le 50 colonne e rimuoverne una a livello di codice, invece di aggiungere una per una le 49 colonne desiderate a livello di codice.

## <a name="formatting"></a>Formattazione

La formattazione che può essere applicata al controllo <xref:System.Windows.Forms.DataGrid> include gli stili bordo, gli stili delle linee della griglia, i tipi di carattere, le proprietà delle didascalie, l'allineamento dei dati e l'alternanza dei colori di sfondo tra una riga e l'altra. Per altre informazioni, vedere [Procedura: Formattare il controllo DataGrid Windows Form](how-to-format-the-windows-forms-datagrid-control.md).

## <a name="events"></a>Eventi

Oltre ai normali eventi di controllo, ad esempio <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.Enter> e <xref:System.Windows.Forms.DataGrid.Scroll>, il controllo <xref:System.Windows.Forms.DataGrid> supporta gli eventi associati alla modifica e alla navigazione all'interno della griglia. La proprietà <xref:System.Windows.Forms.DataGrid.CurrentCell%2A> determina quale cella viene selezionata. Quando l'utente passa a una nuova cella, viene generato l'evento <xref:System.Windows.Forms.DataGrid.CurrentCellChanged>. Quando l'utente passa a una nuova tabella mediante le relazioni padre/figlio, viene generato l'evento <xref:System.Windows.Forms.DataGrid.Navigate>. Quando l'utente fa clic sul pulsante Indietro mentre visualizza una tabella figlio, viene generato l'evento <xref:System.Windows.Forms.DataGrid.BackButtonClick> e, quando si fa clic sull'icona per l'attivazione o la disattivazione della visualizzazione delle righe padre, viene generato l'evento <xref:System.Windows.Forms.DataGrid.ShowParentDetailsButtonClick>.

## <a name="see-also"></a>Vedere anche

- [Controllo DataGrid](datagrid-control-windows-forms.md)
- [Procedura: Associare il controllo DataGrid Windows Form a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Procedura: Formattare il controllo DataGrid di Windows Form](how-to-format-the-windows-forms-datagrid-control.md)

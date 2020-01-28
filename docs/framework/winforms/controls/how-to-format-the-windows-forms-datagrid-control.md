---
title: Formattare il controllo DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: 30342a89f3176255fa7217ccbbbd91c166ff7f35
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732967"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a><span data-ttu-id="ea029-102">Procedura: formattare il controllo DataGrid di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ea029-102">How to: Format the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="ea029-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="ea029-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="ea029-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ea029-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="ea029-105">L'applicazione di colori diversi a diverse parti di un controllo <xref:System.Windows.Forms.DataGrid> può contribuire a rendere le informazioni più facili da leggere e interpretare.</span><span class="sxs-lookup"><span data-stu-id="ea029-105">Applying different colors to various parts of a <xref:System.Windows.Forms.DataGrid> control can help to make the information in it easier to read and interpret.</span></span> <span data-ttu-id="ea029-106">Il colore può essere applicato a righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="ea029-106">Color can be applied to rows and columns.</span></span> <span data-ttu-id="ea029-107">Le righe e le colonne possono anche essere nascoste o visualizzate a propria discrezione.</span><span class="sxs-lookup"><span data-stu-id="ea029-107">Rows and columns can also be hidden or shown at your discretion.</span></span>  
  
 <span data-ttu-id="ea029-108">La formattazione del controllo <xref:System.Windows.Forms.DataGrid> è costituita da tre aspetti di base.</span><span class="sxs-lookup"><span data-stu-id="ea029-108">There are three basic aspects of formatting the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="ea029-109">È possibile impostare le proprietà per stabilire uno stile predefinito in cui vengono visualizzati i dati.</span><span class="sxs-lookup"><span data-stu-id="ea029-109">You can set properties to establish a default style in which data is displayed.</span></span> <span data-ttu-id="ea029-110">Da tale base è quindi possibile personalizzare la modalità di visualizzazione di determinate tabelle in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ea029-110">From that base, you can then customize the way certain tables are displayed at run time.</span></span> <span data-ttu-id="ea029-111">Infine, è possibile modificare le colonne visualizzate nella griglia dei dati, nonché i colori e altre formattazioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="ea029-111">Finally, you can modify which columns are displayed in the data grid as well as the colors and other formatting that is shown.</span></span>  
  
 <span data-ttu-id="ea029-112">Come passaggio iniziale per la formattazione di una griglia di dati, è possibile impostare le proprietà del <xref:System.Windows.Forms.DataGrid> stesso.</span><span class="sxs-lookup"><span data-stu-id="ea029-112">As an initial step in formatting a data grid, you can set the properties of the <xref:System.Windows.Forms.DataGrid> itself.</span></span> <span data-ttu-id="ea029-113">Queste scelte di colore e formato costituiscono una base da cui è possibile apportare modifiche in base alle tabelle e alle colonne di dati visualizzate.</span><span class="sxs-lookup"><span data-stu-id="ea029-113">These color and format choices form a base from which you can then make changes depending on the data tables and columns displayed.</span></span>  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a><span data-ttu-id="ea029-114">Per stabilire uno stile predefinito per il controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="ea029-114">To establish a default style for the DataGrid control</span></span>  
  
1. <span data-ttu-id="ea029-115">Impostare le proprietà seguenti in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="ea029-115">Set the following properties as appropriate:</span></span>  
  
    |<span data-ttu-id="ea029-116">Gli</span><span class="sxs-lookup"><span data-stu-id="ea029-116">Property</span></span>|<span data-ttu-id="ea029-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea029-117">Description</span></span>|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<span data-ttu-id="ea029-118">La proprietà <xref:System.Windows.Forms.DataGrid.BackColor%2A> definisce il colore delle righe pari della griglia.</span><span class="sxs-lookup"><span data-stu-id="ea029-118">The <xref:System.Windows.Forms.DataGrid.BackColor%2A> property defines the color of the even-numbered rows of the grid.</span></span> <span data-ttu-id="ea029-119">Quando si imposta la proprietà <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> su un colore diverso, ogni altra riga viene impostata sul nuovo colore (righe 1, 3, 5 e così via).</span><span class="sxs-lookup"><span data-stu-id="ea029-119">When you set the <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> property to a different color, every other row is set to this new color (rows 1, 3, 5, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|<span data-ttu-id="ea029-120">Il colore di sfondo delle righe pari della griglia (righe 0, 2, 4, 6 e così via).</span><span class="sxs-lookup"><span data-stu-id="ea029-120">The background color of the even-numbered rows of the grid (rows 0, 2, 4, 6, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|<span data-ttu-id="ea029-121">Mentre le proprietà <xref:System.Windows.Forms.DataGrid.BackColor%2A> e <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> determinano il colore delle righe nella griglia, la proprietà <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> determina il colore dell'area senza righe, che è visibile solo quando la griglia viene spostata in basso o se nella griglia sono contenute solo poche righe.</span><span class="sxs-lookup"><span data-stu-id="ea029-121">Whereas the <xref:System.Windows.Forms.DataGrid.BackColor%2A> and <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> properties determines the color of rows in the grid, the <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> property determines the color of the nonrow area, which is only visible when the grid is scrolled to the bottom, or if only a few rows are contained in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|<span data-ttu-id="ea029-122">Stile del bordo della griglia, uno dei valori di enumerazione <xref:System.Windows.Forms.BorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="ea029-122">The grid's border style, one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|<span data-ttu-id="ea029-123">Colore di sfondo della didascalia della finestra della griglia visualizzata immediatamente sopra la griglia.</span><span class="sxs-lookup"><span data-stu-id="ea029-123">The background color of the grid's window caption which appears immediately above the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|<span data-ttu-id="ea029-124">Il tipo di carattere della didascalia nella parte superiore della griglia.</span><span class="sxs-lookup"><span data-stu-id="ea029-124">The font of the caption at the top of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|<span data-ttu-id="ea029-125">Colore di sfondo della didascalia della finestra della griglia.</span><span class="sxs-lookup"><span data-stu-id="ea029-125">The background color of the grid's window caption.</span></span>|  
    |<xref:System.Windows.Forms.Control.Font%2A>|<span data-ttu-id="ea029-126">Tipo di carattere utilizzato per visualizzare il testo nella griglia.</span><span class="sxs-lookup"><span data-stu-id="ea029-126">The font used to display the text in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|<span data-ttu-id="ea029-127">Colore del tipo di carattere visualizzato dai dati nelle righe della griglia dei dati.</span><span class="sxs-lookup"><span data-stu-id="ea029-127">The color of the font displayed by the data in the rows of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|<span data-ttu-id="ea029-128">Colore delle linee della griglia dei dati.</span><span class="sxs-lookup"><span data-stu-id="ea029-128">The color of the grid lines of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|<span data-ttu-id="ea029-129">Stile delle linee che separano le celle della griglia, uno dei valori di enumerazione <xref:System.Windows.Forms.DataGridLineStyle>.</span><span class="sxs-lookup"><span data-stu-id="ea029-129">The style of the lines separating the cells of the grid, one of the <xref:System.Windows.Forms.DataGridLineStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|<span data-ttu-id="ea029-130">Colore di sfondo delle intestazioni di riga e colonna.</span><span class="sxs-lookup"><span data-stu-id="ea029-130">The background color of row and column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|<span data-ttu-id="ea029-131">Tipo di carattere utilizzato per le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="ea029-131">The font used for the column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|<span data-ttu-id="ea029-132">Colore di primo piano delle intestazioni di colonna della griglia, compresi il testo dell'intestazione di colonna e i glifi più/meno (per espandere le righe quando vengono visualizzate più tabelle correlate).</span><span class="sxs-lookup"><span data-stu-id="ea029-132">The foreground color of the grid's column headers, including the column header text and the plus/minus glyphs (to expand rows when multiple related tables are displayed).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|<span data-ttu-id="ea029-133">Colore del testo di tutti i collegamenti nella griglia dati, inclusi i collegamenti alle tabelle figlio, il nome della relazione e così via.</span><span class="sxs-lookup"><span data-stu-id="ea029-133">The color of text of all the links in the data grid, including links to child tables, the relation name, and so on.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|<span data-ttu-id="ea029-134">In una tabella figlio si tratta del colore di sfondo delle righe padre.</span><span class="sxs-lookup"><span data-stu-id="ea029-134">In a child table, this is the background color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|<span data-ttu-id="ea029-135">In una tabella figlio si tratta del colore di primo piano delle righe padre.</span><span class="sxs-lookup"><span data-stu-id="ea029-135">In a child table, this is the foreground color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|<span data-ttu-id="ea029-136">Determina se i nomi della tabella e della colonna vengono visualizzati nella riga padre, per mezzo dell'enumerazione <xref:System.Windows.Forms.DataGridParentRowsLabelStyle>.</span><span class="sxs-lookup"><span data-stu-id="ea029-136">Determines whether the table and column names are displayed in the parent row, by means of the <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumeration.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|<span data-ttu-id="ea029-137">Larghezza predefinita (in pixel) delle colonne della griglia.</span><span class="sxs-lookup"><span data-stu-id="ea029-137">The default width (in pixels) of columns in the grid.</span></span> <span data-ttu-id="ea029-138">Impostare questa proprietà prima di reimpostare le proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A>, separatamente o tramite il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>, oppure la proprietà non avrà alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="ea029-138">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="ea029-139">La proprietà non può essere impostata su un valore minore di 0.</span><span class="sxs-lookup"><span data-stu-id="ea029-139">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|<span data-ttu-id="ea029-140">Altezza della riga, in pixel, delle righe della griglia.</span><span class="sxs-lookup"><span data-stu-id="ea029-140">The row height (in pixels) of rows in the grid.</span></span> <span data-ttu-id="ea029-141">Impostare questa proprietà prima di reimpostare le proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A>, separatamente o tramite il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>, oppure la proprietà non avrà alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="ea029-141">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="ea029-142">La proprietà non può essere impostata su un valore minore di 0.</span><span class="sxs-lookup"><span data-stu-id="ea029-142">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|<span data-ttu-id="ea029-143">Larghezza delle intestazioni di riga della griglia.</span><span class="sxs-lookup"><span data-stu-id="ea029-143">The width of the row headers of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|<span data-ttu-id="ea029-144">Quando si seleziona una riga o una cella, si tratta del colore di sfondo.</span><span class="sxs-lookup"><span data-stu-id="ea029-144">When a row or cell is selected, this is the background color.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|<span data-ttu-id="ea029-145">Quando si seleziona una riga o una cella, questo è il colore di primo piano.</span><span class="sxs-lookup"><span data-stu-id="ea029-145">When a row or cell is selected, this is the foreground color.</span></span>|  
  
    > [!NOTE]
    > <span data-ttu-id="ea029-146">Tenere presente che, quando si personalizzano i colori dei controlli, è possibile rendere il controllo inaccessibile, a causa di una scelta di colori insufficiente (ad esempio, rosso e verde).</span><span class="sxs-lookup"><span data-stu-id="ea029-146">Keep in mind, when customizing the colors of controls, that it is possible to make the control inaccessible, due to poor color choice (for example, red and green).</span></span> <span data-ttu-id="ea029-147">Usare i colori disponibili nella tavolozza **colori di sistema** per evitare questo problema.</span><span class="sxs-lookup"><span data-stu-id="ea029-147">Use the colors available on the **System Colors** palette to avoid this issue.</span></span>  
  
     <span data-ttu-id="ea029-148">Nelle procedure riportate di seguito si presuppone che il form disponga di un controllo <xref:System.Windows.Forms.DataGrid> associato a una tabella di dati.</span><span class="sxs-lookup"><span data-stu-id="ea029-148">The following procedures assume your form has a <xref:System.Windows.Forms.DataGrid> control bound to a data table.</span></span> <span data-ttu-id="ea029-149">Per ulteriori informazioni, vedere [associazione del controllo Windows Forms DataGrid a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="ea029-149">For more information, see [Binding the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a><span data-ttu-id="ea029-150">Per impostare lo stile della tabella e della colonna di una tabella dati a livello di codice</span><span class="sxs-lookup"><span data-stu-id="ea029-150">To set the table and column style of a data table programmatically</span></span>  
  
1. <span data-ttu-id="ea029-151">Creare un nuovo stile di tabella e impostarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="ea029-151">Create a new table style and set its properties.</span></span>  
  
2. <span data-ttu-id="ea029-152">Creare uno stile colonna e impostarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="ea029-152">Create a column style and set its properties.</span></span>  
  
3. <span data-ttu-id="ea029-153">Aggiungere lo stile della colonna alla raccolta di stili di colonna dello stile della tabella.</span><span class="sxs-lookup"><span data-stu-id="ea029-153">Add the column style to the table style's column styles collection.</span></span>  
  
4. <span data-ttu-id="ea029-154">Aggiungere lo stile della tabella alla raccolta di stili di tabella della griglia dati.</span><span class="sxs-lookup"><span data-stu-id="ea029-154">Add the table style to the data grid's table styles collection.</span></span>  
  
5. <span data-ttu-id="ea029-155">Nell'esempio seguente, creare un'istanza di un nuovo <xref:System.Windows.Forms.DataGridTableStyle> e impostare la relativa proprietà <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>.</span><span class="sxs-lookup"><span data-stu-id="ea029-155">In the example below, create an instance of a new <xref:System.Windows.Forms.DataGridTableStyle> and set its <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property.</span></span>  
  
6. <span data-ttu-id="ea029-156">Creare una nuova istanza di un oggetto **GridColumnStyle** e impostarne il **MappingName** (e altre proprietà di layout e visualizzazione).</span><span class="sxs-lookup"><span data-stu-id="ea029-156">Create a new instance of a **GridColumnStyle** and set its **MappingName** (and some other layout and display properties).</span></span>  
  
7. <span data-ttu-id="ea029-157">Ripetere i passaggi da 2 a 6 per ogni stile di colonna che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="ea029-157">Repeat steps 2 through 6 for each column style you want to create.</span></span>  
  
     <span data-ttu-id="ea029-158">Nell'esempio seguente viene illustrato il modo in cui viene creata una <xref:System.Windows.Forms.DataGridTextBoxColumn>, perché nella colonna deve essere visualizzato un nome.</span><span class="sxs-lookup"><span data-stu-id="ea029-158">The following example illustrates how a <xref:System.Windows.Forms.DataGridTextBoxColumn> is created, because a name is to be displayed in the column.</span></span> <span data-ttu-id="ea029-159">Inoltre, lo stile della colonna viene aggiunto al <xref:System.Windows.Forms.GridColumnStylesCollection> dello stile della tabella e lo stile della tabella viene aggiunto al <xref:System.Windows.Forms.GridTableStylesCollection> della griglia dei dati.</span><span class="sxs-lookup"><span data-stu-id="ea029-159">Additionally, you add the column style to the <xref:System.Windows.Forms.GridColumnStylesCollection> of the table style, and you add the table style to the <xref:System.Windows.Forms.GridTableStylesCollection> of the data grid.</span></span>  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName   
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName   
       ' to the name of a DataColumn in the DataTable.   
       ' Set the HeaderText and Width properties.   
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to   
       ' the GridTableStylesCollection.   
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName   
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName   
       // to the name of a DataColumn in the DataTable.   
       // Set the HeaderText and Width properties.   
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to   
       // the GridTableStylesCollection.   
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName   
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName   
          // to the name of a DataColumn in the DataTable.   
          // Set the HeaderText and Width properties.   
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to   
          // the GridTableStylesCollection.   
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ea029-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea029-160">See also</span></span>

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [<span data-ttu-id="ea029-161">Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="ea029-161">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="ea029-162">Controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="ea029-162">DataGrid Control</span></span>](datagrid-control-windows-forms.md)

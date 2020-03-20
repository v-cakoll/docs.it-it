---
title: Format DataGrid (controllo)
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
ms.openlocfilehash: 180f837c7d60f49af880faefc05da262be061d12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182141"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a><span data-ttu-id="e8b5b-102">Procedura: formattare il controllo DataGrid di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e8b5b-102">How to: Format the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="e8b5b-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="e8b5b-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="e8b5b-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="e8b5b-105">L'applicazione di colori diversi <xref:System.Windows.Forms.DataGrid> a varie parti di un controllo può contribuire a semplificare la lettura e l'interpretazione delle informazioni in esso contenute.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-105">Applying different colors to various parts of a <xref:System.Windows.Forms.DataGrid> control can help to make the information in it easier to read and interpret.</span></span> <span data-ttu-id="e8b5b-106">Il colore può essere applicato a righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-106">Color can be applied to rows and columns.</span></span> <span data-ttu-id="e8b5b-107">Righe e colonne possono anche essere nascoste o visualizzate a propria discrezione.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-107">Rows and columns can also be hidden or shown at your discretion.</span></span>  
  
 <span data-ttu-id="e8b5b-108">Esistono tre aspetti di base <xref:System.Windows.Forms.DataGrid> della formattazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-108">There are three basic aspects of formatting the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="e8b5b-109">È possibile impostare le proprietà per stabilire uno stile di default in cui vengono visualizzati i dati.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-109">You can set properties to establish a default style in which data is displayed.</span></span> <span data-ttu-id="e8b5b-110">Da tale base, è quindi possibile personalizzare la modalità di visualizzazione di determinate tabelle in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-110">From that base, you can then customize the way certain tables are displayed at run time.</span></span> <span data-ttu-id="e8b5b-111">Infine, è possibile modificare le colonne visualizzate nella griglia dei dati, nonché i colori e altre formattazioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-111">Finally, you can modify which columns are displayed in the data grid as well as the colors and other formatting that is shown.</span></span>  
  
 <span data-ttu-id="e8b5b-112">Come passaggio iniziale nella formattazione di una <xref:System.Windows.Forms.DataGrid> griglia di dati, è possibile impostare le proprietà della stessa.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-112">As an initial step in formatting a data grid, you can set the properties of the <xref:System.Windows.Forms.DataGrid> itself.</span></span> <span data-ttu-id="e8b5b-113">Queste scelte di colore e formato costituiscono una base da cui è quindi possibile apportare modifiche a seconda delle tabelle dati e delle colonne visualizzate.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-113">These color and format choices form a base from which you can then make changes depending on the data tables and columns displayed.</span></span>  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a><span data-ttu-id="e8b5b-114">Per stabilire uno stile predefinito per il controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="e8b5b-114">To establish a default style for the DataGrid control</span></span>  
  
1. <span data-ttu-id="e8b5b-115">Impostare le seguenti proprietà in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="e8b5b-115">Set the following properties as appropriate:</span></span>  
  
    |<span data-ttu-id="e8b5b-116">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e8b5b-116">Property</span></span>|<span data-ttu-id="e8b5b-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8b5b-117">Description</span></span>|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<span data-ttu-id="e8b5b-118">La <xref:System.Windows.Forms.DataGrid.BackColor%2A> proprietà definisce il colore delle righe pari della griglia.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-118">The <xref:System.Windows.Forms.DataGrid.BackColor%2A> property defines the color of the even-numbered rows of the grid.</span></span> <span data-ttu-id="e8b5b-119">Quando si <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> imposta la proprietà su un colore diverso, ogni altra riga viene impostata su questo nuovo colore (righe 1, 3, 5 e così via).</span><span class="sxs-lookup"><span data-stu-id="e8b5b-119">When you set the <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> property to a different color, every other row is set to this new color (rows 1, 3, 5, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|<span data-ttu-id="e8b5b-120">Colore di sfondo delle righe pari della griglia (righe 0, 2, 4, 6 e così via).</span><span class="sxs-lookup"><span data-stu-id="e8b5b-120">The background color of the even-numbered rows of the grid (rows 0, 2, 4, 6, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|<span data-ttu-id="e8b5b-121">Mentre <xref:System.Windows.Forms.DataGrid.BackColor%2A> le <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> proprietà e determinano il colore <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> delle righe nella griglia, la proprietà determina il colore dell'area non riga, visibile solo quando si scorre la griglia verso il basso o se nella griglia sono contenute solo poche righe.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-121">Whereas the <xref:System.Windows.Forms.DataGrid.BackColor%2A> and <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> properties determines the color of rows in the grid, the <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> property determines the color of the nonrow area, which is only visible when the grid is scrolled to the bottom, or if only a few rows are contained in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|<span data-ttu-id="e8b5b-122">Stile del bordo della griglia, <xref:System.Windows.Forms.BorderStyle> uno dei valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-122">The grid's border style, one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|<span data-ttu-id="e8b5b-123">Colore di sfondo della didascalia della finestra della griglia che appare immediatamente sopra la griglia.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-123">The background color of the grid's window caption which appears immediately above the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|<span data-ttu-id="e8b5b-124">Tipo di carattere della didascalia nella parte superiore della griglia.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-124">The font of the caption at the top of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|<span data-ttu-id="e8b5b-125">Colore di sfondo della didascalia della finestra della griglia.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-125">The background color of the grid's window caption.</span></span>|  
    |<xref:System.Windows.Forms.Control.Font%2A>|<span data-ttu-id="e8b5b-126">Tipo di carattere utilizzato per visualizzare il testo nella griglia.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-126">The font used to display the text in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|<span data-ttu-id="e8b5b-127">Colore del tipo di carattere visualizzato dai dati nelle righe della griglia dei dati.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-127">The color of the font displayed by the data in the rows of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|<span data-ttu-id="e8b5b-128">Colore delle linee della griglia della griglia di dati.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-128">The color of the grid lines of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|<span data-ttu-id="e8b5b-129">Stile delle linee che separano le celle della <xref:System.Windows.Forms.DataGridLineStyle> griglia, uno dei valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-129">The style of the lines separating the cells of the grid, one of the <xref:System.Windows.Forms.DataGridLineStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|<span data-ttu-id="e8b5b-130">Colore di sfondo delle intestazioni di riga e di colonna.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-130">The background color of row and column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|<span data-ttu-id="e8b5b-131">Tipo di carattere utilizzato per le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-131">The font used for the column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|<span data-ttu-id="e8b5b-132">Colore di primo piano delle intestazioni di colonna della griglia, inclusi il testo dell'intestazione di colonna e i glifi più/meno (per espandere le righe quando vengono visualizzate più tabelle correlate).</span><span class="sxs-lookup"><span data-stu-id="e8b5b-132">The foreground color of the grid's column headers, including the column header text and the plus/minus glyphs (to expand rows when multiple related tables are displayed).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|<span data-ttu-id="e8b5b-133">Colore del testo di tutti i collegamenti nella griglia dei dati, inclusi i collegamenti alle tabelle figlio, il nome della relazione e così via.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-133">The color of text of all the links in the data grid, including links to child tables, the relation name, and so on.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|<span data-ttu-id="e8b5b-134">In una tabella figlio, questo è il colore di sfondo delle righe padre.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-134">In a child table, this is the background color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|<span data-ttu-id="e8b5b-135">In una tabella figlio, questo è il colore di primo piano delle righe padre.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-135">In a child table, this is the foreground color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|<span data-ttu-id="e8b5b-136">Determina se i nomi di tabella e colonna vengono visualizzati nella riga padre, tramite l'enumerazione <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> .</span><span class="sxs-lookup"><span data-stu-id="e8b5b-136">Determines whether the table and column names are displayed in the parent row, by means of the <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumeration.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|<span data-ttu-id="e8b5b-137">Larghezza predefinita (in pixel) delle colonne della griglia.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-137">The default width (in pixels) of columns in the grid.</span></span> <span data-ttu-id="e8b5b-138">Impostare questa proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> prima <xref:System.Windows.Forms.DataGrid.DataMember%2A> di reimpostare le <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> proprietà e (separatamente o tramite il metodo ) o la proprietà non avrà alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-138">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="e8b5b-139">La proprietà non può essere impostata su un valore minore di 0.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-139">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|<span data-ttu-id="e8b5b-140">Altezza delle righe (in pixel) delle righe nella griglia.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-140">The row height (in pixels) of rows in the grid.</span></span> <span data-ttu-id="e8b5b-141">Impostare questa proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> prima <xref:System.Windows.Forms.DataGrid.DataMember%2A> di reimpostare le <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> proprietà e (separatamente o tramite il metodo ) o la proprietà non avrà alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-141">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="e8b5b-142">La proprietà non può essere impostata su un valore minore di 0.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-142">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|<span data-ttu-id="e8b5b-143">Larghezza delle intestazioni di riga della griglia.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-143">The width of the row headers of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|<span data-ttu-id="e8b5b-144">Quando si seleziona una riga o una cella, questo è il colore di sfondo.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-144">When a row or cell is selected, this is the background color.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|<span data-ttu-id="e8b5b-145">Quando si seleziona una riga o una cella, questo è il colore di primo piano.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-145">When a row or cell is selected, this is the foreground color.</span></span>|  
  
    > [!NOTE]
    > <span data-ttu-id="e8b5b-146">Tenere presente che quando si personalizzano i colori dei controlli è possibile rendere il controllo inaccessibile, a causa della scarsa scelta del colore (ad esempio, rosso e verde).</span><span class="sxs-lookup"><span data-stu-id="e8b5b-146">Keep in mind, when customizing the colors of controls, that it is possible to make the control inaccessible, due to poor color choice (for example, red and green).</span></span> <span data-ttu-id="e8b5b-147">Utilizzare i colori disponibili nella tavolozza **Colori** di sistema per evitare questo problema.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-147">Use the colors available on the **System Colors** palette to avoid this issue.</span></span>  
  
     <span data-ttu-id="e8b5b-148">Nelle procedure seguenti si <xref:System.Windows.Forms.DataGrid> presuppone che il form disponga di un controllo associato a una tabella dati.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-148">The following procedures assume your form has a <xref:System.Windows.Forms.DataGrid> control bound to a data table.</span></span> <span data-ttu-id="e8b5b-149">Per ulteriori informazioni, vedere [Associazione del controllo DataGrid Windows Form a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="e8b5b-149">For more information, see [Binding the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a><span data-ttu-id="e8b5b-150">Per impostare lo stile di tabella e colonna di una tabella dati a livello di codiceTo set the table and column style of a data table programmatically</span><span class="sxs-lookup"><span data-stu-id="e8b5b-150">To set the table and column style of a data table programmatically</span></span>  
  
1. <span data-ttu-id="e8b5b-151">Creare un nuovo stile di tabella e impostarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-151">Create a new table style and set its properties.</span></span>  
  
2. <span data-ttu-id="e8b5b-152">Creare uno stile di colonna e impostarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-152">Create a column style and set its properties.</span></span>  
  
3. <span data-ttu-id="e8b5b-153">Aggiungere lo stile di colonna alla raccolta di stili di colonna dello stile di tabella.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-153">Add the column style to the table style's column styles collection.</span></span>  
  
4. <span data-ttu-id="e8b5b-154">Aggiungere lo stile di tabella all'insieme di stili di tabella della griglia dei dati.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-154">Add the table style to the data grid's table styles collection.</span></span>  
  
5. <span data-ttu-id="e8b5b-155">Nell'esempio seguente, creare un'istanza di un nuovo <xref:System.Windows.Forms.DataGridTableStyle> e impostarne la <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-155">In the example below, create an instance of a new <xref:System.Windows.Forms.DataGridTableStyle> and set its <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property.</span></span>  
  
6. <span data-ttu-id="e8b5b-156">Creare una nuova istanza di un **GridColumnStyle** e impostarne **il MappingName** (e alcune altre proprietà di layout e visualizzazione).</span><span class="sxs-lookup"><span data-stu-id="e8b5b-156">Create a new instance of a **GridColumnStyle** and set its **MappingName** (and some other layout and display properties).</span></span>  
  
7. <span data-ttu-id="e8b5b-157">Ripetere i passaggi da 2 a 6 per ogni stile di colonna che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-157">Repeat steps 2 through 6 for each column style you want to create.</span></span>  
  
     <span data-ttu-id="e8b5b-158">Nell'esempio seguente viene <xref:System.Windows.Forms.DataGridTextBoxColumn> illustrato come viene creato un oggetto, perché un nome deve essere visualizzato nella colonna.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-158">The following example illustrates how a <xref:System.Windows.Forms.DataGridTextBoxColumn> is created, because a name is to be displayed in the column.</span></span> <span data-ttu-id="e8b5b-159">Inoltre, aggiungere lo stile di <xref:System.Windows.Forms.GridColumnStylesCollection> colonna per lo stile di tabella <xref:System.Windows.Forms.GridTableStylesCollection> e aggiungere lo stile di tabella per la griglia dei dati.</span><span class="sxs-lookup"><span data-stu-id="e8b5b-159">Additionally, you add the column style to the <xref:System.Windows.Forms.GridColumnStylesCollection> of the table style, and you add the table style to the <xref:System.Windows.Forms.GridTableStylesCollection> of the data grid.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e8b5b-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8b5b-160">See also</span></span>

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [<span data-ttu-id="e8b5b-161">Procedura: eliminare o nascondere colonne nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="e8b5b-161">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="e8b5b-162">Controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="e8b5b-162">DataGrid Control</span></span>](datagrid-control-windows-forms.md)

---
title: 'Procedura: Accedere agli oggetti in un elenco a discesa DataGridViewComboBoxCell di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 17b7c93effe9338a9e2d6cb207a948a956d9b666
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59334276"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a><span data-ttu-id="80da0-102">Procedura: Accedere agli oggetti in un elenco a discesa DataGridViewComboBoxCell di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80da0-102">How to: Access Objects in a Windows Forms DataGridViewComboBoxCell Drop-Down List</span></span>
<span data-ttu-id="80da0-103">Ad esempio la <xref:System.Windows.Forms.ComboBox> (controllo), il <xref:System.Windows.Forms.DataGridViewComboBoxColumn> e <xref:System.Windows.Forms.DataGridViewComboBoxCell> tipi consentono di aggiungere oggetti arbitrari agli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="80da0-103">Like the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and <xref:System.Windows.Forms.DataGridViewComboBoxCell> types enable you to add arbitrary objects to their drop-down lists.</span></span> <span data-ttu-id="80da0-104">Con questa funzionalità, è possibile rappresentare gli stati complessi in un elenco a discesa senza la necessità di archiviare oggetti corrispondenti in una raccolta separata.</span><span class="sxs-lookup"><span data-stu-id="80da0-104">With this feature, you can represent complex states in a drop-down list without having to store corresponding objects in a separate collection.</span></span>  
  
 <span data-ttu-id="80da0-105">A differenza di <xref:System.Windows.Forms.ComboBox> (controllo), il <xref:System.Windows.Forms.DataGridView> tipi non è un <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> proprietà per il recupero dell'oggetto attualmente selezionato.</span><span class="sxs-lookup"><span data-stu-id="80da0-105">Unlike the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridView> types do not have a <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> property for retrieving the currently selected object.</span></span> <span data-ttu-id="80da0-106">In alternativa, è necessario impostare il <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> proprietà sul nome di una proprietà nell'oggetto business.</span><span class="sxs-lookup"><span data-stu-id="80da0-106">Instead, you must set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> property to the name of a property on your business object.</span></span> <span data-ttu-id="80da0-107">Quando l'utente effettua una selezione, la proprietà indicata dell'oggetto business imposta la cella <xref:System.Windows.Forms.DataGridViewCell.Value%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="80da0-107">When the user makes a selection, the indicated property of the business object sets the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
 <span data-ttu-id="80da0-108">Per recuperare l'oggetto business tramite il valore della cella, il `ValueMember` proprietà deve indicare una proprietà che restituisce un riferimento all'oggetto di business stesso.</span><span class="sxs-lookup"><span data-stu-id="80da0-108">To retrieve the business object through the cell value, the `ValueMember` property must indicate a property that returns a reference to the business object itself.</span></span> <span data-ttu-id="80da0-109">Pertanto, se il tipo dell'oggetto business non controllati dall'utente, è necessario aggiungere questo tipo di proprietà dall'estensione del tipo tramite l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="80da0-109">Therefore, if the type of the business object is not under your control, you must add such a property by extending the type through inheritance.</span></span>  
  
 <span data-ttu-id="80da0-110">Le procedure seguenti illustrano come compilare un elenco a discesa con gli oggetti business e recuperare gli oggetti tramite la cella <xref:System.Windows.Forms.DataGridViewCell.Value%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="80da0-110">The following procedures demonstrate how to populate a drop-down list with business objects and retrieve the objects through the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a><span data-ttu-id="80da0-111">Per aggiungere gli oggetti business per l'elenco a discesa</span><span class="sxs-lookup"><span data-stu-id="80da0-111">To add business objects to the drop-down list</span></span>  
  
1. <span data-ttu-id="80da0-112">Creare una nuova <xref:System.Windows.Forms.DataGridViewComboBoxColumn> e popolare il <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="80da0-112">Create a new <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and populate its <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> collection.</span></span> <span data-ttu-id="80da0-113">In alternativa, è possibile impostare la colonna <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> proprietà alla raccolta di oggetti business.</span><span class="sxs-lookup"><span data-stu-id="80da0-113">Alternatively, you can set the column <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property to the collection of business objects.</span></span> <span data-ttu-id="80da0-114">In tal caso, tuttavia, non è possibile aggiungere "non assegnati" per l'elenco a discesa senza creare un oggetto business corrispondente nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="80da0-114">In that case, however, you cannot add "unassigned" to the drop-down list without creating a corresponding business object in your collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. <span data-ttu-id="80da0-115">Impostare le proprietà <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> e <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>.</span><span class="sxs-lookup"><span data-stu-id="80da0-115">Set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> and <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> properties.</span></span> <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> <span data-ttu-id="80da0-116">indica la proprietà dell'oggetto business da visualizzare nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="80da0-116">indicates the property of the business object to display in the drop-down list.</span></span> <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> <span data-ttu-id="80da0-117">indica la proprietà che restituisce un riferimento all'oggetto business.</span><span class="sxs-lookup"><span data-stu-id="80da0-117">indicates the property that returns a reference to the business object.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. <span data-ttu-id="80da0-118">Assicurarsi che il tipo di oggetto business contiene una proprietà che restituisce un riferimento all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="80da0-118">Make sure that your business object type contains a property that returns a reference to the current instance.</span></span> <span data-ttu-id="80da0-119">Questa proprietà deve essere denominata con il valore assegnato a <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="80da0-119">This property must be named with the value assigned to <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> in the previous step.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a><span data-ttu-id="80da0-120">Per recuperare l'oggetto business attualmente selezionata</span><span class="sxs-lookup"><span data-stu-id="80da0-120">To retrieve the currently selected business object</span></span>  
  
-   <span data-ttu-id="80da0-121">Ottiene la cella <xref:System.Windows.Forms.DataGridViewCell.Value%2A> proprietà ed eseguirne il cast al tipo di oggetto business.</span><span class="sxs-lookup"><span data-stu-id="80da0-121">Get the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property and cast it to the business object type.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a><span data-ttu-id="80da0-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="80da0-122">Example</span></span>  
 <span data-ttu-id="80da0-123">L'esempio completo viene illustrato l'utilizzo di oggetti business in un elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="80da0-123">The complete example demonstrates the use of business objects in a drop-down list.</span></span> <span data-ttu-id="80da0-124">Nell'esempio, un <xref:System.Windows.Forms.DataGridView> è associato a una raccolta di `Task` oggetti.</span><span class="sxs-lookup"><span data-stu-id="80da0-124">In the example, a <xref:System.Windows.Forms.DataGridView> control is bound to a collection of `Task` objects.</span></span> <span data-ttu-id="80da0-125">Ciascuna `Task` oggetto ha un `AssignedTo` proprietà che indica il `Employee` oggetto attualmente assegnato a tale attività.</span><span class="sxs-lookup"><span data-stu-id="80da0-125">Each `Task` object has an `AssignedTo` property that indicates the `Employee` object currently assigned to that task.</span></span> <span data-ttu-id="80da0-126">Il `Assigned To` colonna vengono visualizzati la `Name` valore della proprietà per ogni dipendente assegnato, o "non assegnati" se il `Task.AssignedTo` valore della proprietà è `null`.</span><span class="sxs-lookup"><span data-stu-id="80da0-126">The `Assigned To` column displays the `Name` property value for each assigned employee, or "unassigned" if the `Task.AssignedTo` property value is `null`.</span></span>  
  
 <span data-ttu-id="80da0-127">Per visualizzare il comportamento di questo esempio, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="80da0-127">To view the behavior of this example, perform the following steps:</span></span>  
  
1. <span data-ttu-id="80da0-128">Modificare le assegnazioni nel `Assigned To` colonna selezionando valori diversi dagli elenchi a discesa o premendo CTRL + 0 in una cella di casella combinata.</span><span class="sxs-lookup"><span data-stu-id="80da0-128">Change assignments in the `Assigned To` column by selecting different values from the drop-down lists or pressing CTRL+0 in a combo-box cell.</span></span>  
  
2. <span data-ttu-id="80da0-129">Fare clic su `Generate Report` per visualizzare le assegnazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="80da0-129">Click `Generate Report` to display the current assignments.</span></span> <span data-ttu-id="80da0-130">Ciò dimostra che una modifica nel `Assigned To` colonna Aggiorna automaticamente il `tasks` raccolta.</span><span class="sxs-lookup"><span data-stu-id="80da0-130">This demonstrates that a change in the `Assigned To` column automatically updates the `tasks` collection.</span></span>  
  
3. <span data-ttu-id="80da0-131">Fare clic su un `Request Status` il pulsante per chiamare il `RequestStatus` metodo dell'oggetto corrente `Employee` oggetto per la riga.</span><span class="sxs-lookup"><span data-stu-id="80da0-131">Click a `Request Status` button to call the `RequestStatus` method of the current `Employee` object for that row.</span></span> <span data-ttu-id="80da0-132">Ciò dimostra che l'oggetto selezionato è stato recuperato.</span><span class="sxs-lookup"><span data-stu-id="80da0-132">This demonstrates that the selected object has been successfully retrieved.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="80da0-133">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="80da0-133">Compiling the Code</span></span>  
 <span data-ttu-id="80da0-134">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="80da0-134">This example requires:</span></span>  
  
-   <span data-ttu-id="80da0-135">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="80da0-135">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80da0-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80da0-136">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ComboBox>
- [<span data-ttu-id="80da0-137">Visualizzazione di dati nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="80da0-137">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)

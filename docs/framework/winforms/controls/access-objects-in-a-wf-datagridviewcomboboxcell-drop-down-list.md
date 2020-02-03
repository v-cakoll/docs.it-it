---
title: Accedere agli oggetti nell'elenco a discesa DataGridViewComboBoxCell
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 7e76ab1ac9089778e4371f4ee65b06d5ebc570bf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746317"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a><span data-ttu-id="a0190-102">Procedura: accedere agli oggetti in un elenco a discesa DataGridViewComboBoxCell Windows Form</span><span class="sxs-lookup"><span data-stu-id="a0190-102">How to: Access Objects in a Windows Forms DataGridViewComboBoxCell Drop-Down List</span></span>
<span data-ttu-id="a0190-103">Analogamente al controllo <xref:System.Windows.Forms.ComboBox>, i tipi <xref:System.Windows.Forms.DataGridViewComboBoxColumn> e <xref:System.Windows.Forms.DataGridViewComboBoxCell> consentono di aggiungere oggetti arbitrari ai rispettivi elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="a0190-103">Like the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and <xref:System.Windows.Forms.DataGridViewComboBoxCell> types enable you to add arbitrary objects to their drop-down lists.</span></span> <span data-ttu-id="a0190-104">Con questa funzionalità è possibile rappresentare stati complessi in un elenco a discesa senza dover archiviare gli oggetti corrispondenti in una raccolta separata.</span><span class="sxs-lookup"><span data-stu-id="a0190-104">With this feature, you can represent complex states in a drop-down list without having to store corresponding objects in a separate collection.</span></span>  
  
 <span data-ttu-id="a0190-105">A differenza del controllo <xref:System.Windows.Forms.ComboBox>, i tipi di <xref:System.Windows.Forms.DataGridView> non dispongono di una proprietà <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> per il recupero dell'oggetto attualmente selezionato.</span><span class="sxs-lookup"><span data-stu-id="a0190-105">Unlike the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridView> types do not have a <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> property for retrieving the currently selected object.</span></span> <span data-ttu-id="a0190-106">Al contrario, è necessario impostare la proprietà <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> sul nome di una proprietà nell'oggetto business.</span><span class="sxs-lookup"><span data-stu-id="a0190-106">Instead, you must set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> property to the name of a property on your business object.</span></span> <span data-ttu-id="a0190-107">Quando l'utente effettua una selezione, la proprietà indicata dell'oggetto business imposta la cella <xref:System.Windows.Forms.DataGridViewCell.Value%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="a0190-107">When the user makes a selection, the indicated property of the business object sets the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
 <span data-ttu-id="a0190-108">Per recuperare l'oggetto business tramite il valore della cella, la proprietà `ValueMember` deve indicare una proprietà che restituisce un riferimento all'oggetto business stesso.</span><span class="sxs-lookup"><span data-stu-id="a0190-108">To retrieve the business object through the cell value, the `ValueMember` property must indicate a property that returns a reference to the business object itself.</span></span> <span data-ttu-id="a0190-109">Pertanto, se il tipo dell'oggetto business non è sotto il controllo, è necessario aggiungere tale proprietà estendendo il tipo mediante ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="a0190-109">Therefore, if the type of the business object is not under your control, you must add such a property by extending the type through inheritance.</span></span>  
  
 <span data-ttu-id="a0190-110">Nelle procedure riportate di seguito viene illustrato come popolare un elenco a discesa con oggetti business e come recuperare gli oggetti tramite la cella <xref:System.Windows.Forms.DataGridViewCell.Value%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="a0190-110">The following procedures demonstrate how to populate a drop-down list with business objects and retrieve the objects through the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a><span data-ttu-id="a0190-111">Per aggiungere oggetti business all'elenco a discesa</span><span class="sxs-lookup"><span data-stu-id="a0190-111">To add business objects to the drop-down list</span></span>  
  
1. <span data-ttu-id="a0190-112">Creare una nuova <xref:System.Windows.Forms.DataGridViewComboBoxColumn> e popolare la relativa raccolta di <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="a0190-112">Create a new <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and populate its <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> collection.</span></span> <span data-ttu-id="a0190-113">In alternativa, è possibile impostare la colonna <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> proprietà sulla raccolta di oggetti business.</span><span class="sxs-lookup"><span data-stu-id="a0190-113">Alternatively, you can set the column <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property to the collection of business objects.</span></span> <span data-ttu-id="a0190-114">In tal caso, tuttavia, non è possibile aggiungere "non assegnati" all'elenco a discesa senza creare un oggetto business corrispondente nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="a0190-114">In that case, however, you cannot add "unassigned" to the drop-down list without creating a corresponding business object in your collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. <span data-ttu-id="a0190-115">Impostare le proprietà <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> e <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>.</span><span class="sxs-lookup"><span data-stu-id="a0190-115">Set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> and <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> properties.</span></span> <span data-ttu-id="a0190-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indica la proprietà dell'oggetto business da visualizzare nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="a0190-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indicates the property of the business object to display in the drop-down list.</span></span> <span data-ttu-id="a0190-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indica la proprietà che restituisce un riferimento all'oggetto business.</span><span class="sxs-lookup"><span data-stu-id="a0190-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indicates the property that returns a reference to the business object.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. <span data-ttu-id="a0190-118">Verificare che il tipo di oggetto business contenga una proprietà che restituisce un riferimento all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="a0190-118">Make sure that your business object type contains a property that returns a reference to the current instance.</span></span> <span data-ttu-id="a0190-119">Questa proprietà deve essere denominata con il valore assegnato a <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="a0190-119">This property must be named with the value assigned to <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> in the previous step.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a><span data-ttu-id="a0190-120">Per recuperare l'oggetto business attualmente selezionato</span><span class="sxs-lookup"><span data-stu-id="a0190-120">To retrieve the currently selected business object</span></span>  
  
- <span data-ttu-id="a0190-121">Ottenere la cella <xref:System.Windows.Forms.DataGridViewCell.Value%2A> proprietà ed eseguirne il cast al tipo di oggetto business.</span><span class="sxs-lookup"><span data-stu-id="a0190-121">Get the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property and cast it to the business object type.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a><span data-ttu-id="a0190-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="a0190-122">Example</span></span>  
 <span data-ttu-id="a0190-123">Nell'esempio completo viene illustrato l'utilizzo di oggetti business in un elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="a0190-123">The complete example demonstrates the use of business objects in a drop-down list.</span></span> <span data-ttu-id="a0190-124">Nell'esempio un controllo <xref:System.Windows.Forms.DataGridView> viene associato a una raccolta di oggetti `Task`.</span><span class="sxs-lookup"><span data-stu-id="a0190-124">In the example, a <xref:System.Windows.Forms.DataGridView> control is bound to a collection of `Task` objects.</span></span> <span data-ttu-id="a0190-125">Ogni oggetto `Task` dispone di una proprietà `AssignedTo` che indica l'oggetto `Employee` attualmente assegnato a tale attività.</span><span class="sxs-lookup"><span data-stu-id="a0190-125">Each `Task` object has an `AssignedTo` property that indicates the `Employee` object currently assigned to that task.</span></span> <span data-ttu-id="a0190-126">Nella colonna `Assigned To` viene visualizzato il valore della proprietà `Name` per ogni dipendente assegnato o "non assegnato" Se il valore della proprietà `Task.AssignedTo` è `null`.</span><span class="sxs-lookup"><span data-stu-id="a0190-126">The `Assigned To` column displays the `Name` property value for each assigned employee, or "unassigned" if the `Task.AssignedTo` property value is `null`.</span></span>  
  
 <span data-ttu-id="a0190-127">Per visualizzare il comportamento di questo esempio, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="a0190-127">To view the behavior of this example, perform the following steps:</span></span>  
  
1. <span data-ttu-id="a0190-128">Modificare le assegnazioni nella colonna `Assigned To` selezionando valori diversi dall'elenco a discesa o premendo CTRL + 0 in una cella della casella combinata.</span><span class="sxs-lookup"><span data-stu-id="a0190-128">Change assignments in the `Assigned To` column by selecting different values from the drop-down lists or pressing CTRL+0 in a combo-box cell.</span></span>  
  
2. <span data-ttu-id="a0190-129">Fare clic su `Generate Report` per visualizzare le assegnazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="a0190-129">Click `Generate Report` to display the current assignments.</span></span> <span data-ttu-id="a0190-130">Ciò dimostra che una modifica nella colonna `Assigned To` aggiorna automaticamente la raccolta di `tasks`.</span><span class="sxs-lookup"><span data-stu-id="a0190-130">This demonstrates that a change in the `Assigned To` column automatically updates the `tasks` collection.</span></span>  
  
3. <span data-ttu-id="a0190-131">Fare clic su un pulsante `Request Status` per chiamare il metodo `RequestStatus` dell'oggetto `Employee` corrente per la riga.</span><span class="sxs-lookup"><span data-stu-id="a0190-131">Click a `Request Status` button to call the `RequestStatus` method of the current `Employee` object for that row.</span></span> <span data-ttu-id="a0190-132">Ciò dimostra che l'oggetto selezionato è stato recuperato correttamente.</span><span class="sxs-lookup"><span data-stu-id="a0190-132">This demonstrates that the selected object has been successfully retrieved.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a0190-133">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a0190-133">Compiling the Code</span></span>  
 <span data-ttu-id="a0190-134">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0190-134">This example requires:</span></span>  
  
- <span data-ttu-id="a0190-135">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="a0190-135">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0190-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0190-136">See also</span></span>

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
- [<span data-ttu-id="a0190-137">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a0190-137">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)

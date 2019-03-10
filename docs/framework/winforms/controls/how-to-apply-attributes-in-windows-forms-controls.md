---
title: 'Procedura: Applicare attributi nei controlli di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: fd41999b1cd1cde940d182f3acc505bbb92a3aa4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718545"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="8e67d-102">Procedura: Applicare attributi nei controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8e67d-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="8e67d-103">Per lo sviluppo di componenti e controlli che interagiscano correttamente con l'ambiente di progettazione ed eseguito correttamente in fase di esecuzione, è necessario applicare correttamente gli attributi alle classi e membri.</span><span class="sxs-lookup"><span data-stu-id="8e67d-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e67d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8e67d-104">Example</span></span>  
 <span data-ttu-id="8e67d-105">Esempio di codice seguente viene illustrato come usare alcuni attributi in un controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8e67d-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="8e67d-106">Il controllo illustra una funzionalità di registrazione semplice.</span><span class="sxs-lookup"><span data-stu-id="8e67d-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="8e67d-107">Quando il controllo è associato a un'origine dati, vengono visualizzati i valori inviati dall'origine dei dati in un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="8e67d-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="8e67d-108">Se un valore supera il valore specificato per il `Threshold` proprietà, un `ThresholdExceeded` viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="8e67d-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="8e67d-109">Il `AttributesDemoControl` registra i valori con un `LogEntry` classe.</span><span class="sxs-lookup"><span data-stu-id="8e67d-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="8e67d-110">Il `LogEntry` è una classe modello, ovvero con i parametri nel tipo che si connette.</span><span class="sxs-lookup"><span data-stu-id="8e67d-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="8e67d-111">Ad esempio, se il `AttributesDemoControl` registra valori di tipo `float`, ognuna `LogEntry` istanza viene dichiarata e usata come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8e67d-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="8e67d-112">Poiché `LogEntry` con i parametri per un tipo arbitrario, deve usare la reflection per funzionare con il tipo di parametro.</span><span class="sxs-lookup"><span data-stu-id="8e67d-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="8e67d-113">Per la funzionalità di lavoro, il tipo di parametro soglia `T` deve implementare il <xref:System.IComparable> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8e67d-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="8e67d-114">Il modulo che ospita il `AttributesDemoControl` esegue periodicamente una query un contatore delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8e67d-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="8e67d-115">Ogni valore viene inserito in una `LogEntry` del tipo appropriato e aggiunto al form <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="8e67d-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="8e67d-116">Il `AttributesDemoControl` riceve il valore tramite l'associazione dati e viene visualizzato il valore in un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="8e67d-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="8e67d-117">Il primo esempio di codice è il `AttributesDemoControl` implementazione.</span><span class="sxs-lookup"><span data-stu-id="8e67d-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="8e67d-118">Il secondo esempio di codice viene illustrato un form che usa il `AttributesDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="8e67d-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="8e67d-119">Attributi a livello di classe</span><span class="sxs-lookup"><span data-stu-id="8e67d-119">Class-level Attributes</span></span>  
 <span data-ttu-id="8e67d-120">Alcuni attributi vengono applicati a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="8e67d-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="8e67d-121">Esempio di codice seguente illustra gli attributi che vengono generalmente applicati a un controllo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8e67d-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="8e67d-122">Atribut TypeConverter</span><span class="sxs-lookup"><span data-stu-id="8e67d-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="8e67d-123"><xref:System.ComponentModel.TypeConverterAttribute> è un altro attributo a livello di classe comunemente utilizzato.</span><span class="sxs-lookup"><span data-stu-id="8e67d-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="8e67d-124">Esempio di codice seguente viene illustrato l'utilizzo per il `LogEntry` classe.</span><span class="sxs-lookup"><span data-stu-id="8e67d-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="8e67d-125">In questo esempio viene inoltre illustrata un'implementazione di un <xref:System.ComponentModel.TypeConverter> per il `LogEntry` tipo, denominato `LogEntryTypeConverter`.</span><span class="sxs-lookup"><span data-stu-id="8e67d-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="8e67d-126">Attributi a livello di membro</span><span class="sxs-lookup"><span data-stu-id="8e67d-126">Member-level Attributes</span></span>  
 <span data-ttu-id="8e67d-127">Alcuni attributi vengono applicati a livello di membro.</span><span class="sxs-lookup"><span data-stu-id="8e67d-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="8e67d-128">Gli esempi di codice seguenti illustrano alcuni attributi comunemente applicate alle proprietà dei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8e67d-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="8e67d-129">Attributo AmbientValue</span><span class="sxs-lookup"><span data-stu-id="8e67d-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="8e67d-130">Nell'esempio seguente viene illustrato il <xref:System.ComponentModel.AmbientValueAttribute> e Mostra il codice che supporta l'interazione con l'ambiente di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8e67d-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="8e67d-131">Questa interazione viene chiamata *atmosfera*.</span><span class="sxs-lookup"><span data-stu-id="8e67d-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="8e67d-132">Attributi di Data Binding</span><span class="sxs-lookup"><span data-stu-id="8e67d-132">Databinding Attributes</span></span>  
 <span data-ttu-id="8e67d-133">Gli esempi seguenti illustrano un'implementazione di data binding complesso.</span><span class="sxs-lookup"><span data-stu-id="8e67d-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="8e67d-134">Livello di classe <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, come illustrato in precedenza, specifica il `DataSource` e `DataMember` proprietà da utilizzare per il data binding.</span><span class="sxs-lookup"><span data-stu-id="8e67d-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="8e67d-135">Il <xref:System.ComponentModel.AttributeProviderAttribute> specifica il tipo a cui il `DataSource` assocerà la proprietà.</span><span class="sxs-lookup"><span data-stu-id="8e67d-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8e67d-136">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8e67d-136">Compiling the Code</span></span>  
  
-   <span data-ttu-id="8e67d-137">Il form che contiene il `AttributesDemoControl` richiede un riferimento al `AttributesDemoControl` per compilare assembly.</span><span class="sxs-lookup"><span data-stu-id="8e67d-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e67d-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e67d-138">See also</span></span>
- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="8e67d-139">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8e67d-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="8e67d-140">Attributi nei controlli Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8e67d-140">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
- <span data-ttu-id="8e67d-141">[Procedura: Serializzare raccolte di tipi Standard tramite DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="8e67d-141">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>

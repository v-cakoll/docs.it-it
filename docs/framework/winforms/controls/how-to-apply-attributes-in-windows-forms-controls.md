---
title: Applicare gli attributi nei controlli
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: b8ecd516cf6bb189c6ad1b208dd8e3a5444f001c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741488"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="754fd-102">Procedura: applicare attributi nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="754fd-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="754fd-103">Per sviluppare componenti e controlli che interagiscono correttamente con l'ambiente di progettazione e vengono eseguiti correttamente in fase di esecuzione, è necessario applicare correttamente gli attributi a classi e membri.</span><span class="sxs-lookup"><span data-stu-id="754fd-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="754fd-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="754fd-104">Example</span></span>  
 <span data-ttu-id="754fd-105">Nell'esempio di codice riportato di seguito viene illustrato come utilizzare diversi attributi in un controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="754fd-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="754fd-106">Il controllo illustra una semplice funzionalità di registrazione.</span><span class="sxs-lookup"><span data-stu-id="754fd-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="754fd-107">Quando il controllo è associato a un'origine dati, Visualizza i valori inviati dall'origine dati in un controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="754fd-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="754fd-108">Se un valore supera il valore specificato dalla proprietà `Threshold`, viene generato un evento `ThresholdExceeded`.</span><span class="sxs-lookup"><span data-stu-id="754fd-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="754fd-109">Il `AttributesDemoControl` registra i valori con una classe `LogEntry`.</span><span class="sxs-lookup"><span data-stu-id="754fd-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="754fd-110">La classe `LogEntry` è una classe modello, che significa che è parametrizzata sul tipo che registra.</span><span class="sxs-lookup"><span data-stu-id="754fd-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="754fd-111">Se, ad esempio, il `AttributesDemoControl` registra i valori di tipo `float`, ogni `LogEntry` istanza viene dichiarata e utilizzata come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="754fd-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="754fd-112">Poiché `LogEntry` è parametrizzato da un tipo arbitrario, è necessario utilizzare la reflection per operare sul tipo di parametro.</span><span class="sxs-lookup"><span data-stu-id="754fd-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="754fd-113">Per il funzionamento della funzionalità di soglia, il tipo di parametro `T` deve implementare l'interfaccia <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="754fd-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="754fd-114">Il modulo che ospita il `AttributesDemoControl` esegue periodicamente query su un contatore delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="754fd-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="754fd-115">Ogni valore è incluso in un `LogEntry` del tipo appropriato e viene aggiunto al <xref:System.Windows.Forms.BindingSource>del modulo.</span><span class="sxs-lookup"><span data-stu-id="754fd-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="754fd-116">Il `AttributesDemoControl` riceve il valore tramite la relativa data binding e visualizza il valore in un controllo di <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="754fd-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="754fd-117">Il primo esempio di codice è l'implementazione del `AttributesDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="754fd-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="754fd-118">Nel secondo esempio di codice viene illustrato un modulo che utilizza il `AttributesDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="754fd-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="754fd-119">Attributi a livello di classe</span><span class="sxs-lookup"><span data-stu-id="754fd-119">Class-level Attributes</span></span>  
 <span data-ttu-id="754fd-120">Alcuni attributi vengono applicati a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="754fd-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="754fd-121">Nell'esempio di codice riportato di seguito vengono illustrati gli attributi comunemente applicati a un controllo Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="754fd-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="754fd-122">TypeConverter (attributo)</span><span class="sxs-lookup"><span data-stu-id="754fd-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="754fd-123"><xref:System.ComponentModel.TypeConverterAttribute> è un altro attributo a livello di classe comunemente utilizzato.</span><span class="sxs-lookup"><span data-stu-id="754fd-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="754fd-124">Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo della classe `LogEntry`.</span><span class="sxs-lookup"><span data-stu-id="754fd-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="754fd-125">In questo esempio viene inoltre illustrata un'implementazione di un <xref:System.ComponentModel.TypeConverter> per il tipo di `LogEntry`, denominato `LogEntryTypeConverter`.</span><span class="sxs-lookup"><span data-stu-id="754fd-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="754fd-126">Attributi a livello di membro</span><span class="sxs-lookup"><span data-stu-id="754fd-126">Member-level Attributes</span></span>  
 <span data-ttu-id="754fd-127">Alcuni attributi vengono applicati a livello di membro.</span><span class="sxs-lookup"><span data-stu-id="754fd-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="754fd-128">Negli esempi di codice riportati di seguito vengono illustrati alcuni attributi che vengono comunemente applicati alle proprietà dei controlli Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="754fd-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="754fd-129">Attributo AmbientValue</span><span class="sxs-lookup"><span data-stu-id="754fd-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="754fd-130">Nell'esempio seguente viene illustrato il <xref:System.ComponentModel.AmbientValueAttribute> e viene mostrato il codice che supporta l'interazione con l'ambiente di progettazione.</span><span class="sxs-lookup"><span data-stu-id="754fd-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="754fd-131">Questa interazione è detta *ambiente*.</span><span class="sxs-lookup"><span data-stu-id="754fd-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="754fd-132">Attributi DataBinding</span><span class="sxs-lookup"><span data-stu-id="754fd-132">Databinding Attributes</span></span>  
 <span data-ttu-id="754fd-133">Negli esempi seguenti viene illustrata un'implementazione di data binding complesse.</span><span class="sxs-lookup"><span data-stu-id="754fd-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="754fd-134">Il <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>a livello di classe, illustrato in precedenza, specifica le proprietà `DataSource` e `DataMember` da utilizzare per data binding.</span><span class="sxs-lookup"><span data-stu-id="754fd-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="754fd-135">Il <xref:System.ComponentModel.AttributeProviderAttribute> specifica il tipo a cui viene associata la proprietà `DataSource`.</span><span class="sxs-lookup"><span data-stu-id="754fd-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="754fd-136">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="754fd-136">Compiling the Code</span></span>  
  
- <span data-ttu-id="754fd-137">Il form che ospita il `AttributesDemoControl` richiede un riferimento all'assembly `AttributesDemoControl` per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="754fd-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754fd-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="754fd-138">See also</span></span>

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="754fd-139">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="754fd-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="754fd-140">Attributi nei controlli Windows Forms</span><span class="sxs-lookup"><span data-stu-id="754fd-140">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
- <span data-ttu-id="754fd-141">[Procedura: serializzare raccolte di tipi standard con DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="754fd-141">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>

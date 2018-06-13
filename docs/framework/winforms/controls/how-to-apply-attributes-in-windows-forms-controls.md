---
title: 'Procedura: applicare attributi nei controlli Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: 49c2aaa48a48e33a71b5112db31991975011551d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529636"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="b046f-102">Procedura: applicare attributi nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="b046f-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="b046f-103">Per sviluppare componenti e controlli che interagiscano correttamente con l'ambiente di progettazione ed eseguire correttamente in fase di esecuzione, è necessario applicare correttamente gli attributi alle classi e membri.</span><span class="sxs-lookup"><span data-stu-id="b046f-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b046f-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b046f-104">Example</span></span>  
 <span data-ttu-id="b046f-105">Esempio di codice riportato di seguito viene illustrato come utilizzare diversi attributi con un controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b046f-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="b046f-106">Il controllo illustra una funzionalità di registrazione semplice.</span><span class="sxs-lookup"><span data-stu-id="b046f-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="b046f-107">Quando il controllo è associato a un'origine dati, vengono visualizzati i valori inviati dall'origine dei dati in un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="b046f-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b046f-108">Se un valore supera il valore specificato per il `Threshold` proprietà, un `ThresholdExceeded` viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="b046f-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="b046f-109">Il `AttributesDemoControl` registra i valori con un `LogEntry` classe.</span><span class="sxs-lookup"><span data-stu-id="b046f-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="b046f-110">La `LogEntry` classe è una classe di modello, ovvero con i parametri nel tipo che viene registrato.</span><span class="sxs-lookup"><span data-stu-id="b046f-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="b046f-111">Ad esempio, se il `AttributesDemoControl` registra valori di tipo `float`, ogni `LogEntry` istanza viene dichiarata e utilizzata come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="b046f-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="b046f-112">Poiché `LogEntry` è con parametri per un tipo arbitrario, è necessario usare la reflection per funzionare con il tipo di parametro.</span><span class="sxs-lookup"><span data-stu-id="b046f-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="b046f-113">Per la funzionalità di lavoro, il tipo di parametro soglia `T` deve implementare il <xref:System.IComparable> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b046f-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="b046f-114">Il modulo che ospita il `AttributesDemoControl` esegue periodicamente una query di un contatore delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b046f-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="b046f-115">Ogni valore viene inserito in un `LogEntry` del tipo appropriato e aggiunto al form <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="b046f-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="b046f-116">Il `AttributesDemoControl` riceve il valore tramite l'associazione dati e visualizza il valore in un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="b046f-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="b046f-117">Il primo esempio di codice è il `AttributesDemoControl` implementazione.</span><span class="sxs-lookup"><span data-stu-id="b046f-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="b046f-118">Nel secondo esempio di codice viene illustrato un form che usa il `AttributesDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="b046f-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="b046f-119">Attributi a livello di classe</span><span class="sxs-lookup"><span data-stu-id="b046f-119">Class-level Attributes</span></span>  
 <span data-ttu-id="b046f-120">Alcuni attributi vengono applicati a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="b046f-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="b046f-121">Esempio di codice seguente mostra gli attributi che sono in genere applicati a un controllo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="b046f-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="b046f-122">Attributo TypeConverter</span><span class="sxs-lookup"><span data-stu-id="b046f-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="b046f-123"><xref:System.ComponentModel.TypeConverterAttribute> è un altro attributo a livello di classe di uso comune.</span><span class="sxs-lookup"><span data-stu-id="b046f-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="b046f-124">Esempio di codice seguente viene illustrato l'utilizzo per la `LogEntry` classe.</span><span class="sxs-lookup"><span data-stu-id="b046f-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="b046f-125">In questo esempio viene inoltre illustrata un'implementazione di un <xref:System.ComponentModel.TypeConverter> per il `LogEntry` tipo, denominato `LogEntryTypeConverter`.</span><span class="sxs-lookup"><span data-stu-id="b046f-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="b046f-126">Attributi a livello di membro</span><span class="sxs-lookup"><span data-stu-id="b046f-126">Member-level Attributes</span></span>  
 <span data-ttu-id="b046f-127">Alcuni attributi vengono applicati a livello di membro.</span><span class="sxs-lookup"><span data-stu-id="b046f-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="b046f-128">Gli esempi di codice seguenti illustrano alcuni attributi vengono in genere applicati alle proprietà dei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="b046f-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="b046f-129">Attributo AmbientValue</span><span class="sxs-lookup"><span data-stu-id="b046f-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="b046f-130">Nell'esempio seguente viene illustrato il <xref:System.ComponentModel.AmbientValueAttribute> e il codice che supporta l'interazione con l'ambiente di progettazione.</span><span class="sxs-lookup"><span data-stu-id="b046f-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="b046f-131">Viene chiamata per tale interazione *ambiente*.</span><span class="sxs-lookup"><span data-stu-id="b046f-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="b046f-132">Attributi di associazione dati</span><span class="sxs-lookup"><span data-stu-id="b046f-132">Databinding Attributes</span></span>  
 <span data-ttu-id="b046f-133">Nell'esempio seguente viene illustrata l'implementazione di data binding complesso.</span><span class="sxs-lookup"><span data-stu-id="b046f-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="b046f-134">Il livello di classe <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, come illustrato in precedenza, specifica il `DataSource` e `DataMember` proprietà da utilizzare per l'associazione dati.</span><span class="sxs-lookup"><span data-stu-id="b046f-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="b046f-135">Il <xref:System.ComponentModel.AttributeProviderAttribute> specifica il tipo a cui il `DataSource` assocerà la proprietà.</span><span class="sxs-lookup"><span data-stu-id="b046f-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b046f-136">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b046f-136">Compiling the Code</span></span>  
  
-   <span data-ttu-id="b046f-137">Il modulo che ospita il `AttributesDemoControl` richiede un riferimento al `AttributesDemoControl` assembly per eseguire la compilazione.</span><span class="sxs-lookup"><span data-stu-id="b046f-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b046f-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b046f-138">See Also</span></span>  
 <xref:System.IComparable>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="b046f-139">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b046f-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="b046f-140">Attributi nei controlli Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b046f-140">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 [<span data-ttu-id="b046f-141">Procedura: serializzare le raccolte di tipi Standard tramite DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="b046f-141">How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)

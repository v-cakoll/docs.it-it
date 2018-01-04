---
title: Attributi nei controlli Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- attributes [Windows Forms]
- attributes [Windows Forms], data binding properties
- attributes [Windows Forms], control properties
- attributes [Windows Forms], classes
ms.assetid: 2c5640e9-6c6c-49d7-a5e4-a768f6be7853
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13aad22dca249147e3037bcef6da755c264021db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="attributes-in-windows-forms-controls"></a><span data-ttu-id="3e7bf-102">Attributi nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="3e7bf-102">Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="3e7bf-103">.NET Framework offre un'ampia gamma di attributi che è possibile applicare ai membri dei controlli e dei componenti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-103">The .NET Framework provides a variety of attributes you can apply to the members of your custom controls and components.</span></span> <span data-ttu-id="3e7bf-104">Alcuni di questi attributi influiscono sul comportamento in fase di esecuzione di una classe, mentre altri influiscono sul comportamento in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-104">Some of these attributes affect the run-time behavior of a class, and others affect the design-time behavior.</span></span>  
  
## <a name="attributes-for-control-and-component-properties"></a><span data-ttu-id="3e7bf-105">Attributi per le proprietà del controllo e del componente</span><span class="sxs-lookup"><span data-stu-id="3e7bf-105">Attributes for Control and Component Properties</span></span>  
 <span data-ttu-id="3e7bf-106">La tabella seguente illustra gli attributi che è possibile applicare alle proprietà o ad altri membri dei componenti e dei controlli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-106">The following table shows the attributes you can apply to properties or other members of your custom controls and components.</span></span> <span data-ttu-id="3e7bf-107">Per un esempio che usa molti di questi attributi vedere [Procedura: applicare attributi nei controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="3e7bf-107">For an example that uses many of these attributes, see [How to: Apply Attributes in Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
|<span data-ttu-id="3e7bf-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="3e7bf-108">Attribute</span></span>|<span data-ttu-id="3e7bf-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e7bf-109">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ComponentModel.AmbientValueAttribute>|<span data-ttu-id="3e7bf-110">Specifica il valore per passare a una proprietà che determini il proprio valore da un'altra origine.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-110">Specifies the value to pass to a property to cause the property to get its value from another source.</span></span> <span data-ttu-id="3e7bf-111">Questo concetto è noto come *ambiente*.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-111">This is known as *ambience*.</span></span>|  
|<xref:System.ComponentModel.BrowsableAttribute>|<span data-ttu-id="3e7bf-112">Indica se visualizzare una proprietà o un evento in una finestra **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-112">Specifies whether a property or event should be displayed in a **Properties** window.</span></span>|  
|<xref:System.ComponentModel.CategoryAttribute>|<span data-ttu-id="3e7bf-113">Specifica il nome della categoria in base a cui raggruppare la proprietà o evento se visualizzato in un <xref:System.Windows.Forms.PropertyGrid> controllo impostato su <xref:System.Windows.Forms.PropertySort.Categorized> modalità.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-113">Specifies the name of the category in which to group the property or event when displayed in a <xref:System.Windows.Forms.PropertyGrid> control set to <xref:System.Windows.Forms.PropertySort.Categorized> mode.</span></span>|  
|<xref:System.ComponentModel.DefaultValueAttribute>|<span data-ttu-id="3e7bf-114">Specifica il valore predefinito per una proprietà.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-114">Specifies the default value for a property.</span></span>|  
|<xref:System.ComponentModel.DescriptionAttribute>|<span data-ttu-id="3e7bf-115">Specifica una descrizione per una proprietà o un evento.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-115">Specifies a description for a property or event.</span></span>|  
|<xref:System.ComponentModel.DisplayNameAttribute>|<span data-ttu-id="3e7bf-116">Specifica il nome visualizzato per una proprietà, un evento o un metodo `public``void` che non accetta argomenti.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-116">Specifies the display name for a property, event, or `public``void` method that takes no arguments.</span></span>|  
|<xref:System.ComponentModel.EditorAttribute>|<span data-ttu-id="3e7bf-117">Specifica l'editor da usare per modificare una proprietà.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-117">Specifies the editor to use to change a property.</span></span>|  
|<xref:System.ComponentModel.EditorBrowsableAttribute>|<span data-ttu-id="3e7bf-118">Specifica che una proprietà o un metodo è visualizzabile in un editor.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-118">Specifies that a property or method is viewable in an editor.</span></span>|  
|<xref:System.ComponentModel.Design.HelpKeywordAttribute>|<span data-ttu-id="3e7bf-119">Specifica la parola chiave di contesto per una classe o un membro.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-119">Specifies the context keyword for a class or member.</span></span>|  
|<xref:System.ComponentModel.LocalizableAttribute>|<span data-ttu-id="3e7bf-120">Specifica se è necessario localizzare una proprietà.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-120">Specifies whether a property should be localized.</span></span>|  
|<xref:System.ComponentModel.PasswordPropertyTextAttribute>|<span data-ttu-id="3e7bf-121">Indica che la rappresentazione di testo di un oggetto è nascosta da caratteri quali gli asterischi.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-121">Indicates that an object's text representation is obscured by characters such as asterisks.</span></span>|  
|<xref:System.ComponentModel.ReadOnlyAttribute>|<span data-ttu-id="3e7bf-122">Specifica se la proprietà a cui è associato questo attributo è di sola lettura o di lettura/scrittura in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-122">Specifies whether the property this attribute is bound to is read-only or read/write at design time.</span></span>|  
|<xref:System.ComponentModel.RefreshPropertiesAttribute>|<span data-ttu-id="3e7bf-123">Indica che la griglia delle proprietà deve essere aggiornata quando cambia il valore della proprietà associata.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-123">Indicates that the property grid should refresh when the associated property value changes.</span></span>|  
|<xref:System.ComponentModel.TypeConverterAttribute>|<span data-ttu-id="3e7bf-124">Specifica il tipo da utilizzare come convertitore per l'oggetto a cui l'attributo è associato.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-124">Specifies what type to use as a converter for the object this attribute is bound to.</span></span>|  
  
## <a name="attributes-for-data-binding-properties"></a><span data-ttu-id="3e7bf-125">Attributi per le proprietà dell'associazione di dati</span><span class="sxs-lookup"><span data-stu-id="3e7bf-125">Attributes for Data Binding Properties</span></span>  
 <span data-ttu-id="3e7bf-126">La tabella seguente illustra gli attributi che è possibile applicare per specificare le modalità in cui i componenti e i controlli personalizzati interagiscono con l'associazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-126">The following table shows the attributes you can apply to specify how your custom controls and components interact with data binding.</span></span>  
  
|<span data-ttu-id="3e7bf-127">Attributo</span><span class="sxs-lookup"><span data-stu-id="3e7bf-127">Attribute</span></span>|<span data-ttu-id="3e7bf-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e7bf-128">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ComponentModel.BindableAttribute>|<span data-ttu-id="3e7bf-129">Specifica se una proprietà viene in genere usata per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-129">Specifies whether a property is typically used for binding.</span></span>|  
|<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|<span data-ttu-id="3e7bf-130">Specifica l'origine dati e le proprietà dei membri dati per un componente.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-130">Specifies the data source and data member properties for a component.</span></span>|  
|<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|<span data-ttu-id="3e7bf-131">Specifica la proprietà di associazione predefinita per un componente.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-131">Specifies the default binding property for a component.</span></span>|  
|<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|<span data-ttu-id="3e7bf-132">Specifica l'origine dati e le proprietà dei membri dati per un componente.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-132">Specifies the data source and data member properties for a component.</span></span>|  
|<xref:System.ComponentModel.AttributeProviderAttribute>|<span data-ttu-id="3e7bf-133">Consente il reindirizzamento degli attributi.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-133">Enables attribute redirection.</span></span>|  
  
## <a name="attributes-for-classes"></a><span data-ttu-id="3e7bf-134">Attributi per classi</span><span class="sxs-lookup"><span data-stu-id="3e7bf-134">Attributes for Classes</span></span>  
 <span data-ttu-id="3e7bf-135">La tabella seguente illustra gli attributi che è possibile applicare per specificare il comportamento dei componenti e dei controlli personalizzati in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-135">The following table shows the attributes you can apply to specify the behavior of your custom controls and components at design time.</span></span>  
  
|<span data-ttu-id="3e7bf-136">Attributo</span><span class="sxs-lookup"><span data-stu-id="3e7bf-136">Attribute</span></span>|<span data-ttu-id="3e7bf-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e7bf-137">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ComponentModel.DefaultEventAttribute>|<span data-ttu-id="3e7bf-138">Specifica l'evento predefinito per un componente.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-138">Specifies the default event for a component.</span></span>|  
|<xref:System.ComponentModel.DefaultPropertyAttribute>|<span data-ttu-id="3e7bf-139">Specifica la proprietà predefinita per un componente.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-139">Specifies the default property for a component.</span></span>|  
|<xref:System.ComponentModel.DesignerAttribute>|<span data-ttu-id="3e7bf-140">Specifica la classe usata per implementare i servizi in fase di progettazione per un componente.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-140">Specifies the class used to implement design-time services for a component.</span></span>|  
|<xref:System.ComponentModel.DesignerCategoryAttribute>|<span data-ttu-id="3e7bf-141">Specifica che la finestra di progettazione di una classe appartiene a una determinata categoria.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-141">Specifies that the designer for a class belongs to a certain category.</span></span>|  
|<xref:System.ComponentModel.ToolboxItemAttribute>|<span data-ttu-id="3e7bf-142">Rappresenta un attributo di un elemento della casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-142">Represents an attribute of a toolbox item.</span></span>|  
|<xref:System.ComponentModel.ToolboxItemFilterAttribute>|<span data-ttu-id="3e7bf-143">Specifica la stringa del filtro e il tipo di filtro da usare per un elemento della casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="3e7bf-143">Specifies the filter string and filter type to use for a Toolbox item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e7bf-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e7bf-144">See Also</span></span>  
 <xref:System.Attribute>  
 [<span data-ttu-id="3e7bf-145">Procedura: Applicare attributi nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="3e7bf-145">How to: Apply Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)  
 [<span data-ttu-id="3e7bf-146">Estensione del supporto in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="3e7bf-146">Extending Design-Time Support</span></span>](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [<span data-ttu-id="3e7bf-147">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3e7bf-147">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)

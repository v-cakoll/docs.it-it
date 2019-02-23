---
title: Data binding di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
ms.openlocfilehash: b33ad9d78230588b9c1afd5d59fd0333e2cd18a6
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747061"
---
# <a name="windows-forms-data-binding"></a><span data-ttu-id="60810-102">Data binding di Windows Form</span><span class="sxs-lookup"><span data-stu-id="60810-102">Windows Forms Data Binding</span></span>
<span data-ttu-id="60810-103">Data binding in Windows Form consente di visualizzare e modificare le informazioni da un'origine dati nei controlli del form.</span><span class="sxs-lookup"><span data-stu-id="60810-103">Data binding in Windows Forms gives you the means to display and make changes to information from a data source in controls on the form.</span></span> <span data-ttu-id="60810-104">È possibile effettuare associazioni alle origini dati tradizionali e a quasi ogni struttura che contiene dati.</span><span class="sxs-lookup"><span data-stu-id="60810-104">You can bind to both traditional data sources as well as almost any structure that contains data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60810-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="60810-105">In This Section</span></span>  
 [<span data-ttu-id="60810-106">Data binding e Windows Forms</span><span class="sxs-lookup"><span data-stu-id="60810-106">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 <span data-ttu-id="60810-107">Fornisce una panoramica del data binding in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="60810-107">Provides an overview of data binding in Windows Forms.</span></span>  
  
 [<span data-ttu-id="60810-108">Origini dati supportate da Windows Form</span><span class="sxs-lookup"><span data-stu-id="60810-108">Data Sources Supported by Windows Forms</span></span>](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 <span data-ttu-id="60810-109">Descrive le origini dati che possono essere usate con Windows Form.</span><span class="sxs-lookup"><span data-stu-id="60810-109">Describes the data sources that can be used with Windows Forms.</span></span>  
  
 [<span data-ttu-id="60810-110">Interfacce correlate al data binding</span><span class="sxs-lookup"><span data-stu-id="60810-110">Interfaces Related to Data Binding</span></span>](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 <span data-ttu-id="60810-111">Descrive molte delle interfacce usate con il data binding in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="60810-111">Describes several of the interfaces used with Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="60810-112">Procedura: Esplorare dati in Windows Form</span><span class="sxs-lookup"><span data-stu-id="60810-112">How to: Navigate Data in Windows Forms</span></span>](../../../docs/framework/winforms/how-to-navigate-data-in-windows-forms.md)  
 <span data-ttu-id="60810-113">Mostra come spostarsi tra gli elementi in un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="60810-113">Shows how to navigate through items in a data source.</span></span>  
  
 [<span data-ttu-id="60810-114">Notifica delle modifiche nel data binding dei Windows Form</span><span class="sxs-lookup"><span data-stu-id="60810-114">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 <span data-ttu-id="60810-115">Descrive i vari tipi di notifica delle modifiche per il data binding in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="60810-115">Describes different types of change notification for Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="60810-116">Procedura: Implementare l'interfaccia INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="60810-116">How to: Implement the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 <span data-ttu-id="60810-117">Mostra come implementare l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="60810-117">Shows how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="60810-118">L'interfaccia comunica a un controllo associato le modifiche delle proprietà di un oggetto business.</span><span class="sxs-lookup"><span data-stu-id="60810-118">The interface  communicates to a bound control the property changes on a business object</span></span>  
  
 [<span data-ttu-id="60810-119">Procedura: Applicare il modello PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="60810-119">How to: Apply the PropertyNameChanged Pattern</span></span>](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 <span data-ttu-id="60810-120">Viene illustrato come applicare la *PropertyName*modello Changed alle proprietà di un controllo utente Windows Form.</span><span class="sxs-lookup"><span data-stu-id="60810-120">Shows how to apply the *PropertyName*Changed pattern to properties of a Windows Forms user control.</span></span>  
  
 [<span data-ttu-id="60810-121">Procedura: Implementare l'interfaccia ITypedList</span><span class="sxs-lookup"><span data-stu-id="60810-121">How to: Implement the ITypedList Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-itypedlist-interface.md)  
 <span data-ttu-id="60810-122">Mostra come abilitare l'individuazione dello schema per un elenco associabile mediante l'implementazione dell'interfaccia <xref:System.ComponentModel.ITypedList>.</span><span class="sxs-lookup"><span data-stu-id="60810-122">Shows how to enable discovery of the schema for a bindable list by implementing the <xref:System.ComponentModel.ITypedList> interface.</span></span>  
  
 [<span data-ttu-id="60810-123">Procedura: Implementare l'interfaccia IListSource</span><span class="sxs-lookup"><span data-stu-id="60810-123">How to: Implement the IListSource Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-ilistsource-interface.md)  
 <span data-ttu-id="60810-124">Illustra come implementare l'interfaccia <xref:System.ComponentModel.IListSource> per creare una classe associabile che non implementa <xref:System.Collections.IList>, ma fornisce un elenco da un altro percorso.</span><span class="sxs-lookup"><span data-stu-id="60810-124">Shows how to implement the <xref:System.ComponentModel.IListSource> interface to create a bindable class does not implement <xref:System.Collections.IList>, but provides a list from another location.</span></span>  
  
 [<span data-ttu-id="60810-125">Procedura: Verificare che più controlli associati alla stessa origine dati rimangano sincronizzati</span><span class="sxs-lookup"><span data-stu-id="60810-125">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)  
 <span data-ttu-id="60810-126">Mostra come gestire l'evento <xref:System.Windows.Forms.BindingSource.BindingComplete> per assicurare che tutti i controlli associati a un'origine dati rimangano sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="60810-126">Shows how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event to ensure all controls bound to a data source remain synchronized.</span></span>  
  
 [<span data-ttu-id="60810-127">Procedura: Verificare che la riga selezionata in una tabella figlio rimanga nella posizione corretta</span><span class="sxs-lookup"><span data-stu-id="60810-127">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>](../../../docs/framework/winforms/ensure-the-selected-row-in-a-child-table-correct.md)  
 <span data-ttu-id="60810-128">Mostra come garantire che la riga selezionata di una tabella figlio non venga modificata quando viene apportata una modifica a un campo della tabella padre.</span><span class="sxs-lookup"><span data-stu-id="60810-128">Shows how to ensure the selected row of a child table does not change, when a change is made to a field of the parent table.</span></span>  
  
 <span data-ttu-id="60810-129">Vedere anche [interfacce correlate al Data Binding](interfaces-related-to-data-binding.md), [come: Esplorare dati in Windows Form](how-to-navigate-data-in-windows-forms.md), e [come: Creare un controllo con associazione semplice in un Form Windows](how-to-create-a-simple-bound-control-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="60810-129">Also see [Interfaces Related to Data Binding](interfaces-related-to-data-binding.md), [How to: Navigate Data in Windows Forms](how-to-navigate-data-in-windows-forms.md), and [How to: Create a Simple-Bound Control on a Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="60810-130">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="60810-130">Reference</span></span>  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 <span data-ttu-id="60810-131">Descrive la classe che rappresenta l'associazione tra un componente associabile e un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="60810-131">Describes the class that represents the binding between a bindable component and a data source.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 <span data-ttu-id="60810-132">Descrive la classe che incapsula un'origine dati per l'associazione ai controlli.</span><span class="sxs-lookup"><span data-stu-id="60810-132">Describes the class that encapsulates a data source for binding to controls.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="60810-133">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="60810-133">Related Sections</span></span>  
 [<span data-ttu-id="60810-134">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="60810-134">BindingSource Component</span></span>](../../../docs/framework/winforms/controls/bindingsource-component.md)  
 <span data-ttu-id="60810-135">Contiene un elenco di argomenti in cui viene illustrato come usare il componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="60810-135">Contains a list of topics that demonstrate how to use the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="60810-136">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="60810-136">DataGridView Control</span></span>](../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 <span data-ttu-id="60810-137">Fornisce un elenco di argomenti in cui viene illustrato come usare un controllo Datagrid associabile.</span><span class="sxs-lookup"><span data-stu-id="60810-137">Provides a list of topics that demonstrate how to use a bindable datagrid control.</span></span>  
  
 <span data-ttu-id="60810-138">Vedere anche [l'accesso ai dati in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="60810-138">Also see [Accessing Data in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span></span>

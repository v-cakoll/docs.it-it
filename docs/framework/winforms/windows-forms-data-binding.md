---
title: Data binding
description: Informazioni su come usare data binding in Windows Forms per visualizzare e modificare le informazioni di un'origine dati in controlli del modulo.
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
ms.openlocfilehash: 3dfce24147caf9b138916ca8dc3b7a9010439f58
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325548"
---
# <a name="windows-forms-data-binding"></a><span data-ttu-id="4905e-103">Data binding di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4905e-103">Windows Forms Data Binding</span></span>
<span data-ttu-id="4905e-104">Data binding in Windows Form consente di visualizzare e modificare le informazioni da un'origine dati nei controlli del form.</span><span class="sxs-lookup"><span data-stu-id="4905e-104">Data binding in Windows Forms gives you the means to display and make changes to information from a data source in controls on the form.</span></span> <span data-ttu-id="4905e-105">È possibile effettuare associazioni alle origini dati tradizionali e a quasi ogni struttura che contiene dati.</span><span class="sxs-lookup"><span data-stu-id="4905e-105">You can bind to both traditional data sources as well as almost any structure that contains data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4905e-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4905e-106">In This Section</span></span>  
 [<span data-ttu-id="4905e-107">Associazione dati e Windows Form</span><span class="sxs-lookup"><span data-stu-id="4905e-107">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)  
 <span data-ttu-id="4905e-108">Fornisce una panoramica del data binding in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="4905e-108">Provides an overview of data binding in Windows Forms.</span></span>  
  
 [<span data-ttu-id="4905e-109">Origini dati supportate da Windows Form</span><span class="sxs-lookup"><span data-stu-id="4905e-109">Data Sources Supported by Windows Forms</span></span>](data-sources-supported-by-windows-forms.md)  
 <span data-ttu-id="4905e-110">Descrive le origini dati che possono essere usate con Windows Form.</span><span class="sxs-lookup"><span data-stu-id="4905e-110">Describes the data sources that can be used with Windows Forms.</span></span>  
  
 [<span data-ttu-id="4905e-111">Interfacce correlate al data binding</span><span class="sxs-lookup"><span data-stu-id="4905e-111">Interfaces Related to Data Binding</span></span>](interfaces-related-to-data-binding.md)  
 <span data-ttu-id="4905e-112">Descrive molte delle interfacce usate con il data binding in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="4905e-112">Describes several of the interfaces used with Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="4905e-113">Procedura: Esplorare dati in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4905e-113">How to: Navigate Data in Windows Forms</span></span>](how-to-navigate-data-in-windows-forms.md)  
 <span data-ttu-id="4905e-114">Mostra come spostarsi tra gli elementi in un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4905e-114">Shows how to navigate through items in a data source.</span></span>  
  
 [<span data-ttu-id="4905e-115">Notifica delle modifiche nell'associazione dati dei Windows Form</span><span class="sxs-lookup"><span data-stu-id="4905e-115">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)  
 <span data-ttu-id="4905e-116">Descrive i vari tipi di notifica delle modifiche per il data binding in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="4905e-116">Describes different types of change notification for Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="4905e-117">Procedura: Implementare l'interfaccia INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="4905e-117">How to: Implement the INotifyPropertyChanged Interface</span></span>](how-to-implement-the-inotifypropertychanged-interface.md)  
 <span data-ttu-id="4905e-118">Mostra come implementare l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="4905e-118">Shows how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="4905e-119">L'interfaccia comunica a un controllo associato le modifiche delle proprietà di un oggetto business.</span><span class="sxs-lookup"><span data-stu-id="4905e-119">The interface  communicates to a bound control the property changes on a business object</span></span>  
  
 [<span data-ttu-id="4905e-120">Procedura: Applicare il modello PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="4905e-120">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)  
 <span data-ttu-id="4905e-121">Illustra come applicare il modello *PropertyName*changed alle proprietà di un controllo utente Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4905e-121">Shows how to apply the *PropertyName*Changed pattern to properties of a Windows Forms user control.</span></span>  
  
 [<span data-ttu-id="4905e-122">Procedura: Implementare l'interfaccia ITypedList</span><span class="sxs-lookup"><span data-stu-id="4905e-122">How to: Implement the ITypedList Interface</span></span>](how-to-implement-the-itypedlist-interface.md)  
 <span data-ttu-id="4905e-123">Mostra come abilitare l'individuazione dello schema per un elenco associabile mediante l'implementazione dell'interfaccia <xref:System.ComponentModel.ITypedList>.</span><span class="sxs-lookup"><span data-stu-id="4905e-123">Shows how to enable discovery of the schema for a bindable list by implementing the <xref:System.ComponentModel.ITypedList> interface.</span></span>  
  
 [<span data-ttu-id="4905e-124">Procedura: Implementare l'interfaccia IListSource</span><span class="sxs-lookup"><span data-stu-id="4905e-124">How to: Implement the IListSource Interface</span></span>](how-to-implement-the-ilistsource-interface.md)  
 <span data-ttu-id="4905e-125">Illustra come implementare l'interfaccia <xref:System.ComponentModel.IListSource> per creare una classe associabile che non implementa <xref:System.Collections.IList>, ma fornisce un elenco da un altro percorso.</span><span class="sxs-lookup"><span data-stu-id="4905e-125">Shows how to implement the <xref:System.ComponentModel.IListSource> interface to create a bindable class does not implement <xref:System.Collections.IList>, but provides a list from another location.</span></span>  
  
 [<span data-ttu-id="4905e-126">Procedura: Garantire la sincronizzazione di più controlli associati alla stessa origine dati</span><span class="sxs-lookup"><span data-stu-id="4905e-126">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](multiple-controls-bound-to-data-source-synchronized.md)  
 <span data-ttu-id="4905e-127">Mostra come gestire l'evento <xref:System.Windows.Forms.BindingSource.BindingComplete> per assicurare che tutti i controlli associati a un'origine dati rimangano sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="4905e-127">Shows how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event to ensure all controls bound to a data source remain synchronized.</span></span>  
  
 [<span data-ttu-id="4905e-128">Procedura: Garantire che la riga selezionata in una tabella figlio rimanga nella posizione corretta</span><span class="sxs-lookup"><span data-stu-id="4905e-128">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>](ensure-the-selected-row-in-a-child-table-correct.md)  
 <span data-ttu-id="4905e-129">Mostra come garantire che la riga selezionata di una tabella figlio non venga modificata quando viene apportata una modifica a un campo della tabella padre.</span><span class="sxs-lookup"><span data-stu-id="4905e-129">Shows how to ensure the selected row of a child table does not change, when a change is made to a field of the parent table.</span></span>  
  
 <span data-ttu-id="4905e-130">Vedere anche [interfacce correlate all'associazione dati](interfaces-related-to-data-binding.md), [procedura: esplorare i dati in Windows Forms](how-to-navigate-data-in-windows-forms.md)e [procedura: creare un controllo con associazione semplice in un Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="4905e-130">Also see [Interfaces Related to Data Binding](interfaces-related-to-data-binding.md), [How to: Navigate Data in Windows Forms](how-to-navigate-data-in-windows-forms.md), and [How to: Create a Simple-Bound Control on a Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4905e-131">Riferimento</span><span class="sxs-lookup"><span data-stu-id="4905e-131">Reference</span></span>  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 <span data-ttu-id="4905e-132">Descrive la classe che rappresenta l'associazione tra un componente associabile e un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4905e-132">Describes the class that represents the binding between a bindable component and a data source.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 <span data-ttu-id="4905e-133">Descrive la classe che incapsula un'origine dati per l'associazione ai controlli.</span><span class="sxs-lookup"><span data-stu-id="4905e-133">Describes the class that encapsulates a data source for binding to controls.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4905e-134">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="4905e-134">Related Sections</span></span>  
 [<span data-ttu-id="4905e-135">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="4905e-135">BindingSource Component</span></span>](./controls/bindingsource-component.md)  
 <span data-ttu-id="4905e-136">Contiene un elenco di argomenti in cui viene illustrato come usare il componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="4905e-136">Contains a list of topics that demonstrate how to use the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="4905e-137">DataGridView (controllo)</span><span class="sxs-lookup"><span data-stu-id="4905e-137">DataGridView Control</span></span>](./controls/datagridview-control-windows-forms.md)  
 <span data-ttu-id="4905e-138">Fornisce un elenco di argomenti in cui viene illustrato come usare un controllo Datagrid associabile.</span><span class="sxs-lookup"><span data-stu-id="4905e-138">Provides a list of topics that demonstrate how to use a bindable datagrid control.</span></span>  
  
 <span data-ttu-id="4905e-139">Vedere anche [accesso ai dati in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="4905e-139">Also see [Accessing Data in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span></span>

---
title: Crea controllo che mostra lo stato di avanzamento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], progress tracking
- controls [Windows Forms], creating
- progress [Windows Forms], reporting [Windows Forms]
- FlashTrackBar custom control
ms.assetid: 24c5a2e3-058c-4b8d-a217-c06e6a130c2f
ms.openlocfilehash: 9d2cf353ba2309380221bb51733baaca1b81a5d5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731183"
---
# <a name="how-to-create-a-windows-forms-control-that-shows-progress"></a><span data-ttu-id="e3b88-102">Procedura: creare un controllo di Windows Form che visualizzi lo stato di avanzamento</span><span class="sxs-lookup"><span data-stu-id="e3b88-102">How to: Create a Windows Forms Control That Shows Progress</span></span>
<span data-ttu-id="e3b88-103">L'esempio di codice seguente visualizza un controllo personalizzato denominato `FlashTrackBar` che può essere usato per visualizzare all'utente il livello o lo stato di avanzamento di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e3b88-103">The following code example shows a custom control called `FlashTrackBar` that can be used to show the user the level or the progress of an application.</span></span> <span data-ttu-id="e3b88-104">Usa una sfumatura per rappresentare visivamente lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="e3b88-104">It uses a gradient to visually represent progress.</span></span>  
  
 <span data-ttu-id="e3b88-105">Il controllo `FlashTrackBar` illustra i concetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3b88-105">The `FlashTrackBar` control illustrates the following concepts:</span></span>  
  
- <span data-ttu-id="e3b88-106">Definizione di proprietà personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e3b88-106">Defining custom properties.</span></span>  
  
- <span data-ttu-id="e3b88-107">Definizione di eventi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e3b88-107">Defining custom events.</span></span> <span data-ttu-id="e3b88-108">(`FlashTrackBar` definisce l'evento `ValueChanged`.)</span><span class="sxs-lookup"><span data-stu-id="e3b88-108">(`FlashTrackBar` defines the `ValueChanged` event.)</span></span>  
  
- <span data-ttu-id="e3b88-109">Override del metodo <xref:System.Windows.Forms.Control.OnPaint%2A> per fornire la logica per creare il controllo.</span><span class="sxs-lookup"><span data-stu-id="e3b88-109">Overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method to provide logic to draw the control.</span></span>  
  
- <span data-ttu-id="e3b88-110">Calcolo dell'area disponibile per il disegno del controllo tramite la relativa proprietà <xref:System.Windows.Forms.Control.ClientRectangle%2A>.</span><span class="sxs-lookup"><span data-stu-id="e3b88-110">Computing the area available for drawing the control by using its <xref:System.Windows.Forms.Control.ClientRectangle%2A> property.</span></span> <span data-ttu-id="e3b88-111">`FlashTrackBar` esegue questa operazione nel relativo metodo `OptimizedInvalidate`.</span><span class="sxs-lookup"><span data-stu-id="e3b88-111">`FlashTrackBar` does this in its `OptimizedInvalidate` method.</span></span>  
  
- <span data-ttu-id="e3b88-112">Implementazione della serializzazione o del salvataggio permanente per una proprietà quando viene modificata nella Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="e3b88-112">Implementing serialization or persistence for a property when it is changed in the Windows Forms Designer.</span></span> <span data-ttu-id="e3b88-113">`FlashTrackBar` definisce i metodi `ShouldSerializeStartColor` e `ShouldSerializeEndColor` per la serializzazione delle relative proprietà `StartColor` e `EndColor`.</span><span class="sxs-lookup"><span data-stu-id="e3b88-113">`FlashTrackBar` defines the `ShouldSerializeStartColor` and `ShouldSerializeEndColor` methods for serializing its `StartColor` and `EndColor` properties.</span></span>  
  
 <span data-ttu-id="e3b88-114">La tabella seguente elenca le proprietà personalizzate definite da `FlashTrackBar`.</span><span class="sxs-lookup"><span data-stu-id="e3b88-114">The following table shows the custom properties defined by `FlashTrackBar`.</span></span>  
  
|<span data-ttu-id="e3b88-115">Gli</span><span class="sxs-lookup"><span data-stu-id="e3b88-115">Property</span></span>|<span data-ttu-id="e3b88-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3b88-116">Description</span></span>|  
|--------------|-----------------|  
|`AllowUserEdit`|<span data-ttu-id="e3b88-117">Indica se l'utente può modificare il valore del controllo FlashTrackBar tramite selezione e trascinamento.</span><span class="sxs-lookup"><span data-stu-id="e3b88-117">Indicates whether the user can change the value of the flash track bar by clicking and dragging it.</span></span>|  
|`EndColor`|<span data-ttu-id="e3b88-118">Specifica il colore finale della barra di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="e3b88-118">Specifies the ending color of the track bar.</span></span>|  
|`DarkenBy`|<span data-ttu-id="e3b88-119">Specifica di quanto scurire lo sfondo rispetto alla sfumatura di primo piano.</span><span class="sxs-lookup"><span data-stu-id="e3b88-119">Specifies how much to darken the background with respect to the foreground gradient.</span></span>|  
|`Max`|<span data-ttu-id="e3b88-120">Specifica il valore massimo della barra di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="e3b88-120">Specifies the maximum value of the track bar.</span></span>|  
|`Min`|<span data-ttu-id="e3b88-121">Specifica il valore minimo della barra di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="e3b88-121">Specifies the minimum value of the track bar.</span></span>|  
|`StartColor`|<span data-ttu-id="e3b88-122">Specifica il colore iniziale della sfumatura.</span><span class="sxs-lookup"><span data-stu-id="e3b88-122">Specifies the starting color of the gradient.</span></span>|  
|`ShowPercentage`|<span data-ttu-id="e3b88-123">Indica se visualizzare una percentuale sulla sfumatura.</span><span class="sxs-lookup"><span data-stu-id="e3b88-123">Indicates whether to display a percentage over the gradient.</span></span>|  
|`ShowValue`|<span data-ttu-id="e3b88-124">Indica se visualizzare il valore corrente sulla sfumatura.</span><span class="sxs-lookup"><span data-stu-id="e3b88-124">Indicates whether to display the current value over the gradient.</span></span>|  
|`ShowGradient`|<span data-ttu-id="e3b88-125">Indica se l'indicatore di avanzamento deve visualizzare una sfumatura di colore che indica il valore corrente.</span><span class="sxs-lookup"><span data-stu-id="e3b88-125">Indicates whether the track bar should display a color gradient showing the current value.</span></span>|  
|-   `Value`|<span data-ttu-id="e3b88-126">Specifica il valore corrente della barra di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="e3b88-126">Specifies the current value of the track bar.</span></span>|  
  
 <span data-ttu-id="e3b88-127">La tabella seguente elenca membri aggiuntivi definiti dalla proprietà `FlashTrackBar:`: l'evento proprietà modificata e il metodo che genera tale evento.</span><span class="sxs-lookup"><span data-stu-id="e3b88-127">The following table shows additional members defined by `FlashTrackBar:` the property-changed event and the method that raises the event.</span></span>  
  
|<span data-ttu-id="e3b88-128">Member</span><span class="sxs-lookup"><span data-stu-id="e3b88-128">Member</span></span>|<span data-ttu-id="e3b88-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3b88-129">Description</span></span>|  
|------------|-----------------|  
|`ValueChanged`|<span data-ttu-id="e3b88-130">L'evento generato quando viene modificata la proprietà `Value` della barra di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="e3b88-130">The event that is raised when the `Value` property of the track bar changes.</span></span>|  
|`OnValueChanged`|<span data-ttu-id="e3b88-131">Il metodo che genera l'evento `ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="e3b88-131">The method that raises the `ValueChanged` event.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="e3b88-132">`FlashTrackBar` usa la classe <xref:System.EventArgs> per i dati dell'evento e <xref:System.EventHandler> per il delegato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="e3b88-132">`FlashTrackBar` uses the <xref:System.EventArgs> class for event data and <xref:System.EventHandler> for the event delegate.</span></span>  
  
 <span data-ttu-id="e3b88-133">Per gestire gli eventi *EventName* corrispondenti, `FlashTrackBar` esegue l'override dei metodi seguenti ereditati da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="e3b88-133">To handle the corresponding *EventName* events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
- <xref:System.Windows.Forms.Control.OnPaint%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseDown%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseMove%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseUp%2A>  
  
- <xref:System.Windows.Forms.Control.OnResize%2A>  
  
 <span data-ttu-id="e3b88-134">Per gestire gli eventi di modifica di proprietà corrispondenti, `FlashTrackBar` esegue l'override dei metodi seguenti ereditati da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="e3b88-134">To handle the corresponding property-changed events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
- <xref:System.Windows.Forms.Control.OnBackColorChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnBackgroundImageChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnTextChanged%2A>  
  
## <a name="example"></a><span data-ttu-id="e3b88-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="e3b88-135">Example</span></span>  
 <span data-ttu-id="e3b88-136">Il controllo `FlashTrackBar` definisce due editor di tipi dell'interfaccia utente, `FlashTrackBarValueEditor` e `FlashTrackBarDarkenByEditor`, visualizzati negli elenchi di codice seguenti.</span><span class="sxs-lookup"><span data-stu-id="e3b88-136">The `FlashTrackBar` control defines two UI type editors, `FlashTrackBarValueEditor` and `FlashTrackBarDarkenByEditor`, which are shown in the following code listings.</span></span> <span data-ttu-id="e3b88-137">La classe `HostApp` usa il controllo `FlashTrackBar` in un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="e3b88-137">The `HostApp` class uses the `FlashTrackBar` control on a Windows Form.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#1)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#1)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarDarkenByEditor.cs#10)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarDarkenByEditor.vb#10)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarValueEditor.cs#20)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarValueEditor.vb#20)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/HostApp.cs#30)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/HostApp.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="e3b88-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3b88-138">See also</span></span>

- <span data-ttu-id="e3b88-139">[Estensione del supporto in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e3b88-139">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>
- [<span data-ttu-id="e3b88-140">Nozioni fondamentali sullo sviluppo di controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="e3b88-140">Windows Forms Control Development Basics</span></span>](windows-forms-control-development-basics.md)

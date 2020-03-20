---
title: Aggiunta di informazioni per l'Accesso facilitato ai controlli in un Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
ms.openlocfilehash: 672104db94826cfbe113a7ae0ea29546b0c3b9da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182004"
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a><span data-ttu-id="e9f43-102">Aggiunta di informazioni per l'Accesso facilitato ai controlli in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="e9f43-102">Providing Accessibility Information for Controls on a Windows Form</span></span>
<span data-ttu-id="e9f43-103">Gli strumenti per l'accessibilità sono dispositivi e programmi specializzati che consentono agli utenti con disabilità di usare i computer in modo più efficace.</span><span class="sxs-lookup"><span data-stu-id="e9f43-103">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span> <span data-ttu-id="e9f43-104">Sono incluse, ad esempio, le utilità per la lettura dello schermo per gli utenti non vedenti e le utilità di input vocale per le persone che usano i comandi vocali anziché il mouse o la tastiera.</span><span class="sxs-lookup"><span data-stu-id="e9f43-104">Examples include screen readers for people who are blind and voice input utilities for people who provide verbal commands instead of using the mouse or keyboard.</span></span> <span data-ttu-id="e9f43-105">Gli strumenti per l'accessibilità interagiscono con le proprietà di accessibilità esposte dai controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="e9f43-105">These accessibility aids interact with the accessibility properties exposed by Windows Forms controls.</span></span> <span data-ttu-id="e9f43-106">Le proprietà sono riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="e9f43-106">These properties are:</span></span>  
  
- <span data-ttu-id="e9f43-107">**AccessibilityObject**</span><span class="sxs-lookup"><span data-stu-id="e9f43-107">**AccessibilityObject**</span></span>  
  
- <span data-ttu-id="e9f43-108">**AccessibleDefaultActionDescription**</span><span class="sxs-lookup"><span data-stu-id="e9f43-108">**AccessibleDefaultActionDescription**</span></span>  
  
- <span data-ttu-id="e9f43-109">**AccessibleDescription**</span><span class="sxs-lookup"><span data-stu-id="e9f43-109">**AccessibleDescription**</span></span>  
  
- <span data-ttu-id="e9f43-110">**AccessibleName**</span><span class="sxs-lookup"><span data-stu-id="e9f43-110">**AccessibleName**</span></span>  
  
- <span data-ttu-id="e9f43-111">**AccessibleRole**</span><span class="sxs-lookup"><span data-stu-id="e9f43-111">**AccessibleRole**</span></span>  
  
## <a name="accessibilityobject-property"></a><span data-ttu-id="e9f43-112">Proprietà AccessibilityObject</span><span class="sxs-lookup"><span data-stu-id="e9f43-112">AccessibilityObject Property</span></span>  
 <span data-ttu-id="e9f43-113">Questa proprietà di sola lettura contiene un'istanza della <xref:System.Windows.Forms.AccessibleObject> .</span><span class="sxs-lookup"><span data-stu-id="e9f43-113">This read-only property contains an <xref:System.Windows.Forms.AccessibleObject> instance.</span></span> <span data-ttu-id="e9f43-114">**AccessibleObject** implementa l'interfaccia <xref:Accessibility.IAccessible> , che fornisce informazioni sulla descrizione del controllo, la posizione sullo schermo, le capacità di spostamento e il valore.</span><span class="sxs-lookup"><span data-stu-id="e9f43-114">The **AccessibleObject** implements the <xref:Accessibility.IAccessible> interface, which provides information about the control's description, screen location, navigational abilities, and value.</span></span> <span data-ttu-id="e9f43-115">La finestra di progettazione imposta questo valore quando il controllo viene aggiunto al form.</span><span class="sxs-lookup"><span data-stu-id="e9f43-115">The designer sets this value when the control is added to the form.</span></span>  
  
## <a name="accessibledefaultactiondescription-property"></a><span data-ttu-id="e9f43-116">Proprietà AccessibleDefaultActionDescription</span><span class="sxs-lookup"><span data-stu-id="e9f43-116">AccessibleDefaultActionDescription Property</span></span>  
 <span data-ttu-id="e9f43-117">Questa stringa descrive l'azione del controllo.</span><span class="sxs-lookup"><span data-stu-id="e9f43-117">This string describes the action of the control.</span></span> <span data-ttu-id="e9f43-118">Non è visualizzata nella finestra Proprietà e può essere impostata solo nel codice.</span><span class="sxs-lookup"><span data-stu-id="e9f43-118">It does not appear in the Properties window and may only be set in code.</span></span> <span data-ttu-id="e9f43-119">L'esempio seguente mostra come impostare questa proprietà per un pulsante:</span><span class="sxs-lookup"><span data-stu-id="e9f43-119">The following example sets this property for a button control:</span></span>  
  
```vb  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
```

```csharp  
Button1.AccessibleDefaultActionDescription =
   "Closes the application.";  
```

```cpp  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a><span data-ttu-id="e9f43-120">Proprietà AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="e9f43-120">AccessibleDescription Property</span></span>  
 <span data-ttu-id="e9f43-121">Questa stringa descrive il controllo.</span><span class="sxs-lookup"><span data-stu-id="e9f43-121">This string describes the control.</span></span> <span data-ttu-id="e9f43-122">Può essere impostata nella finestra Proprietà o nel codice, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e9f43-122">It may be set in the Properties window, or in code as follows:</span></span>  
  
```vb  
Button1.AccessibleDescription = "A button with text 'Exit'."  
```

```csharp  
Button1.AccessibleDescription = "A button with text 'Exit'";  
```

```cpp  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a><span data-ttu-id="e9f43-123">Proprietà AccessibleName</span><span class="sxs-lookup"><span data-stu-id="e9f43-123">AccessibleName Property</span></span>  
 <span data-ttu-id="e9f43-124">Questa stringa rappresenta il nome di un controllo segnalato agli strumenti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="e9f43-124">This is the name of a control reported to accessibility aids.</span></span> <span data-ttu-id="e9f43-125">Può essere impostata nella finestra Proprietà o nel codice, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e9f43-125">It may be set in the Properties window, or in code as follows:</span></span>  
  
```vb  
Button1.AccessibleName = "Order"  
```

```csharp  
Button1.AccessibleName = "Order";  
```

```cpp  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a><span data-ttu-id="e9f43-126">Proprietà AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="e9f43-126">AccessibleRole Property</span></span>  
 <span data-ttu-id="e9f43-127">Questa proprietà, che contiene una <xref:System.Windows.Forms.AccessibleRole> descrive il ruolo di interfaccia utente del controllo.</span><span class="sxs-lookup"><span data-stu-id="e9f43-127">This property, which contains an <xref:System.Windows.Forms.AccessibleRole> enumeration, describes the user interface role of the control.</span></span> <span data-ttu-id="e9f43-128">Per un nuovo controllo il valore è impostato su `Default`.</span><span class="sxs-lookup"><span data-stu-id="e9f43-128">A new control has the value set to `Default`.</span></span> <span data-ttu-id="e9f43-129">Ciò significa che, per impostazione predefinita, un controllo **Button** si comporta come un **pulsante**.</span><span class="sxs-lookup"><span data-stu-id="e9f43-129">This would mean that by default, a **Button** control acts as a **Button**.</span></span> <span data-ttu-id="e9f43-130">È consigliabile reimpostare questa proprietà se il controllo ha un altro ruolo.</span><span class="sxs-lookup"><span data-stu-id="e9f43-130">You may want to reset this property if a control has another role.</span></span> <span data-ttu-id="e9f43-131">Se, ad esempio, si usa un controllo **PictureBox** come un **grafico**, è possibile fare in modo che il ruolo venga segnalato come **Chart**anziché come **PictureBox**.</span><span class="sxs-lookup"><span data-stu-id="e9f43-131">For example, you may be using a **PictureBox** control as a **Chart**, and you may want accessibility aids to report the role as a **Chart**, not as a **PictureBox**.</span></span> <span data-ttu-id="e9f43-132">È anche consigliabile specificare questa proprietà per eventuali controlli personalizzati sviluppati.</span><span class="sxs-lookup"><span data-stu-id="e9f43-132">You may also want to specify this property for custom controls you have developed.</span></span> <span data-ttu-id="e9f43-133">La proprietà può essere impostata nella finestra Proprietà o nel codice, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e9f43-133">This property may be set in the Properties window, or in code as follows:</span></span>  
  
```vb
PictureBox1.AccessibleRole = AccessibleRole.Chart  
```

```csharp  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
```

```cpp  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9f43-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9f43-134">See also</span></span>

- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>

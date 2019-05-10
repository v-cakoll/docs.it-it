---
title: "Procedura dettagliata: Creazione di un'applicazione Windows ad accesso facilitato"
ms.date: 03/30/2017
helpviewer_keywords:
- accessibility [Windows Forms], Windows applications
- Windows applications [Windows Forms], accessibility
- applications [Windows Forms], accessibility
ms.assetid: 654c7f2f-1586-480b-9f12-9d9b8f5cc32b
ms.openlocfilehash: c324e4956d6db29e4de12bd7639a69daaf65d872
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665921"
---
# <a name="walkthrough-creating-an-accessible-windows-based-application"></a><span data-ttu-id="35350-102">Procedura dettagliata: Creazione di un'applicazione Windows ad accesso facilitato</span><span class="sxs-lookup"><span data-stu-id="35350-102">Walkthrough: Creating an Accessible Windows-based Application</span></span>
<span data-ttu-id="35350-103">La creazione di un'applicazione accessibile ha risvolti importanti per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="35350-103">Creating an accessible application has important business implications.</span></span> <span data-ttu-id="35350-104">Molti governi hanno norme relative all'accessibilità per l'acquisto del software.</span><span class="sxs-lookup"><span data-stu-id="35350-104">Many governments have accessibility regulations for software purchase.</span></span> <span data-ttu-id="35350-105">Il logo Certified for Windows include requisiti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="35350-105">The Certified for Windows logo includes accessibility requirements.</span></span> <span data-ttu-id="35350-106">È stato stimato che solo negli Stati Uniti risiedono 30 milioni di persone, molte delle quali potenziali clienti, interessate all'accessibilità del software.</span><span class="sxs-lookup"><span data-stu-id="35350-106">An estimated 30 million residents of the U.S. alone, many of them potential customers, are affected by the accessibility of software.</span></span>  
  
 <span data-ttu-id="35350-107">Questa procedura dettagliata illustra i cinque requisiti di accessibilità per il logo Certified for Windows.</span><span class="sxs-lookup"><span data-stu-id="35350-107">This walkthrough will address the five accessibility requirements for the Certified for Windows logo.</span></span> <span data-ttu-id="35350-108">In base a questi requisiti, un'applicazione accessibile deve:</span><span class="sxs-lookup"><span data-stu-id="35350-108">According to these requirements, an accessible application will:</span></span>  
  
- <span data-ttu-id="35350-109">Supportare le impostazioni di dimensioni, tipi di caratteri, colori e input del Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="35350-109">Support Control Panel size, color, font, and input settings.</span></span> <span data-ttu-id="35350-110">La barra dei menu, la barra del titolo, i bordi e la barra di stato verranno ridimensionati automaticamente quando l'utente modifica le impostazioni del Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="35350-110">The menu bar, title bar, borders, and status bar will all resize themselves when the user changes the control panel settings.</span></span> <span data-ttu-id="35350-111">In questa applicazione non sono necessarie altre modifiche ai controlli o al codice.</span><span class="sxs-lookup"><span data-stu-id="35350-111">No additional changes to the controls or code are required in this application.</span></span>  
  
- <span data-ttu-id="35350-112">Supportare la modalità contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="35350-112">Support High Contrast mode.</span></span>  
  
- <span data-ttu-id="35350-113">Fornire l'accesso da tastiera documentato a tutte le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="35350-113">Provide documented keyboard access to all features.</span></span>  
  
- <span data-ttu-id="35350-114">Esporre la posizione dello stato attivo della tastiera a livello visivo o di programmazione.</span><span class="sxs-lookup"><span data-stu-id="35350-114">Expose location of the keyboard focus visually and programmatically.</span></span>  
  
- <span data-ttu-id="35350-115">Evitare di comunicare informazioni importanti solo tramite segnali acustici.</span><span class="sxs-lookup"><span data-stu-id="35350-115">Avoid conveying important information by sound alone.</span></span>  
  
 <span data-ttu-id="35350-116">Per altre informazioni, vedere [Risorse per la progettazione di applicazioni accessibili](/visualstudio/ide/reference/resources-for-designing-accessible-applications).</span><span class="sxs-lookup"><span data-stu-id="35350-116">For more information, see [Resources for Designing Accessible Applications](/visualstudio/ide/reference/resources-for-designing-accessible-applications).</span></span>  
  
 <span data-ttu-id="35350-117">Per informazioni sul supporto di diversi layout di tastiera, vedere [Procedure consigliate per lo sviluppo di applicazioni internazionali](../../../standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).</span><span class="sxs-lookup"><span data-stu-id="35350-117">For information on supporting varying keyboard layouts, see [Best Practices for Developing World-Ready Applications](../../../standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="35350-118">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="35350-118">Creating the Project</span></span>  
 <span data-ttu-id="35350-119">Questa procedura dettagliata crea l'interfaccia utente per un'applicazione che accetta ordini di pizza.</span><span class="sxs-lookup"><span data-stu-id="35350-119">This walkthrough creates the user interface for an application that takes pizza orders.</span></span> <span data-ttu-id="35350-120">È costituita da un oggetto <xref:System.Windows.Forms.TextBox> per il nome del cliente, un gruppo di <xref:System.Windows.Forms.RadioButton> per selezionare la dimensione della pizza, un oggetto <xref:System.Windows.Forms.CheckedListBox> per selezionare i condimenti, due pulsanti con etichetta Order e Cancel e un menu con un comando Exit.</span><span class="sxs-lookup"><span data-stu-id="35350-120">It consists of a <xref:System.Windows.Forms.TextBox> for the customer's name, a <xref:System.Windows.Forms.RadioButton> group to select the pizza size, a <xref:System.Windows.Forms.CheckedListBox> for selecting the toppings, two Button controls labeled Order and Cancel, and a Menu with an Exit command.</span></span>  
  
 <span data-ttu-id="35350-121">L'utente immette il nome del cliente, la dimensione della pizza e gli ingredienti desiderati.</span><span class="sxs-lookup"><span data-stu-id="35350-121">The user enters the customer's name, the size of the pizza, and the toppings desired.</span></span> <span data-ttu-id="35350-122">Quando l'utente fa clic sul pulsante Order, in una finestra di messaggio vengono visualizzati un riepilogo dell'ordine e il costo. I controlli vengono cancellati e sono pronti per l'ordine successivo.</span><span class="sxs-lookup"><span data-stu-id="35350-122">When the user clicks the Order button, a summary of the order and its cost are displayed in a message box and the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="35350-123">Quando l'utente fa clic sul pulsante Cancel, i controlli vengono cancellati e sono pronti per l'ordine successivo.</span><span class="sxs-lookup"><span data-stu-id="35350-123">When the user clicks the Cancel button, the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="35350-124">Quando l'utente fa clic sulla voce di menu Exit, il programma si chiude.</span><span class="sxs-lookup"><span data-stu-id="35350-124">When the user clicks the Exit menu item, the program closes.</span></span>  
  
 <span data-ttu-id="35350-125">In questa procedura dettagliata l'elemento importante non è il codice per un sistema di ordini di vendita al dettaglio, ma l'accessibilità dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="35350-125">The emphasis of this walkthrough is not the code for a retail order system, but the accessibility of the user interface.</span></span> <span data-ttu-id="35350-126">La procedura dettagliata illustra le funzionalità di accessibilità di diversi controlli usati di frequente, tra cui pulsanti, pulsanti di opzione, caselle di testo ed etichette.</span><span class="sxs-lookup"><span data-stu-id="35350-126">The walkthrough demonstrates the accessibility features of several frequently used controls, including buttons, radio buttons, text boxes, and labels.</span></span>  
  
#### <a name="to-begin-making-the-application"></a><span data-ttu-id="35350-127">Per iniziare a creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="35350-127">To begin making the application</span></span>  
  
- <span data-ttu-id="35350-128">Creare una nuova applicazione Windows in Visual Basic o l'oggetto visivo C#.</span><span class="sxs-lookup"><span data-stu-id="35350-128">Create a new Windows Application in Visual Basic or Visual C#.</span></span> <span data-ttu-id="35350-129">Assegnare il nome **PizzaOrder** al progetto.</span><span class="sxs-lookup"><span data-stu-id="35350-129">Name the project **PizzaOrder**.</span></span> <span data-ttu-id="35350-130">Per i dettagli, vedere [Creazione di nuove soluzioni e progetti](/visualstudio/ide/creating-solutions-and-projects).</span><span class="sxs-lookup"><span data-stu-id="35350-130">(For details see [Creating New Solutions and Projects](/visualstudio/ide/creating-solutions-and-projects).)</span></span>  
  
## <a name="adding-the-controls-to-the-form"></a><span data-ttu-id="35350-131">Aggiunta dei controlli al form</span><span class="sxs-lookup"><span data-stu-id="35350-131">Adding the Controls to the Form</span></span>  
 <span data-ttu-id="35350-132">Quando si aggiungono i controlli a un form, tenere presenti le linee guida seguenti per creare un'applicazione accessibile:</span><span class="sxs-lookup"><span data-stu-id="35350-132">When adding the controls to a form, keep in mind the following guidelines to make an accessible application:</span></span>  
  
- <span data-ttu-id="35350-133">Impostare le proprietà <xref:System.Windows.Forms.Control.AccessibleDescription%2A> e <xref:System.Windows.Forms.Control.AccessibleName%2A>.</span><span class="sxs-lookup"><span data-stu-id="35350-133">Set the <xref:System.Windows.Forms.Control.AccessibleDescription%2A> and <xref:System.Windows.Forms.Control.AccessibleName%2A> properties.</span></span> <span data-ttu-id="35350-134">In questo esempio, l'impostazione predefinita per <xref:System.Windows.Forms.Control.AccessibleRole%2A> è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="35350-134">In this example, the Default setting for the <xref:System.Windows.Forms.Control.AccessibleRole%2A> is sufficient.</span></span> <span data-ttu-id="35350-135">Per altre informazioni sulle proprietà di accessibilità, vedere [Providing Accessibility Information for Controls on a Windows Form](../controls/providing-accessibility-information-for-controls-on-a-windows-form.md) (Specifica di informazioni di accessibilità per i controlli in un Windows Form).</span><span class="sxs-lookup"><span data-stu-id="35350-135">For more information on the accessibility properties, see [Providing Accessibility Information for Controls on a Windows Form](../controls/providing-accessibility-information-for-controls-on-a-windows-form.md).</span></span>  
  
- <span data-ttu-id="35350-136">Impostare le dimensioni del carattere su 10 o più punti.</span><span class="sxs-lookup"><span data-stu-id="35350-136">Set the font size to 10 points or larger.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35350-137">Se all'inizio si impostano le dimensioni del carattere del form su 10, tutti i controlli aggiunti successivamente al form avranno dimensioni del carattere pari a 10.</span><span class="sxs-lookup"><span data-stu-id="35350-137">If you set the font size of the form to 10 when you start, then all controls subsequently added to the form will have a font size of 10.</span></span>  
  
- <span data-ttu-id="35350-138">Assicurarsi che tutti i controlli etichetta che descrivono un controllo TextBox precedano immediatamente il controllo TextBox nell'ordine di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="35350-138">Make sure any Label control that describes a TextBox control immediately precedes the TextBox control in the tab order.</span></span>  
  
- <span data-ttu-id="35350-139">Aggiungere una chiave di accesso, usando il carattere "&", al <xref:System.Windows.Forms.Control.Text%2A> proprietà di qualsiasi controllo potrebbe essere necessario l'utente a cui passare.</span><span class="sxs-lookup"><span data-stu-id="35350-139">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of any control the user may want to navigate to.</span></span>  
  
- <span data-ttu-id="35350-140">Aggiungere una chiave di accesso, usando il carattere "&", al <xref:System.Windows.Forms.Control.Text%2A> proprietà dell'etichetta che precede un controllo che l'utente desidera spostarsi.</span><span class="sxs-lookup"><span data-stu-id="35350-140">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of the label that precedes a control that the user may want to navigate to.</span></span> <span data-ttu-id="35350-141">Impostare la proprietà <xref:System.Windows.Forms.Label.UseMnemonic%2A> delle etichette su `true`, in modo che lo stato attivo venga impostato sul controllo successivo nell'ordine di tabulazione quando l'utente preme il tasto di scelta.</span><span class="sxs-lookup"><span data-stu-id="35350-141">Set the labels' <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`, so that the focus is set to the next control in the tab order when the user presses the access key.</span></span>  
  
- <span data-ttu-id="35350-142">Aggiungere tasti di scelta a tutte le voci di menu.</span><span class="sxs-lookup"><span data-stu-id="35350-142">Add access keys to all menu items.</span></span>  
  
#### <a name="to-make-your-windows-application-accessible"></a><span data-ttu-id="35350-143">Per rendere accessibile l'applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="35350-143">To make your Windows Application accessible</span></span>  
  
- <span data-ttu-id="35350-144">Aggiungere i controlli al form e impostare le proprietà come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="35350-144">Add the controls to the form and set the properties as described below.</span></span> <span data-ttu-id="35350-145">Vedere l'immagine alla fine della tabella per un modello di come disporre i controlli nel form.</span><span class="sxs-lookup"><span data-stu-id="35350-145">See the picture at the end of the table for a model of how to arrange the controls on the form.</span></span>  
  
    |<span data-ttu-id="35350-146">Object</span><span class="sxs-lookup"><span data-stu-id="35350-146">Object</span></span>|<span data-ttu-id="35350-147">Proprietà</span><span class="sxs-lookup"><span data-stu-id="35350-147">Property</span></span>|<span data-ttu-id="35350-148">Value</span><span class="sxs-lookup"><span data-stu-id="35350-148">Value</span></span>|  
    |------------|--------------|-----------|  
    |<span data-ttu-id="35350-149">Form1</span><span class="sxs-lookup"><span data-stu-id="35350-149">Form1</span></span>|<span data-ttu-id="35350-150">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="35350-150">AccessibleDescription</span></span>|<span data-ttu-id="35350-151">Order form</span><span class="sxs-lookup"><span data-stu-id="35350-151">Order form</span></span>|  
    ||<span data-ttu-id="35350-152">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="35350-152">AccessibleName</span></span>|<span data-ttu-id="35350-153">Order form</span><span class="sxs-lookup"><span data-stu-id="35350-153">Order form</span></span>|  
    ||<span data-ttu-id="35350-154">Dimensione carattere</span><span class="sxs-lookup"><span data-stu-id="35350-154">Font Size</span></span>|<span data-ttu-id="35350-155">10</span><span class="sxs-lookup"><span data-stu-id="35350-155">10</span></span>|  
    ||<span data-ttu-id="35350-156">Testo</span><span class="sxs-lookup"><span data-stu-id="35350-156">Text</span></span>|<span data-ttu-id="35350-157">Pizza Order Form</span><span class="sxs-lookup"><span data-stu-id="35350-157">Pizza Order Form</span></span>|  
    |<span data-ttu-id="35350-158">PictureBox</span><span class="sxs-lookup"><span data-stu-id="35350-158">PictureBox</span></span>|<span data-ttu-id="35350-159">Nome</span><span class="sxs-lookup"><span data-stu-id="35350-159">Name</span></span>|<span data-ttu-id="35350-160">logo</span><span class="sxs-lookup"><span data-stu-id="35350-160">logo</span></span>|  
    ||<span data-ttu-id="35350-161">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="35350-161">AccessibleDescription</span></span>|<span data-ttu-id="35350-162">A slice of pizza</span><span class="sxs-lookup"><span data-stu-id="35350-162">A slice of pizza</span></span>|  
    ||<span data-ttu-id="35350-163">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="35350-163">AccessibleName</span></span>|<span data-ttu-id="35350-164">Company logo</span><span class="sxs-lookup"><span data-stu-id="35350-164">Company logo</span></span>|  
    ||<span data-ttu-id="35350-165">Image</span><span class="sxs-lookup"><span data-stu-id="35350-165">Image</span></span>|<span data-ttu-id="35350-166">Un'icona o una bitmap</span><span class="sxs-lookup"><span data-stu-id="35350-166">Any icon or bitmap</span></span>|  
    |<span data-ttu-id="35350-167">Label</span><span class="sxs-lookup"><span data-stu-id="35350-167">Label</span></span>|<span data-ttu-id="35350-168">Nome</span><span class="sxs-lookup"><span data-stu-id="35350-168">Name</span></span>|<span data-ttu-id="35350-169">companyLabel</span><span class="sxs-lookup"><span data-stu-id="35350-169">companyLabel</span></span>|  
    ||<span data-ttu-id="35350-170">Testo</span><span class="sxs-lookup"><span data-stu-id="35350-170">Text</span></span>|<span data-ttu-id="35350-171">Good Pizza</span><span class="sxs-lookup"><span data-stu-id="35350-171">Good Pizza</span></span>|  
    ||<span data-ttu-id="35350-172">TabIndex</span><span class="sxs-lookup"><span data-stu-id="35350-172">TabIndex</span></span>|<span data-ttu-id="35350-173">1</span><span class="sxs-lookup"><span data-stu-id="35350-173">1</span></span>|  
    ||<span data-ttu-id="35350-174">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="35350-174">AccessibleDescription</span></span>|<span data-ttu-id="35350-175">Company name</span><span class="sxs-lookup"><span data-stu-id="35350-175">Company name</span></span>|  
    ||<span data-ttu-id="35350-176">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="35350-176">AccessibleName</span></span>|<span data-ttu-id="35350-177">Company name</span><span class="sxs-lookup"><span data-stu-id="35350-177">Company name</span></span>|  
    ||<span data-ttu-id="35350-178">Backcolor</span><span class="sxs-lookup"><span data-stu-id="35350-178">Backcolor</span></span>|<span data-ttu-id="35350-179">Blu</span><span class="sxs-lookup"><span data-stu-id="35350-179">Blue</span></span>|  
    ||<span data-ttu-id="35350-180">Forecolor</span><span class="sxs-lookup"><span data-stu-id="35350-180">Forecolor</span></span>|<span data-ttu-id="35350-181">Giallo</span><span class="sxs-lookup"><span data-stu-id="35350-181">Yellow</span></span>|  
    ||<span data-ttu-id="35350-182">Dimensione carattere</span><span class="sxs-lookup"><span data-stu-id="35350-182">Font size</span></span>|<span data-ttu-id="35350-183">18</span><span class="sxs-lookup"><span data-stu-id="35350-183">18</span></span>|  
    |<span data-ttu-id="35350-184">Label</span><span class="sxs-lookup"><span data-stu-id="35350-184">Label</span></span>|<span data-ttu-id="35350-185">Nome</span><span class="sxs-lookup"><span data-stu-id="35350-185">Name</span></span>|<span data-ttu-id="35350-186">customerLabel</span><span class="sxs-lookup"><span data-stu-id="35350-186">customerLabel</span></span>|  
    ||<span data-ttu-id="35350-187">Testo</span><span class="sxs-lookup"><span data-stu-id="35350-187">Text</span></span>|<span data-ttu-id="35350-188">&Name</span><span class="sxs-lookup"><span data-stu-id="35350-188">&Name</span></span>|  
    ||<span data-ttu-id="35350-189">TabIndex</span><span class="sxs-lookup"><span data-stu-id="35350-189">TabIndex</span></span>|<span data-ttu-id="35350-190">2</span><span class="sxs-lookup"><span data-stu-id="35350-190">2</span></span>|  
    ||<span data-ttu-id="35350-191">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="35350-191">AccessibleDescription</span></span>|<span data-ttu-id="35350-192">Customer name label</span><span class="sxs-lookup"><span data-stu-id="35350-192">Customer name label</span></span>|  
    ||<span data-ttu-id="35350-193">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="35350-193">AccessibleName</span></span>|<span data-ttu-id="35350-194">Customer name label</span><span class="sxs-lookup"><span data-stu-id="35350-194">Customer name label</span></span>|  
    ||<span data-ttu-id="35350-195">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="35350-195">UseMnemonic</span></span>|<span data-ttu-id="35350-196">True</span><span class="sxs-lookup"><span data-stu-id="35350-196">True</span></span>|  
    |<span data-ttu-id="35350-197">TextBox</span><span class="sxs-lookup"><span data-stu-id="35350-197">TextBox</span></span>|<span data-ttu-id="35350-198">Nome</span><span class="sxs-lookup"><span data-stu-id="35350-198">Name</span></span>|<span data-ttu-id="35350-199">customerName</span><span class="sxs-lookup"><span data-stu-id="35350-199">customerName</span></span>|  
    ||<span data-ttu-id="35350-200">Testo</span><span class="sxs-lookup"><span data-stu-id="35350-200">Text</span></span>|<span data-ttu-id="35350-201">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="35350-201">(none)</span></span>|  
    ||<span data-ttu-id="35350-202">TabIndex</span><span class="sxs-lookup"><span data-stu-id="35350-202">TabIndex</span></span>|<span data-ttu-id="35350-203">3</span><span class="sxs-lookup"><span data-stu-id="35350-203">3</span></span>|  
    ||<span data-ttu-id="35350-204">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="35350-204">AccessibleDescription</span></span>|<span data-ttu-id="35350-205">Customer name</span><span class="sxs-lookup"><span data-stu-id="35350-205">Customer name</span></span>|  
    ||<span data-ttu-id="35350-206">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="35350-206">AccessibleName</span></span>|<span data-ttu-id="35350-207">Customer name</span><span class="sxs-lookup"><span data-stu-id="35350-207">Customer name</span></span>|  
    |<span data-ttu-id="35350-208">GroupBox</span><span class="sxs-lookup"><span data-stu-id="35350-208">GroupBox</span></span>|<span data-ttu-id="35350-209">Nome</span><span class="sxs-lookup"><span data-stu-id="35350-209">Name</span></span>|<span data-ttu-id="35350-210">sizeOptions</span><span class="sxs-lookup"><span data-stu-id="35350-210">sizeOptions</span></span>|  
    ||<span data-ttu-id="35350-211">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="35350-211">AccessibleDescription</span></span>|<span data-ttu-id="35350-212">Pizza size options</span><span class="sxs-lookup"><span data-stu-id="35350-212">Pizza size options</span></span>|  
    ||<span data-ttu-id="35350-213">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="35350-213">AccessibleName</span></span>|<span data-ttu-id="35350-214">Pizza size options</span><span class="sxs-lookup"><span data-stu-id="35350-214">Pizza size options</span></span>|  
    ||<span data-ttu-id="35350-215">Testo</span><span class="sxs-lookup"><span data-stu-id="35350-215">Text</span></span>|<span data-ttu-id="35350-216">Pizza size</span><span class="sxs-lookup"><span data-stu-id="35350-216">Pizza size</span></span>|  
    ||<span data-ttu-id="35350-217">TabIndex</span><span class="sxs-lookup"><span data-stu-id="35350-217">TabIndex</span></span>|<span data-ttu-id="35350-218">4</span><span class="sxs-lookup"><span data-stu-id="35350-218">4</span></span>|  
    |<span data-ttu-id="35350-219">RadioButton</span><span class="sxs-lookup"><span data-stu-id="35350-219">RadioButton</span></span>|<span data-ttu-id="35350-220">Nome</span><span class="sxs-lookup"><span data-stu-id="35350-220">Name</span></span>|<span data-ttu-id="35350-221">smallPizza</span><span class="sxs-lookup"><span data-stu-id="35350-221">smallPizza</span></span>|  
    ||<span data-ttu-id="35350-222">Testo</span><span class="sxs-lookup"><span data-stu-id="35350-222">Text</span></span>|<span data-ttu-id="35350-223">&Small $6.00</span><span class="sxs-lookup"><span data-stu-id="35350-223">&Small $6.00</span></span>|  
    ||<span data-ttu-id="35350-224">Selezionato</span><span class="sxs-lookup"><span data-stu-id="35350-224">Checked</span></span>|<span data-ttu-id="35350-225">True</span><span class="sxs-lookup"><span data-stu-id="35350-225">True</span></span>|  
    ||<span data-ttu-id="35350-226">TabIndex</span><span class="sxs-lookup"><span data-stu-id="35350-226">TabIndex</span></span>|<span data-ttu-id="35350-227">0</span><span class="sxs-lookup"><span data-stu-id="35350-227">0</span></span>|  
    ||<span data-ttu-id="35350-228">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="35350-228">AccessibleDescription</span></span>|<span data-ttu-id="35350-229">Small pizza</span><span class="sxs-lookup"><span data-stu-id="35350-229">Small pizza</span></span>|  
    ||<span data-ttu-id="35350-230">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="35350-230">AccessibleName</span></span>|<span data-ttu-id="35350-231">Small pizza</span><span class="sxs-lookup"><span data-stu-id="35350-231">Small pizza</span></span>|  
    |<span data-ttu-id="35350-232">RadioButton</span><span class="sxs-lookup"><span data-stu-id="35350-232">RadioButton</span></span>|<span data-ttu-id="35350-233">Nome</span><span class="sxs-lookup"><span data-stu-id="35350-233">Name</span></span>|<span data-ttu-id="35350-234">largePizza</span><span class="sxs-lookup"><span data-stu-id="35350-234">largePizza</span></span>|  
    ||<span data-ttu-id="35350-235">Testo</span><span class="sxs-lookup"><span data-stu-id="35350-235">Text</span></span>|<span data-ttu-id="35350-236">&Large $10.00</span><span class="sxs-lookup"><span data-stu-id="35350-236">&Large $10.00</span></span>|  
    ||<span data-ttu-id="35350-237">TabIndex</span><span class="sxs-lookup"><span data-stu-id="35350-237">TabIndex</span></span>|<span data-ttu-id="35350-238">1</span><span class="sxs-lookup"><span data-stu-id="35350-238">1</span></span>|  
    ||<span data-ttu-id="35350-239">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="35350-239">AccessibleDescription</span></span>|<span data-ttu-id="35350-240">Large pizza</span><span class="sxs-lookup"><span data-stu-id="35350-240">Large pizza</span></span>|  
    ||<span data-ttu-id="35350-241">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="35350-241">AccessibleName</span></span>|<span data-ttu-id="35350-242">Large pizza</span><span class="sxs-lookup"><span data-stu-id="35350-242">Large pizza</span></span>|  
    |<span data-ttu-id="35350-243">Label</span><span class="sxs-lookup"><span data-stu-id="35350-243">Label</span></span>|<span data-ttu-id="35350-244">Nome</span><span class="sxs-lookup"><span data-stu-id="35350-244">Name</span></span>|<span data-ttu-id="35350-245">toppingsLabel</span><span class="sxs-lookup"><span data-stu-id="35350-245">toppingsLabel</span></span>|  
    ||<span data-ttu-id="35350-246">Testo</span><span class="sxs-lookup"><span data-stu-id="35350-246">Text</span></span>|<span data-ttu-id="35350-247">&Toppings ($0.75 each)</span><span class="sxs-lookup"><span data-stu-id="35350-247">&Toppings ($0.75 each)</span></span>|  
    ||<span data-ttu-id="35350-248">TabIndex</span><span class="sxs-lookup"><span data-stu-id="35350-248">TabIndex</span></span>|<span data-ttu-id="35350-249">5</span><span class="sxs-lookup"><span data-stu-id="35350-249">5</span></span>|  
    ||<span data-ttu-id="35350-250">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="35350-250">AccessibleDescription</span></span>|<span data-ttu-id="35350-251">Toppings label</span><span class="sxs-lookup"><span data-stu-id="35350-251">Toppings label</span></span>|  
    ||<span data-ttu-id="35350-252">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="35350-252">AccessibleName</span></span>|<span data-ttu-id="35350-253">Toppings label</span><span class="sxs-lookup"><span data-stu-id="35350-253">Toppings label</span></span>|  
    ||<span data-ttu-id="35350-254">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="35350-254">UseMnemonic</span></span>|<span data-ttu-id="35350-255">True</span><span class="sxs-lookup"><span data-stu-id="35350-255">True</span></span>|  
    |<span data-ttu-id="35350-256">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="35350-256">CheckedListBox</span></span>|<span data-ttu-id="35350-257">Nome</span><span class="sxs-lookup"><span data-stu-id="35350-257">Name</span></span>|<span data-ttu-id="35350-258">toppings</span><span class="sxs-lookup"><span data-stu-id="35350-258">toppings</span></span>|  
    ||<span data-ttu-id="35350-259">TabIndex</span><span class="sxs-lookup"><span data-stu-id="35350-259">TabIndex</span></span>|<span data-ttu-id="35350-260">6</span><span class="sxs-lookup"><span data-stu-id="35350-260">6</span></span>|  
    ||<span data-ttu-id="35350-261">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="35350-261">AccessibleDescription</span></span>|<span data-ttu-id="35350-262">Available toppings</span><span class="sxs-lookup"><span data-stu-id="35350-262">Available toppings</span></span>|  
    ||<span data-ttu-id="35350-263">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="35350-263">AccessibleName</span></span>|<span data-ttu-id="35350-264">Available toppings</span><span class="sxs-lookup"><span data-stu-id="35350-264">Available toppings</span></span>|  
    ||<span data-ttu-id="35350-265">Elementi</span><span class="sxs-lookup"><span data-stu-id="35350-265">Items</span></span>|<span data-ttu-id="35350-266">Pepperoni, Sausage, Mushrooms</span><span class="sxs-lookup"><span data-stu-id="35350-266">Pepperoni, Sausage, Mushrooms</span></span>|  
    |<span data-ttu-id="35350-267">Button</span><span class="sxs-lookup"><span data-stu-id="35350-267">Button</span></span>|<span data-ttu-id="35350-268">Nome</span><span class="sxs-lookup"><span data-stu-id="35350-268">Name</span></span>|<span data-ttu-id="35350-269">order</span><span class="sxs-lookup"><span data-stu-id="35350-269">order</span></span>|  
    ||<span data-ttu-id="35350-270">Testo</span><span class="sxs-lookup"><span data-stu-id="35350-270">Text</span></span>|<span data-ttu-id="35350-271">&Ordina</span><span class="sxs-lookup"><span data-stu-id="35350-271">&Order</span></span>|  
    ||<span data-ttu-id="35350-272">TabIndex</span><span class="sxs-lookup"><span data-stu-id="35350-272">TabIndex</span></span>|<span data-ttu-id="35350-273">7</span><span class="sxs-lookup"><span data-stu-id="35350-273">7</span></span>|  
    ||<span data-ttu-id="35350-274">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="35350-274">AccessibleDescription</span></span>|<span data-ttu-id="35350-275">Total the order</span><span class="sxs-lookup"><span data-stu-id="35350-275">Total the order</span></span>|  
    ||<span data-ttu-id="35350-276">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="35350-276">AccessibleName</span></span>|<span data-ttu-id="35350-277">Total order</span><span class="sxs-lookup"><span data-stu-id="35350-277">Total order</span></span>|  
    |<span data-ttu-id="35350-278">Button</span><span class="sxs-lookup"><span data-stu-id="35350-278">Button</span></span>|<span data-ttu-id="35350-279">Nome</span><span class="sxs-lookup"><span data-stu-id="35350-279">Name</span></span>|<span data-ttu-id="35350-280">cancel</span><span class="sxs-lookup"><span data-stu-id="35350-280">cancel</span></span>|  
    ||<span data-ttu-id="35350-281">Testo</span><span class="sxs-lookup"><span data-stu-id="35350-281">Text</span></span>|<span data-ttu-id="35350-282">An&nulla</span><span class="sxs-lookup"><span data-stu-id="35350-282">&Cancel</span></span>|  
    ||<span data-ttu-id="35350-283">TabIndex</span><span class="sxs-lookup"><span data-stu-id="35350-283">TabIndex</span></span>|<span data-ttu-id="35350-284">8</span><span class="sxs-lookup"><span data-stu-id="35350-284">8</span></span>|  
    ||<span data-ttu-id="35350-285">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="35350-285">AccessibleDescription</span></span>|<span data-ttu-id="35350-286">Cancel the order</span><span class="sxs-lookup"><span data-stu-id="35350-286">Cancel the order</span></span>|  
    ||<span data-ttu-id="35350-287">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="35350-287">AccessibleName</span></span>|<span data-ttu-id="35350-288">Cancel order</span><span class="sxs-lookup"><span data-stu-id="35350-288">Cancel order</span></span>|  
    |<span data-ttu-id="35350-289">MainMenu</span><span class="sxs-lookup"><span data-stu-id="35350-289">MainMenu</span></span>|<span data-ttu-id="35350-290">Nome</span><span class="sxs-lookup"><span data-stu-id="35350-290">Name</span></span>|<span data-ttu-id="35350-291">theMainMenu</span><span class="sxs-lookup"><span data-stu-id="35350-291">theMainMenu</span></span>|  
    |<span data-ttu-id="35350-292">MenuItem</span><span class="sxs-lookup"><span data-stu-id="35350-292">MenuItem</span></span>|<span data-ttu-id="35350-293">Nome</span><span class="sxs-lookup"><span data-stu-id="35350-293">Name</span></span>|<span data-ttu-id="35350-294">fileCommands</span><span class="sxs-lookup"><span data-stu-id="35350-294">fileCommands</span></span>|  
    ||<span data-ttu-id="35350-295">Testo</span><span class="sxs-lookup"><span data-stu-id="35350-295">Text</span></span>|<span data-ttu-id="35350-296">&File</span><span class="sxs-lookup"><span data-stu-id="35350-296">&File</span></span>|  
    |<span data-ttu-id="35350-297">MenuItem</span><span class="sxs-lookup"><span data-stu-id="35350-297">MenuItem</span></span>|<span data-ttu-id="35350-298">Nome</span><span class="sxs-lookup"><span data-stu-id="35350-298">Name</span></span>|<span data-ttu-id="35350-299">exitApp</span><span class="sxs-lookup"><span data-stu-id="35350-299">exitApp</span></span>|  
    ||<span data-ttu-id="35350-300">Testo</span><span class="sxs-lookup"><span data-stu-id="35350-300">Text</span></span>|<span data-ttu-id="35350-301">&Esci</span><span class="sxs-lookup"><span data-stu-id="35350-301">E&xit</span></span>|
    
      Your form will look something like the following image:
    
      ![The pizza order form with a name textbox, and size and toppings selection.](./media/walkthrough-creating-an-accessible-windows-based-application/visual-basic-pizza-order-form.gif)  

## <a name="supporting-high-contrast-mode"></a><span data-ttu-id="35350-302">Supporto della modalità contrasto elevato</span><span class="sxs-lookup"><span data-stu-id="35350-302">Supporting High Contrast Mode</span></span>  
 <span data-ttu-id="35350-303">La modalità contrasto elevato è un'impostazione di sistema di Windows che migliora la leggibilità usando colori a contrasto e dimensioni del carattere che agevolano gli utenti con problemi di vista.</span><span class="sxs-lookup"><span data-stu-id="35350-303">High Contrast mode is a Windows system setting that improves readability by using contrasting colors and font sizes that are beneficial for visually impaired users.</span></span> <span data-ttu-id="35350-304">Il <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> proprietà viene fornita per determinare se è impostata la modalità contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="35350-304">The <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> property is provided to determine whether the High Contrast mode is set.</span></span>  
  
 <span data-ttu-id="35350-305">Se SystemInformation.HighContrast è `true`, l'applicazione dovrebbe:</span><span class="sxs-lookup"><span data-stu-id="35350-305">If SystemInformation.HighContrast is `true`, the application should:</span></span>  
  
- <span data-ttu-id="35350-306">Visualizzare tutti gli elementi dell'interfaccia utente con la combinazione colori di sistema.</span><span class="sxs-lookup"><span data-stu-id="35350-306">Display all user interface elements using the system color scheme</span></span>  
  
- <span data-ttu-id="35350-307">Comunicare tramite segnali visivi o acustici tutte le informazioni comunicate mediante il colore.</span><span class="sxs-lookup"><span data-stu-id="35350-307">Convey by visual cues or sound any information that is conveyed through color.</span></span> <span data-ttu-id="35350-308">Ad esempio, se determinati elementi elenco vengono evidenziati usando un tipo di carattere rosso, è possibile aggiungere al tipo di carattere anche il grassetto, in modo che l'utente veda un segnale non basato sul colore, indicante che gli elementi sono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="35350-308">For example, if particular list items are highlighted by using a red font, you could also add bold to the font, so that the user has a non-color cue that the items are highlighted.</span></span>  
  
- <span data-ttu-id="35350-309">Evitare di inserire immagini o motivi dietro il testo.</span><span class="sxs-lookup"><span data-stu-id="35350-309">Omit any images or patterns behind text</span></span>  
  
 <span data-ttu-id="35350-310">All'avvio l'applicazione dovrebbe controllare l'impostazione di <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> e rispondere all'evento di sistema <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span><span class="sxs-lookup"><span data-stu-id="35350-310">The application should check the setting of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> when the application starts and respond to the system event <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span></span> <span data-ttu-id="35350-311">L'evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> viene generato ogni volta che il valore di <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> cambia.</span><span class="sxs-lookup"><span data-stu-id="35350-311">The <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event is raised whenever the value of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> changes.</span></span>  
  
 <span data-ttu-id="35350-312">Nell'applicazione l'unico elemento che non usa le impostazioni di sistema per il colore è `lblCompanyName`.</span><span class="sxs-lookup"><span data-stu-id="35350-312">In our application, the only element that is not using the system settings for color is `lblCompanyName`.</span></span> <span data-ttu-id="35350-313">Il <xref:System.Drawing.SystemColors> classe viene utilizzata per modificare le impostazioni colore dell'etichetta con i colori di sistema selezionati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="35350-313">The <xref:System.Drawing.SystemColors> class is used to change the color settings of the label to the user-selected system colors.</span></span>  
  
#### <a name="to-enable-high-contrast-mode-in-an-effective-way"></a><span data-ttu-id="35350-314">Per abilitare la modalità contrasto elevato in modo efficace</span><span class="sxs-lookup"><span data-stu-id="35350-314">To enable High Contrast mode in an effective way</span></span>  
  
1. <span data-ttu-id="35350-315">Creare un metodo per impostare i colori dell'etichetta sui colori di sistema.</span><span class="sxs-lookup"><span data-stu-id="35350-315">Create a method to set the colors of the label to the system colors.</span></span>  
  
    ```  
    ' Visual Basic  
    Private Sub SetColorScheme()  
       If SystemInformation.HighContrast Then  
          companyLabel.BackColor = SystemColors.Window  
          companyLabel.ForeColor = SystemColors.WindowText  
       Else  
          companyLabel.BackColor = Color.Blue  
          companyLabel.ForeColor = Color.Yellow  
       End If  
    End Sub  
  
    // C#  
    private void SetColorScheme()  
    {  
       if (SystemInformation.HighContrast)  
       {  
          companyLabel.BackColor = SystemColors.Window;  
          companyLabel.ForeColor = SystemColors.WindowText;  
       }  
       else  
       {  
          companyLabel.BackColor = Color.Blue;  
          companyLabel.ForeColor = Color.Yellow;  
       }  
    }  
    ```  
  
2. <span data-ttu-id="35350-316">Chiamare la routine `SetColorScheme`nel costruttore del form (`Public Sub New()` in Visual Basic e `public class Form1` in Visual C#).</span><span class="sxs-lookup"><span data-stu-id="35350-316">Call the `SetColorScheme` procedure in the form constructor (`Public Sub New()` in Visual Basic and `public class Form1` in Visual C#).</span></span> <span data-ttu-id="35350-317">Per accedere al costruttore in Visual Basic, sarà necessario espandere l'area con l'etichetta **Codice generato da Progettazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="35350-317">To access the constructor in Visual Basic, you will need to expand the region labeled **Windows Form Designer generated code**.</span></span>  
  
    ```  
    ' Visual Basic   
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
    }  
    ```  
  
3. <span data-ttu-id="35350-318">Creare una routine evento, con la firma appropriata, per rispondere all'evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span><span class="sxs-lookup"><span data-stu-id="35350-318">Create an event procedure, with the appropriate signature, to respond to the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event.</span></span>  
  
    ```  
    ' Visual Basic  
    Protected Sub UserPreferenceChanged(ByVal sender As Object, _  
    ByVal e As Microsoft.Win32.UserPreferenceChangedEventArgs)  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public void UserPreferenceChanged(object sender,   
    Microsoft.Win32.UserPreferenceChangedEventArgs e)  
    {  
       SetColorScheme();  
    }  
    ```  
  
4. <span data-ttu-id="35350-319">Aggiungere il codice al costruttore del form, dopo la chiamata a `InitializeComponents`, per associare la routine evento all'evento di sistema.</span><span class="sxs-lookup"><span data-stu-id="35350-319">Add code to the form constructor, after the call to `InitializeComponents`, to hook up the event procedure to the system event.</span></span> <span data-ttu-id="35350-320">Questo metodo chiama la routine `SetColorScheme`.</span><span class="sxs-lookup"><span data-stu-id="35350-320">This method calls the `SetColorScheme` procedure.</span></span>  
  
    ```  
    ' Visual Basic  
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
       AddHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          += new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
    }  
    ```  
  
5. <span data-ttu-id="35350-321">Aggiungere il codice al metodo <xref:System.Windows.Forms.Control.Dispose%2A> del form, prima della chiamata al metodo <xref:System.Windows.Forms.Control.Dispose%2A> della classe base, per rilasciare l'evento quando l'applicazione si chiude.</span><span class="sxs-lookup"><span data-stu-id="35350-321">Add code to the form <xref:System.Windows.Forms.Control.Dispose%2A> method, before the call to the <xref:System.Windows.Forms.Control.Dispose%2A> method of the base class, to release the event when the application closes.</span></span> <span data-ttu-id="35350-322">Per accedere al metodo <xref:System.Windows.Forms.Control.Dispose%2A> in Visual Basic, sarà necessario espandere l'area con l'etichetta Codice generato da Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="35350-322">To access the <xref:System.Windows.Forms.Control.Dispose%2A> method in Visual Basic, you will need to expand the region labeled Windows Form Designer generated code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35350-323">Il codice dell'evento di sistema esegue un thread separato dall'applicazione principale.</span><span class="sxs-lookup"><span data-stu-id="35350-323">The system event code runs a thread separate from the main application.</span></span> <span data-ttu-id="35350-324">Se non si rilascia l'evento, il codice associato all'evento verrà eseguito anche dopo la chiusura del programma.</span><span class="sxs-lookup"><span data-stu-id="35350-324">If you do not release the event, the code that you hook up to the event will run even after the program is closed.</span></span>  
  
    ```  
    ' Visual Basic  
    Protected Overloads Overrides Sub Dispose(ByVal disposing As Boolean)  
       If disposing Then  
          If Not (components Is Nothing) Then  
             components.Dispose()  
          End If  
       End If  
       RemoveHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
       MyBase.Dispose(disposing)  
    End Sub  
  
    // C#  
    protected override void Dispose( bool disposing )  
    {  
       if( disposing )  
       {  
          if (components != null)   
          {  
             components.Dispose();  
          }  
       }  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          -= new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
       base.Dispose( disposing );  
    }  
    ```  
  
6. <span data-ttu-id="35350-325">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="35350-325">Press F5 to run the application.</span></span>  
  
## <a name="conveying-important-information-by-means-other-than-sound"></a><span data-ttu-id="35350-326">Comunicazione di informazioni importanti con mezzi diversi dai segnali acustici.</span><span class="sxs-lookup"><span data-stu-id="35350-326">Conveying Important Information by Means Other Than Sound</span></span>  
 <span data-ttu-id="35350-327">In questa applicazione, nessuna informazione viene comunicata solo mediante segnali acustici.</span><span class="sxs-lookup"><span data-stu-id="35350-327">In this application, no information is conveyed by sound alone.</span></span> <span data-ttu-id="35350-328">Se si usano i segnagli acustici nell'applicazione, è necessario comunicare le informazioni anche con altri mezzi.</span><span class="sxs-lookup"><span data-stu-id="35350-328">If you use sound in your application, then you should supply the information by some other means as well.</span></span>  
  
#### <a name="to-supply-information-by-some-other-means-than-sound"></a><span data-ttu-id="35350-329">Per fornire informazioni con mezzi diversi dai segnali acustici</span><span class="sxs-lookup"><span data-stu-id="35350-329">To supply information by some other means than sound</span></span>  
  
1. <span data-ttu-id="35350-330">Far lampeggiare la barra del titolo usando la funzione FlashWindow dell'API Windows.</span><span class="sxs-lookup"><span data-stu-id="35350-330">Make the title bar flash by using the Windows API function FlashWindow.</span></span> <span data-ttu-id="35350-331">Per un esempio di come chiamare funzioni API Windows, vedere [procedura dettagliata: Chiamata delle API di Windows](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).</span><span class="sxs-lookup"><span data-stu-id="35350-331">For an example of how to call Windows API functions, see [Walkthrough: Calling Windows APIs](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35350-332">L'utente potrebbe aver abilitato il servizio Segnali visivi di Windows, che farà lampeggiare la finestra anche quando i suoni di sistema vengono riprodotti tramite l'altoparlante predefinito del computer.</span><span class="sxs-lookup"><span data-stu-id="35350-332">The user may have the Windows SoundSentry service enabled, which will also cause the window to flash when the system sounds are played through the computer's built-in speaker.</span></span>  
  
2. <span data-ttu-id="35350-333">Visualizzare le informazioni importanti in una finestra non modale in modo che l'utente rispondere a esse.</span><span class="sxs-lookup"><span data-stu-id="35350-333">Display the important information in a non-modal window so that the user may respond to it.</span></span>  
  
3. <span data-ttu-id="35350-334">Visualizzare una finestra di messaggio che acquisisce lo stato attivo della tastiera.</span><span class="sxs-lookup"><span data-stu-id="35350-334">Display a message box that acquires the keyboard focus.</span></span> <span data-ttu-id="35350-335">Evitare questo metodo se è possibile che l'utente stia digitando.</span><span class="sxs-lookup"><span data-stu-id="35350-335">Avoid this method when the user may be typing.</span></span>  
  
4. <span data-ttu-id="35350-336">Visualizzare un indicatore di stato nell'area di notifica dello stato della barra delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="35350-336">Display a status indicator in the status notification area of the taskbar.</span></span> <span data-ttu-id="35350-337">Per i dettagli, vedere [Aggiunta di icone alla barra delle applicazioni mediante il componente NotifyIcon di Windows Form](../controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span><span class="sxs-lookup"><span data-stu-id="35350-337">For details, see [Adding Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](../controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="35350-338">Verifica dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="35350-338">Testing the Application</span></span>  
 <span data-ttu-id="35350-339">Prima di distribuire l'applicazione, è consigliabile testare le funzionalità di accessibilità implementate.</span><span class="sxs-lookup"><span data-stu-id="35350-339">Before deploying the application, you should test the accessibility features that you have implemented.</span></span>  
  
#### <a name="to-test-accessibility-features"></a><span data-ttu-id="35350-340">Per testare le funzionalità di accessibilità</span><span class="sxs-lookup"><span data-stu-id="35350-340">To test accessibility features</span></span>  
  
1. <span data-ttu-id="35350-341">Per testare l'accesso tramite tastiera, scollegare il mouse ed esplorare l'interfaccia utente per ogni funzionalità solo con la tastiera.</span><span class="sxs-lookup"><span data-stu-id="35350-341">To test keyboard access, unplug the mouse and navigate the user interface for each feature using only the keyboard.</span></span> <span data-ttu-id="35350-342">Assicurarsi che tutte le attività possano essere eseguite solo con la tastiera.</span><span class="sxs-lookup"><span data-stu-id="35350-342">Ensure that all tasks may be performed using the keyboard only.</span></span>  
  
2. <span data-ttu-id="35350-343">Per testare il supporto del contrasto elevato, scegliere l'icona Accesso facilitato nel Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="35350-343">To test support of High Contrast, choose the Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="35350-344">Fare clic sulla scheda Schermo e selezionare la casella di controllo Usa Contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="35350-344">Click the Display tab and select the Use High Contrast check box.</span></span> <span data-ttu-id="35350-345">Spostarsi tra tutti gli elementi dell'interfaccia utente per verificare che siano state applicate le modifiche al colore e al tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="35350-345">Navigate through all user interface elements to ensure that the color and font changes are reflected.</span></span> <span data-ttu-id="35350-346">Assicurarsi anche non siano state inserite immagini o motivi dietro il testo.</span><span class="sxs-lookup"><span data-stu-id="35350-346">Also, ensure that images or patterns drawn behind text are omitted.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35350-347">Windows NT 4 non dispone dell'icona Accesso facilitato nel Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="35350-347">Windows NT 4 does not have an Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="35350-348">Quindi questa procedura per cambiare l'impostazione SystemInformation.HighContrast non funziona in Windows NT 4.</span><span class="sxs-lookup"><span data-stu-id="35350-348">Thus, this procedure for changing the SystemInformation.HighContrast setting does not work in Windows NT 4.</span></span>  
  
3. <span data-ttu-id="35350-349">Per testare l'accessibilità di un'applicazione, sono facilmente disponibili altri strumenti.</span><span class="sxs-lookup"><span data-stu-id="35350-349">Other tools are readily available for testing the accessibility of an application.</span></span>  
  
4. <span data-ttu-id="35350-350">Per testare l'esposizione dello stato attivo della tastiera, eseguire Lente di ingrandimento.</span><span class="sxs-lookup"><span data-stu-id="35350-350">To test exposing the keyboard focus, run Magnifier.</span></span> <span data-ttu-id="35350-351">Per aprirla, fare clic sul menu **Start**, scegliere **Programmi**, **Accessori**, **Accessibilità**, quindi fare clic su **Lente di ingrandimento**.</span><span class="sxs-lookup"><span data-stu-id="35350-351">(To open it, click the **Start** menu, point to **Programs**, point to **Accessories**, point to **Accessibility**, and then click **Magnifier**).</span></span> <span data-ttu-id="35350-352">Spostarsi nell'interfaccia utente usando sia il mouse che il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="35350-352">Navigate the user interface using both keyboard tabbing and the mouse.</span></span> <span data-ttu-id="35350-353">Assicurarsi che tutti gli spostamenti vengano registrati correttamente in **Lente di ingrandimento**.</span><span class="sxs-lookup"><span data-stu-id="35350-353">Ensure that all navigation is tracked properly in **Magnifier**.</span></span>  
  
5. <span data-ttu-id="35350-354">Per testare l'esposizione degli elementi dello schermo, eseguire Controlla e usare sia il mouse che il tasto TAB per raggiungere ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="35350-354">To test exposing screen elements, run Inspect, and use both the mouse and the TAB key to reach each element.</span></span> <span data-ttu-id="35350-355">Assicurarsi che le informazioni presentate nei campi Nome, Stato, Ruolo, Posizione e Valore della finestra Controlla abbiano senso per l'utente per ogni oggetto dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="35350-355">Ensure that the information presented in the Name, State, Role, Location, and Value fields of the Inspect window is meaningful to the user for each object in the UI.</span></span>

---
title: Controllo RichTextBox (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text boxes
- RichTextBox control [Windows Forms]
- rich edit controls
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 80621a12a4ccd5008a0331af005629d45f60abdf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="1d54e-102">Controllo RichTextBox (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="1d54e-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="1d54e-103">Windows Form `RichTextBox` controllo viene utilizzato per la visualizzazione, l'immissione e la modifica del testo con formattazione.</span><span class="sxs-lookup"><span data-stu-id="1d54e-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="1d54e-104">Il `RichTextBox` controllo esegue tutto il <xref:System.Windows.Forms.TextBox> dal controllo, ma può anche visualizzare i tipi di carattere, colori e collegamenti; caricare testo e immagini incorporate da un file; rollback e rollforward; operazioni di modifica e trovare i caratteri specificati.</span><span class="sxs-lookup"><span data-stu-id="1d54e-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="1d54e-105">Il `RichTextBox` controllo viene in genere utilizzato per fornire funzionalità simili alle applicazioni di elaborazione di testi, ad esempio Microsoft Word di visualizzazione e modifica di testo.</span><span class="sxs-lookup"><span data-stu-id="1d54e-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="1d54e-106">Come il <xref:System.Windows.Forms.TextBox> (controllo), il `RichTextBox` controllo può visualizzare le barre di scorrimento; ma a differenza di <xref:System.Windows.Forms.TextBox> (controllo), Visualizza le barre di scorrimento orizzontali e verticali per impostazione predefinita e quali fornisce impostazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="1d54e-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1d54e-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1d54e-107">In This Section</span></span>  
 [<span data-ttu-id="1d54e-108">Panoramica sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="1d54e-108">RichTextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="1d54e-109">Introduce i concetti generali relativi il `RichTextBox` controllo, che consente agli utenti di immettere, visualizzare e modificare il testo con le opzioni di formattazione.</span><span class="sxs-lookup"><span data-stu-id="1d54e-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="1d54e-110">Procedura: Individuare le modifiche degli attributi di formattazione nel controllo RichTextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1d54e-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="1d54e-111">Viene illustrato come tenere traccia delle modifiche nel tipo di carattere e paragrafo la formattazione di `RichTextBox` controllo.</span><span class="sxs-lookup"><span data-stu-id="1d54e-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="1d54e-112">Procedura: Visualizzare le barre di scorrimento nel controllo RichTextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1d54e-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="1d54e-113">Vengono descritte le numerose opzioni disponibili per le barre di scorrimento nel `RichTextBox` controllo.</span><span class="sxs-lookup"><span data-stu-id="1d54e-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="1d54e-114">Procedura: Visualizzare collegamenti ipertestuali con il controllo RichTextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1d54e-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="1d54e-115">Viene illustrato come inserire collegamenti a siti Web di `RichTextBox` controllo.</span><span class="sxs-lookup"><span data-stu-id="1d54e-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="1d54e-116">Procedura: Abilitare operazioni di trascinamento con il controllo RichTextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1d54e-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="1d54e-117">Vengono fornite istruzioni per il trascinamento dei dati nel `RichTextBox` controllo.</span><span class="sxs-lookup"><span data-stu-id="1d54e-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="1d54e-118">Procedura: Caricare file nel controllo RichTextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1d54e-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="1d54e-119">Vengono fornite istruzioni per il caricamento di un file esistente nel `RichTextBox` controllo.</span><span class="sxs-lookup"><span data-stu-id="1d54e-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="1d54e-120">Procedura: Salvare file con il controllo RichTextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1d54e-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="1d54e-121">Vengono fornite istruzioni per salvare il contenuto di `RichTextBox` controllo in un file.</span><span class="sxs-lookup"><span data-stu-id="1d54e-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="1d54e-122">Procedura: Impostare gli attributi dei caratteri per il controllo RichTextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1d54e-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="1d54e-123">Viene descritto come impostare la famiglia di caratteri, dimensioni, stile e colore del testo di `RichTextBox` controllo.</span><span class="sxs-lookup"><span data-stu-id="1d54e-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="1d54e-124">Procedura: Impostare rientri, rientri sporgenti e paragrafi puntati con il controllo RichTextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1d54e-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="1d54e-125">Viene descritto come formattare i paragrafi di `RichTextBox` controllo.</span><span class="sxs-lookup"><span data-stu-id="1d54e-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1d54e-126">Riferimento</span><span class="sxs-lookup"><span data-stu-id="1d54e-126">Reference</span></span>  
 <span data-ttu-id="1d54e-127">Classe <xref:System.Windows.Forms.RichTextBox></span><span class="sxs-lookup"><span data-stu-id="1d54e-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="1d54e-128">Descrive la classe e fornisce i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="1d54e-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1d54e-129">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="1d54e-129">Related Sections</span></span>  
 [<span data-ttu-id="1d54e-130">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="1d54e-130">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="1d54e-131">Fornisce un elenco completo dei controlli Windows Form, con collegamenti alle informazioni sul relativo uso.</span><span class="sxs-lookup"><span data-stu-id="1d54e-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="1d54e-132">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="1d54e-132">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)  
 <span data-ttu-id="1d54e-133">Introduce i concetti generali relativi il <xref:System.Windows.Forms.TextBox> controllo, che consente l'input su più righe modificabile dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1d54e-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>

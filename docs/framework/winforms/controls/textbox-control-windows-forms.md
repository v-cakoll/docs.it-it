---
title: Controllo TextBox (Windows Form)
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
- TextBox control [Windows Forms]
ms.assetid: e5a06987-8aec-4271-b196-2245ba992d62
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d606140a5be2b1770bc5a16159e96e20b0fccdd9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="textbox-control-windows-forms"></a><span data-ttu-id="17838-102">Controllo TextBox (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="17838-102">TextBox Control (Windows Forms)</span></span>
<span data-ttu-id="17838-103">Caselle di testo di Windows Form vengono utilizzate per ottenere l'input dell'utente o per visualizzare il testo.</span><span class="sxs-lookup"><span data-stu-id="17838-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="17838-104">Il `TextBox` controllo viene in genere utilizzato per il testo modificabile, anche se può inoltre essere resa di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="17838-104">The `TextBox` control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="17838-105">Caselle di testo possono visualizzare più righe, a capo automatico per le dimensioni del controllo e aggiungere la formattazione di base.</span><span class="sxs-lookup"><span data-stu-id="17838-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="17838-106">Il `TextBox` controllo consente a un singolo formato per il testo visualizzato o inserito nel controllo.</span><span class="sxs-lookup"><span data-stu-id="17838-106">The `TextBox` control allows a single format for text displayed or entered in the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17838-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="17838-107">In This Section</span></span>  
 [<span data-ttu-id="17838-108">Cenni preliminari sul controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="17838-108">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 <span data-ttu-id="17838-109">Definisce il controllo e ne illustra le funzionalità chiave e le proprietà.</span><span class="sxs-lookup"><span data-stu-id="17838-109">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="17838-110">Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="17838-110">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 <span data-ttu-id="17838-111">Vengono fornite indicazioni per la specifica in cui il punto di inserimento viene visualizzato quando un controllo di modifica Ottiene lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="17838-111">Gives directions for specifying where the insertion point appears when an edit control first gets the focus.</span></span>  
  
 [<span data-ttu-id="17838-112">Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="17838-112">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="17838-113">Viene descritto come nascondere digitato nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="17838-113">Explains how to conceal what is typed into a text box.</span></span>  
  
 [<span data-ttu-id="17838-114">Procedura: Creare una casella di testo in sola lettura</span><span class="sxs-lookup"><span data-stu-id="17838-114">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 <span data-ttu-id="17838-115">Viene descritto come impedire che venga modificato il contenuto di una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="17838-115">Describes how to prevent the contents of a text box from being changed.</span></span>  
  
 [<span data-ttu-id="17838-116">Procedura: Inserire virgolette in una stringa</span><span class="sxs-lookup"><span data-stu-id="17838-116">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 <span data-ttu-id="17838-117">Illustra l'aggiunta di virgolette in una stringa in una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="17838-117">Explains adding quotation marks to a string in a text box.</span></span>  
  
 [<span data-ttu-id="17838-118">Procedura: Selezionare testo nel controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="17838-118">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="17838-119">Viene illustrato come evidenziare il testo in una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="17838-119">Explains how to highlight text in a text box.</span></span>  
  
 [<span data-ttu-id="17838-120">Procedura: Visualizzare più righe nel controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="17838-120">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="17838-121">Viene descritto come creare una casella di testo scorrevole.</span><span class="sxs-lookup"><span data-stu-id="17838-121">Describes how to make a text box scrollable.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="17838-122">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="17838-122">Reference</span></span>  
 <span data-ttu-id="17838-123">Classe <xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="17838-123"><xref:System.Windows.Forms.TextBox> class</span></span>  
 <span data-ttu-id="17838-124">Descrive la classe e fornisce i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="17838-124">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="17838-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="17838-125">Related Sections</span></span>  
 [<span data-ttu-id="17838-126">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="17838-126">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="17838-127">Fornisce un elenco completo dei controlli Windows Form, con collegamenti alle informazioni sul relativo uso.</span><span class="sxs-lookup"><span data-stu-id="17838-127">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>

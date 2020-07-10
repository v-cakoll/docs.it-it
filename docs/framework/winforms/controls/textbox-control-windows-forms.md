---
title: Controllo TextBox
description: Vengono fornite informazioni sui vari aspetti del controllo TextBox Windows Forms, incluso l'utilizzo per il testo modificabile e per renderlo di sola lettura.
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- TextBox control [Windows Forms]
ms.assetid: e5a06987-8aec-4271-b196-2245ba992d62
ms.openlocfilehash: 026f6d2653e41dabd3db7490660b6ce19846d397
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174445"
---
# <a name="textbox-control-windows-forms"></a><span data-ttu-id="859f4-103">Controllo TextBox (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="859f4-103">TextBox Control (Windows Forms)</span></span>
<span data-ttu-id="859f4-104">Windows Forms caselle di testo vengono utilizzate per ottenere l'input dall'utente o per visualizzare il testo.</span><span class="sxs-lookup"><span data-stu-id="859f4-104">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="859f4-105">Il `TextBox` controllo viene in genere usato per testo modificabile, anche se può essere reso di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="859f4-105">The `TextBox` control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="859f4-106">Le caselle di testo possono visualizzare più righe, eseguire il wrapping del testo sulle dimensioni del controllo e aggiungere la formattazione di base.</span><span class="sxs-lookup"><span data-stu-id="859f4-106">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="859f4-107">Il `TextBox` controllo consente di visualizzare o immettere un singolo formato per il testo nel controllo.</span><span class="sxs-lookup"><span data-stu-id="859f4-107">The `TextBox` control allows a single format for text displayed or entered in the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="859f4-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="859f4-108">In This Section</span></span>  
 [<span data-ttu-id="859f4-109">Cenni preliminari sul controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="859f4-109">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)  
 <span data-ttu-id="859f4-110">Definisce il controllo e ne illustra le funzionalità chiave e le proprietà.</span><span class="sxs-lookup"><span data-stu-id="859f4-110">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="859f4-111">Procedura: controllare il punto di inserimento in un controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="859f4-111">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 <span data-ttu-id="859f4-112">Fornisce indicazioni per specificare dove viene visualizzato il punto di inserimento quando un controllo di modifica ottiene prima lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="859f4-112">Gives directions for specifying where the insertion point appears when an edit control first gets the focus.</span></span>  
  
 [<span data-ttu-id="859f4-113">Procedura: creare una casella di testo Password con il controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="859f4-113">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="859f4-114">Viene illustrato come nascondere le informazioni digitate in una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="859f4-114">Explains how to conceal what is typed into a text box.</span></span>  
  
 [<span data-ttu-id="859f4-115">Procedura: creare una casella di testo in sola lettura</span><span class="sxs-lookup"><span data-stu-id="859f4-115">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)  
 <span data-ttu-id="859f4-116">Viene descritto come impedire la modifica del contenuto di una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="859f4-116">Describes how to prevent the contents of a text box from being changed.</span></span>  
  
 [<span data-ttu-id="859f4-117">Procedura: inserire virgolette in una stringa</span><span class="sxs-lookup"><span data-stu-id="859f4-117">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 <span data-ttu-id="859f4-118">Viene illustrata l'aggiunta di virgolette a una stringa in una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="859f4-118">Explains adding quotation marks to a string in a text box.</span></span>  
  
 [<span data-ttu-id="859f4-119">Procedura: selezionare testo nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="859f4-119">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="859f4-120">Viene illustrato come evidenziare il testo in una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="859f4-120">Explains how to highlight text in a text box.</span></span>  
  
 [<span data-ttu-id="859f4-121">Procedura: visualizzare più righe nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="859f4-121">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="859f4-122">Viene descritto come rendere scorrevole una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="859f4-122">Describes how to make a text box scrollable.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="859f4-123">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="859f4-123">Reference</span></span>  
 <span data-ttu-id="859f4-124">Classe <xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="859f4-124"><xref:System.Windows.Forms.TextBox> class</span></span>  
 <span data-ttu-id="859f4-125">Descrive la classe e fornisce i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="859f4-125">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="859f4-126">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="859f4-126">Related Sections</span></span>  
 [<span data-ttu-id="859f4-127">Controlli da utilizzare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="859f4-127">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="859f4-128">Fornisce un elenco completo dei controlli Windows Form, con collegamenti alle informazioni sul relativo uso.</span><span class="sxs-lookup"><span data-stu-id="859f4-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>

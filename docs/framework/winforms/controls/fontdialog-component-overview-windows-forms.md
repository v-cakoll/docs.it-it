---
title: Panoramica del componente FontDialog
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 664b756dc068ca283e4f43edbdd0f3266f5d1142
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745698"
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="983ef-102">Cenni preliminari sul componente FontDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="983ef-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="983ef-103">Il componente Windows Forms <xref:System.Windows.Forms.FontDialog> è una finestra di dialogo preconfigurata, ovvero la finestra di dialogo **tipo di carattere** Windows standard utilizzata per esporre i tipi di carattere attualmente installati nel sistema.</span><span class="sxs-lookup"><span data-stu-id="983ef-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="983ef-104">Utilizzarlo all'interno dell'applicazione basata su Windows come soluzione semplice per la selezione dei tipi di carattere anziché configurare la propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="983ef-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="983ef-105">Per impostazione predefinita, nella finestra di dialogo vengono visualizzate le caselle di riepilogo per tipo di carattere, stile del carattere e dimensioni; caselle di controllo per gli effetti quali l'attacco e la sottolineatura; elenco a discesa per lo script; e un esempio di come verrà visualizzato il tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="983ef-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="983ef-106">(Lo script fa riferimento a script di caratteri diversi disponibili per un tipo di carattere specifico, ad esempio ebraico o giapponese). Per visualizzare la finestra di dialogo tipo di carattere, chiamare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="983ef-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="983ef-107">Proprietà chiave</span><span class="sxs-lookup"><span data-stu-id="983ef-107">Key Properties</span></span>  
 <span data-ttu-id="983ef-108">Il componente dispone di una serie di proprietà che ne configurano l'aspetto.</span><span class="sxs-lookup"><span data-stu-id="983ef-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="983ef-109">Le proprietà che impostano le selezioni della finestra di dialogo sono <xref:System.Windows.Forms.FontDialog.Font%2A> e <xref:System.Windows.Forms.FontDialog.Color%2A>.</span><span class="sxs-lookup"><span data-stu-id="983ef-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="983ef-110">La proprietà <xref:System.Windows.Forms.FontDialog.Font%2A> imposta il tipo di carattere, lo stile, le dimensioni, lo script e gli effetti; ad esempio, `Arial, 10pt, style=Italic, Strikeout`.</span><span class="sxs-lookup"><span data-stu-id="983ef-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="983ef-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="983ef-111">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="983ef-112">Componente FontDialog</span><span class="sxs-lookup"><span data-stu-id="983ef-112">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)

---
title: Cenni preliminari sul componente FontDialog (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 7f140807bf4b42e530302190042e729c59248e7f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098559"
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="7bbdd-102">Cenni preliminari sul componente FontDialog (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="7bbdd-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="7bbdd-103">I moduli di Windows <xref:System.Windows.Forms.FontDialog> componente è una finestra di dialogo preconfigurata, ovvero il Windows standard **Font** finestra di dialogo utilizzata per esporre i tipi di carattere attualmente installati nel sistema.</span><span class="sxs-lookup"><span data-stu-id="7bbdd-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="7bbdd-104">Usarlo all'interno dell'applicazione basata su Windows come una soluzione semplice per la selezione del tipo di carattere anziché configurare una propria finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7bbdd-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="7bbdd-105">Per impostazione predefinita, la finestra di dialogo Mostra le caselle di riepilogo per tipo di carattere, stile e dimensioni. ad esempio caselle di controllo per gli effetti barrato e sottolineato; un elenco di riepilogo a discesa per Script. e un esempio del modo in cui verrà visualizzato il tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="7bbdd-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="7bbdd-106">(Lo script fa riferimento agli script di caratteri diversi che sono disponibili per un determinato tipo di carattere, ad esempio, giapponese o ebraica.) Per visualizzare la finestra di dialogo tipo di carattere, chiamare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="7bbdd-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="7bbdd-107">Proprietà chiave</span><span class="sxs-lookup"><span data-stu-id="7bbdd-107">Key Properties</span></span>  
 <span data-ttu-id="7bbdd-108">Il componente ha numerose proprietà che consentono di configurare l'aspetto del controllo.</span><span class="sxs-lookup"><span data-stu-id="7bbdd-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="7bbdd-109">Le proprietà impostare le selezioni di finestra di dialogo sono <xref:System.Windows.Forms.FontDialog.Font%2A> e <xref:System.Windows.Forms.FontDialog.Color%2A>.</span><span class="sxs-lookup"><span data-stu-id="7bbdd-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="7bbdd-110">Il <xref:System.Windows.Forms.FontDialog.Font%2A> proprietà imposta il tipo di carattere, stile, dimensione, script ed effetti; ad esempio, `Arial, 10pt, style=Italic, Strikeout`.</span><span class="sxs-lookup"><span data-stu-id="7bbdd-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bbdd-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bbdd-111">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="7bbdd-112">Componente FontDialog</span><span class="sxs-lookup"><span data-stu-id="7bbdd-112">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)

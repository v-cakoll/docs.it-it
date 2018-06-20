---
title: Visualizzazione di caratteri asiatici mediante la proprietà ImeMode
ms.date: 03/30/2017
helpviewer_keywords:
- Asian languages [Windows Forms], displaying with ImeMode
- Chinese characters [Windows Forms], displaying with ImeMode
- IME mode
- Japanese characters [Windows Forms], displaying with ImeMode
- international applications [Windows Forms], character display
- international characters
- Korean characters
- Asian languages
- Input Method Editor (IME), mode
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
ms.openlocfilehash: d3733f642d4218c851040582ee5637b5486a7804
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208630"
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a><span data-ttu-id="a5c20-102">Visualizzazione di caratteri asiatici mediante la proprietà ImeMode</span><span class="sxs-lookup"><span data-stu-id="a5c20-102">Display of Asian Characters with the ImeMode Property</span></span>
<span data-ttu-id="a5c20-103">Il <xref:System.Windows.Forms.Control.ImeMode%2A> proprietà viene utilizzata per i form e controlli per forzare una modalità specifica per un input method editor (IME).</span><span class="sxs-lookup"><span data-stu-id="a5c20-103">The <xref:System.Windows.Forms.Control.ImeMode%2A> property is used by forms and controls to force a specific mode for an input method editor (IME).</span></span> <span data-ttu-id="a5c20-104">L'IME è un componente essenziale per la creazione di script in cinese, giapponese e coreano, perché questi sistemi di scrittura comprendono più caratteri che possono essere codificati per una normale tastiera.</span><span class="sxs-lookup"><span data-stu-id="a5c20-104">The IME is an essential component for writing Chinese, Japanese, and Korean scripts, since these writing systems have more characters than can be encoded for a regular keyboard.</span></span> <span data-ttu-id="a5c20-105">È possibile, ad esempio, consentire solo caratteri ASCII in una particolare casella di testo.</span><span class="sxs-lookup"><span data-stu-id="a5c20-105">For example, you may want to allow only ASCII characters in a particular text box.</span></span> <span data-ttu-id="a5c20-106">In questo caso è possibile impostare il <xref:System.Windows.Forms.Control.ImeMode%2A> proprietà <xref:System.Windows.Forms.ImeMode> e gli utenti potranno solo immettere caratteri ASCII per la casella di testo.</span><span class="sxs-lookup"><span data-stu-id="a5c20-106">In such a case you can set the <xref:System.Windows.Forms.Control.ImeMode%2A> property to <xref:System.Windows.Forms.ImeMode> and users will only be able to enter ASCII characters for that particular text box.</span></span> <span data-ttu-id="a5c20-107">Il valore predefinito di <xref:System.Windows.Forms.Control.ImeMode%2A> proprietà <xref:System.Windows.Forms.ImeMode>, pertanto se si imposta la proprietà per un form, tutti i controlli nel form erediteranno questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="a5c20-107">The default value of the <xref:System.Windows.Forms.Control.ImeMode%2A> property is <xref:System.Windows.Forms.ImeMode>, so if you set the property for a form, all controls on the form will inherit that setting.</span></span> <span data-ttu-id="a5c20-108">Per ulteriori informazioni, vedere <xref:System.Windows.Forms.Control.ImeMode%2A> ) e <xref:System.Windows.Forms.ImeMode>.</span><span class="sxs-lookup"><span data-stu-id="a5c20-108">For more information, see <xref:System.Windows.Forms.Control.ImeMode%2A> ) and <xref:System.Windows.Forms.ImeMode>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5c20-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5c20-109">See also</span></span>

[<span data-ttu-id="a5c20-110">Globalizzazione di applicazioni Windows Form</span><span class="sxs-lookup"><span data-stu-id="a5c20-110">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)

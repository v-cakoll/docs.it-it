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
ms.openlocfilehash: 25602e1a878443bd54411dfd6481581abebda5c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755480"
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a><span data-ttu-id="c12cd-102">Visualizzazione di caratteri asiatici mediante la proprietà ImeMode</span><span class="sxs-lookup"><span data-stu-id="c12cd-102">Display of Asian Characters with the ImeMode Property</span></span>
<span data-ttu-id="c12cd-103">Il <xref:System.Windows.Forms.Control.ImeMode%2A> proprietà viene usata da form e controlli per forzare una modalità specifica per un input method editor (IME).</span><span class="sxs-lookup"><span data-stu-id="c12cd-103">The <xref:System.Windows.Forms.Control.ImeMode%2A> property is used by forms and controls to force a specific mode for an input method editor (IME).</span></span> <span data-ttu-id="c12cd-104">L'IME è un componente essenziale per la creazione di script in cinese, giapponese e coreano, perché questi sistemi di scrittura comprendono più caratteri che possono essere codificati per una normale tastiera.</span><span class="sxs-lookup"><span data-stu-id="c12cd-104">The IME is an essential component for writing Chinese, Japanese, and Korean scripts, since these writing systems have more characters than can be encoded for a regular keyboard.</span></span> <span data-ttu-id="c12cd-105">È possibile, ad esempio, consentire solo caratteri ASCII in una particolare casella di testo.</span><span class="sxs-lookup"><span data-stu-id="c12cd-105">For example, you may want to allow only ASCII characters in a particular text box.</span></span> <span data-ttu-id="c12cd-106">In tal caso è possibile impostare il <xref:System.Windows.Forms.Control.ImeMode%2A> proprietà <xref:System.Windows.Forms.ImeMode> e gli utenti potranno solo immettere caratteri ASCII per quel particolare casella di testo.</span><span class="sxs-lookup"><span data-stu-id="c12cd-106">In such a case you can set the <xref:System.Windows.Forms.Control.ImeMode%2A> property to <xref:System.Windows.Forms.ImeMode> and users will only be able to enter ASCII characters for that particular text box.</span></span> <span data-ttu-id="c12cd-107">Il valore predefinito di <xref:System.Windows.Forms.Control.ImeMode%2A> è di proprietà <xref:System.Windows.Forms.ImeMode>, pertanto se si imposta la proprietà per un form, tutti i controlli sul form erediteranno tale impostazione.</span><span class="sxs-lookup"><span data-stu-id="c12cd-107">The default value of the <xref:System.Windows.Forms.Control.ImeMode%2A> property is <xref:System.Windows.Forms.ImeMode>, so if you set the property for a form, all controls on the form will inherit that setting.</span></span> <span data-ttu-id="c12cd-108">Per altre informazioni, vedere <xref:System.Windows.Forms.Control.ImeMode%2A> ) e <xref:System.Windows.Forms.ImeMode>.</span><span class="sxs-lookup"><span data-stu-id="c12cd-108">For more information, see <xref:System.Windows.Forms.Control.ImeMode%2A> ) and <xref:System.Windows.Forms.ImeMode>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c12cd-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c12cd-109">See also</span></span>

- [<span data-ttu-id="c12cd-110">Globalizzazione di applicazioni Windows Form</span><span class="sxs-lookup"><span data-stu-id="c12cd-110">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)

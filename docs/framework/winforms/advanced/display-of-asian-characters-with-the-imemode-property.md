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
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500521"
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a>Visualizzazione di caratteri asiatici mediante la proprietà ImeMode
Il <xref:System.Windows.Forms.Control.ImeMode%2A> proprietà viene usata da form e controlli per forzare una modalità specifica per un input method editor (IME). L'IME è un componente essenziale per la creazione di script in cinese, giapponese e coreano, perché questi sistemi di scrittura comprendono più caratteri che possono essere codificati per una normale tastiera. È possibile, ad esempio, consentire solo caratteri ASCII in una particolare casella di testo. In tal caso è possibile impostare il <xref:System.Windows.Forms.Control.ImeMode%2A> proprietà <xref:System.Windows.Forms.ImeMode> e gli utenti potranno solo immettere caratteri ASCII per quel particolare casella di testo. Il valore predefinito di <xref:System.Windows.Forms.Control.ImeMode%2A> è di proprietà <xref:System.Windows.Forms.ImeMode>, pertanto se si imposta la proprietà per un form, tutti i controlli sul form erediteranno tale impostazione. Per altre informazioni, vedere <xref:System.Windows.Forms.Control.ImeMode%2A> ) e <xref:System.Windows.Forms.ImeMode>.  
  
## <a name="see-also"></a>Vedere anche

- [Globalizzazione di applicazioni Windows Form](globalizing-windows-forms.md)

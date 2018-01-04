---
title: "Visualizzazione di caratteri asiatici mediante la proprietà ImeMode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5971fd9a75f936d2ec63eea6a086c681ec996652
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a>Visualizzazione di caratteri asiatici mediante la proprietà ImeMode
Il <xref:System.Windows.Forms.Control.ImeMode%2A> proprietà viene utilizzata per i form e controlli per forzare una modalità specifica per un input method editor (IME). L'IME è un componente essenziale per la creazione di script in cinese, giapponese e coreano, perché questi sistemi di scrittura comprendono più caratteri che possono essere codificati per una normale tastiera. È possibile, ad esempio, consentire solo caratteri ASCII in una particolare casella di testo. In questo caso è possibile impostare il <xref:System.Windows.Forms.Control.ImeMode%2A> proprietà <xref:System.Windows.Forms.ImeMode> e gli utenti potranno solo immettere caratteri ASCII per la casella di testo. Il valore predefinito di <xref:System.Windows.Forms.Control.ImeMode%2A> proprietà <xref:System.Windows.Forms.ImeMode>, pertanto se si imposta la proprietà per un form, tutti i controlli nel form erediteranno questa impostazione. Per ulteriori informazioni, vedere <xref:System.Windows.Forms.Control.ImeMode%2A> ) e <xref:System.Windows.Forms.ImeMode>.  
  
## <a name="see-also"></a>Vedere anche  
 [Globalizzazione di Windows Form](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)

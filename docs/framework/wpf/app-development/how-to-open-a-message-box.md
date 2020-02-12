---
title: 'Procedura: apertura di una finestra di messaggio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: bd2c4dce78e46163eb4628cb3aab829fc0173edf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123727"
---
# <a name="how-to-open-a-message-box"></a>Procedura: apertura di una finestra di messaggio
In questo esempio viene illustrato come aprire una finestra di messaggio.  
  
## <a name="example"></a>Esempio  
 Una finestra di messaggio è una finestra di dialogo modale prefabbricata per la visualizzazione di informazioni agli utenti. Viene aperta una finestra di messaggio chiamando il metodo statico <xref:System.Windows.MessageBox.Show%2A> della classe <xref:System.Windows.MessageBox>. Quando <xref:System.Windows.MessageBox.Show%2A> viene chiamato, il messaggio viene passato utilizzando un parametro di stringa. Diversi overload di <xref:System.Windows.MessageBox.Show%2A> consentono di configurare la modalità di visualizzazione di una finestra di messaggio (vedere <xref:System.Windows.MessageBox>).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>Vedere anche

- [Esempio di MessageBox](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)

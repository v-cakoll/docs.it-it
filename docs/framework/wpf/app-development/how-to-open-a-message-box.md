---
title: 'Procedura: Aprire una finestra di messaggio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: cf7534cdee5e17d53e95294573023d660135e395
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947693"
---
# <a name="how-to-open-a-message-box"></a>Procedura: Aprire una finestra di messaggio
In questo esempio viene illustrato come aprire una finestra di messaggio.  
  
## <a name="example"></a>Esempio  
 Una finestra di messaggio è una finestra di dialogo modale predefiniti per la visualizzazione di informazioni agli utenti. Viene aperta una finestra di messaggio chiamando il metodo statico <xref:System.Windows.MessageBox.Show%2A> metodo di <xref:System.Windows.MessageBox> classe. Quando si <xref:System.Windows.MessageBox.Show%2A> viene chiamato, il messaggio viene passato usando un parametro di stringa. Diversi overload del <xref:System.Windows.MessageBox.Show%2A> consentono di configurare la modalità in cui verrà visualizzata una finestra di messaggio (vedere <xref:System.Windows.MessageBox>).  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a>Vedere anche

- [Esempio di MessageBox](https://go.microsoft.com/fwlink/?LinkID=160023)

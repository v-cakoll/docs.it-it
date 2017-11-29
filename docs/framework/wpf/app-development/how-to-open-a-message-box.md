---
title: 'Procedura: aprire una finestra di messaggio'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 302a3cd34d90d47e38af1bbeaadca7e777a26395
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-message-box"></a><span data-ttu-id="0e921-102">Procedura: aprire una finestra di messaggio</span><span class="sxs-lookup"><span data-stu-id="0e921-102">How to: Open a Message Box</span></span>
<span data-ttu-id="0e921-103">In questo esempio viene illustrato come aprire una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="0e921-103">This example shows how to open a message box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e921-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e921-104">Example</span></span>  
 <span data-ttu-id="0e921-105">Una finestra di messaggio è una finestra modale preimpostata per la visualizzazione di informazioni per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0e921-105">A message box is a prefabricated modal dialog box for displaying information to users.</span></span> <span data-ttu-id="0e921-106">Viene aperta una finestra di messaggio chiamando il metodo statico <xref:System.Windows.MessageBox.Show%2A> metodo la <xref:System.Windows.MessageBox> classe.</span><span class="sxs-lookup"><span data-stu-id="0e921-106">A message box is opened by calling the static <xref:System.Windows.MessageBox.Show%2A> method of the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="0e921-107">Quando <xref:System.Windows.MessageBox.Show%2A> viene chiamato, il messaggio viene passato tramite un parametro di stringa.</span><span class="sxs-lookup"><span data-stu-id="0e921-107">When <xref:System.Windows.MessageBox.Show%2A> is called, the message is passed using a string parameter.</span></span> <span data-ttu-id="0e921-108">Diversi overload di <xref:System.Windows.MessageBox.Show%2A> consentono di configurare la modalità in cui verrà visualizzata una finestra di messaggio (vedere <xref:System.Windows.MessageBox>).</span><span class="sxs-lookup"><span data-stu-id="0e921-108">Several overloads of <xref:System.Windows.MessageBox.Show%2A> allow you to configure how a message box will appear (see <xref:System.Windows.MessageBox>).</span></span>  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a><span data-ttu-id="0e921-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e921-109">See Also</span></span>  
 [<span data-ttu-id="0e921-110">Esempio di MessageBox</span><span class="sxs-lookup"><span data-stu-id="0e921-110">MessageBox Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160023)

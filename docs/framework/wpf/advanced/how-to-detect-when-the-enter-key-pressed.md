---
title: "Procedura: rilevare il momento in cui è stato premuto il tasto INVIO"
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
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 21bb0dc8a38f8b49a4f5372c9dfc1e17e5114d6a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="c7a7e-102">Procedura: rilevare il momento in cui è stato premuto il tasto INVIO</span><span class="sxs-lookup"><span data-stu-id="c7a7e-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="c7a7e-103">In questo esempio viene illustrato come rilevare quando il <xref:System.Windows.Input.Key.Enter> tasto della tastiera.</span><span class="sxs-lookup"><span data-stu-id="c7a7e-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="c7a7e-104">In questo esempio è costituito un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file e un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="c7a7e-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7a7e-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="c7a7e-105">Example</span></span>  
 <span data-ttu-id="c7a7e-106">Quando l'utente preme il <xref:System.Windows.Input.Key.Enter> chiave nel <xref:System.Windows.Controls.TextBox>, l'input nella casella di testo viene visualizzato in un'altra area della [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7a7e-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="c7a7e-107">Le operazioni seguenti [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea l'interfaccia utente, che è costituito da un <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock>e un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="c7a7e-107">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="c7a7e-108">Il codice seguente crea il <xref:System.Windows.UIElement.KeyDown> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c7a7e-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="c7a7e-109">Se la chiave che viene premuta il <xref:System.Windows.Input.Key.Enter> chiave, viene visualizzato un messaggio nel <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="c7a7e-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="c7a7e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7a7e-110">See Also</span></span>  
 [<span data-ttu-id="c7a7e-111">Cenni preliminari sull'input</span><span class="sxs-lookup"><span data-stu-id="c7a7e-111">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [<span data-ttu-id="c7a7e-112">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="c7a7e-112">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)

---
title: 'Procedura: Rilevare quando il tasto premuto immettere'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: 1796127d33087a3fd4504d03f175f8afe5323630
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351862"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="ad299-102">Procedura: Rilevare quando il tasto premuto immettere</span><span class="sxs-lookup"><span data-stu-id="ad299-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="ad299-103">Questo esempio viene illustrato come rilevare il momento di <xref:System.Windows.Input.Key.Enter> tasto sulla tastiera.</span><span class="sxs-lookup"><span data-stu-id="ad299-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="ad299-104">In questo esempio è costituito un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file e un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="ad299-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad299-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad299-105">Example</span></span>  
 <span data-ttu-id="ad299-106">Quando l'utente preme il <xref:System.Windows.Input.Key.Enter> chiavi nel <xref:System.Windows.Controls.TextBox>, l'input nella casella di testo viene visualizzato in un'altra area della [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad299-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="ad299-107">Quanto segue [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea l'interfaccia utente, che è costituito da un <xref:System.Windows.Controls.StackPanel>, un <xref:System.Windows.Controls.TextBlock>e un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="ad299-107">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="ad299-108">Crea il codice seguente sotto il <xref:System.Windows.UIElement.KeyDown> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="ad299-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="ad299-109">Se la chiave che viene premuta il <xref:System.Windows.Input.Key.Enter> key, viene visualizzato un messaggio nel <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="ad299-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="ad299-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad299-110">See also</span></span>
- [<span data-ttu-id="ad299-111">Cenni preliminari sull'input</span><span class="sxs-lookup"><span data-stu-id="ad299-111">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="ad299-112">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="ad299-112">Routed Events Overview</span></span>](routed-events-overview.md)

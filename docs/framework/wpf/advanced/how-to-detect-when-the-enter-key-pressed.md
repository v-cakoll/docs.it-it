---
title: 'Procedura: rilevare il momento in cui è stato premuto il tasto INVIO'
description: Rilevare quando il tasto invio è selezionato sulla tastiera in Windows Presentation Foundation. Questo esempio è costituito da XAML e da un file code-behind.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a955f52ec7bf93b32c70259b27fb51747664ac2e
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163181"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="a6ab1-104">Procedura: rilevare il momento in cui è stato premuto il tasto INVIO</span><span class="sxs-lookup"><span data-stu-id="a6ab1-104">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="a6ab1-105">Questo esempio Mostra come rilevare quando il <xref:System.Windows.Input.Key.Enter> tasto è premuto sulla tastiera.</span><span class="sxs-lookup"><span data-stu-id="a6ab1-105">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="a6ab1-106">Questo esempio è costituito da un file [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e da un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="a6ab1-106">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6ab1-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6ab1-107">Example</span></span>  
 <span data-ttu-id="a6ab1-108">Quando l'utente preme il <xref:System.Windows.Input.Key.Enter> tasto in <xref:System.Windows.Controls.TextBox> , l'input nella casella di testo viene visualizzato in un'altra area del [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6ab1-108">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="a6ab1-109">Il codice XAML seguente crea l'interfaccia utente, che è costituita da un oggetto, da un oggetto <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.TextBlock> e da un oggetto <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a6ab1-109">The following XAML creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="a6ab1-110">Il codice sottostante seguente crea il <xref:System.Windows.UIElement.KeyDown> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="a6ab1-110">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="a6ab1-111">Se il tasto premuto è la <xref:System.Windows.Input.Key.Enter> chiave, viene visualizzato un messaggio in <xref:System.Windows.Controls.TextBlock> .</span><span class="sxs-lookup"><span data-stu-id="a6ab1-111">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="a6ab1-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6ab1-112">See also</span></span>

- [<span data-ttu-id="a6ab1-113">Cenni preliminari sull'input</span><span class="sxs-lookup"><span data-stu-id="a6ab1-113">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="a6ab1-114">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="a6ab1-114">Routed Events Overview</span></span>](routed-events-overview.md)

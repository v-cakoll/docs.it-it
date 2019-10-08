---
title: 'Procedura: Rileva quando viene premuto il tasto invio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: e2337826077c836696937f91541d6d261f1270aa
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004815"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="b3eb7-102">Procedura: Rileva quando viene premuto il tasto invio</span><span class="sxs-lookup"><span data-stu-id="b3eb7-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="b3eb7-103">Questo esempio Mostra come rilevare quando il tasto <xref:System.Windows.Input.Key.Enter> è premuto sulla tastiera.</span><span class="sxs-lookup"><span data-stu-id="b3eb7-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="b3eb7-104">Questo esempio è costituito da un file [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e da un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="b3eb7-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3eb7-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b3eb7-105">Example</span></span>  
 <span data-ttu-id="b3eb7-106">Quando l'utente preme il tasto <xref:System.Windows.Input.Key.Enter> nella <xref:System.Windows.Controls.TextBox>, l'input nella casella di testo viene visualizzato in un'altra area del [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3eb7-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="b3eb7-107">Il codice XAML seguente crea l'interfaccia utente, che è costituita da un <xref:System.Windows.Controls.StackPanel>, da un <xref:System.Windows.Controls.TextBlock> e da un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="b3eb7-107">The following XAML creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="b3eb7-108">Il codice sottostante seguente crea il gestore dell'evento <xref:System.Windows.UIElement.KeyDown>.</span><span class="sxs-lookup"><span data-stu-id="b3eb7-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="b3eb7-109">Se il tasto premuto è il tasto <xref:System.Windows.Input.Key.Enter>, viene visualizzato un messaggio nel <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="b3eb7-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="b3eb7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3eb7-110">See also</span></span>

- [<span data-ttu-id="b3eb7-111">Cenni preliminari sull'input</span><span class="sxs-lookup"><span data-stu-id="b3eb7-111">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="b3eb7-112">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="b3eb7-112">Routed Events Overview</span></span>](routed-events-overview.md)

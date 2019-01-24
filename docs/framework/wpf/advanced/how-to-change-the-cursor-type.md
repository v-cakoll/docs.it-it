---
title: 'Procedura: Modificare il tipo di cursore'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: 2330cdd3be35dc4e4b555db6401dd55d9946ed1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745051"
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="42312-102">Procedura: Modificare il tipo di cursore</span><span class="sxs-lookup"><span data-stu-id="42312-102">How to: Change the Cursor Type</span></span>
<span data-ttu-id="42312-103">In questo esempio viene illustrato come modificare il <xref:System.Windows.Input.Cursor> del puntatore del mouse per un elemento specifico e per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="42312-103">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="42312-104">In questo esempio è costituito un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file e un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="42312-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42312-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="42312-105">Example</span></span>  
 <span data-ttu-id="42312-106">Viene creato l'interfaccia utente, che è costituito un <xref:System.Windows.Controls.ComboBox> per selezionare il valore desiderato <xref:System.Windows.Input.Cursor>, una coppia di <xref:System.Windows.Controls.RadioButton> oggetti per determinare se la modifica del cursore si applica a un solo elemento o si applica all'intera applicazione e un <xref:System.Windows.Controls.Border> ovvero l'elemento che viene applicato il nuovo cursore.</span><span class="sxs-lookup"><span data-stu-id="42312-106">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="42312-107">Il codice sottostante crea un <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> gestore eventi chiamato quando il tipo di cursore è stato modificato nel <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="42312-107">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="42312-108">Un'istruzione switch vengono applicati filtri al nome del cursore e imposta il <xref:System.Windows.FrameworkElement.Cursor%2A> proprietà di <xref:System.Windows.Controls.Border> denominato *DisplayArea*.</span><span class="sxs-lookup"><span data-stu-id="42312-108">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="42312-109">Se la modifica del cursore è impostata su "Intera applicazione", il <xref:System.Windows.Input.Mouse.OverrideCursor%2A> è impostata sul <xref:System.Windows.FrameworkElement.Cursor%2A> proprietà del <xref:System.Windows.Controls.Border> controllo.</span><span class="sxs-lookup"><span data-stu-id="42312-109">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="42312-110">In tal modo il cursore da modificare per l'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="42312-110">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="42312-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42312-111">See also</span></span>
- [<span data-ttu-id="42312-112">Cenni preliminari sull'input</span><span class="sxs-lookup"><span data-stu-id="42312-112">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)

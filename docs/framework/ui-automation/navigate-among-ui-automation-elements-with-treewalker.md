---
title: Navigare tra gli elementi di automazione interfaccia utente utilizzando TreeWalker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, TreeWalker
- TreeWalker class
- elements, navigating among
- UI Automation, navigating among elements
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
ms.openlocfilehash: 506cc4db3fcf255d270f72470a1f0d68e9cca7ce
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966427"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a><span data-ttu-id="c8db0-102">Navigare tra gli elementi di automazione interfaccia utente utilizzando TreeWalker</span><span class="sxs-lookup"><span data-stu-id="c8db0-102">Navigate Among UI Automation Elements with TreeWalker</span></span>
> [!NOTE]
> <span data-ttu-id="c8db0-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="c8db0-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c8db0-104">Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="c8db0-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="c8db0-105">Questo argomento contiene codice di esempio che illustra come spostarsi tra [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] gli elementi usando la <xref:System.Windows.Automation.TreeWalker> classe.</span><span class="sxs-lookup"><span data-stu-id="c8db0-105">This topic contains example code that shows how to navigate among [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements by using the <xref:System.Windows.Automation.TreeWalker> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8db0-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8db0-106">Example</span></span>  
 <span data-ttu-id="c8db0-107">Nell'esempio seguente viene <xref:System.Windows.Automation.TreeWalker.GetParent%2A> usato per scorrere l' [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] albero fino a trovare l'elemento radice o il desktop.</span><span class="sxs-lookup"><span data-stu-id="c8db0-107">The following example uses <xref:System.Windows.Automation.TreeWalker.GetParent%2A> to walk up the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tree until it finds the root element, or desktop.</span></span> <span data-ttu-id="c8db0-108">Elemento appena sotto, ovvero la finestra padre dell'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="c8db0-108">The element just below that is the parent window of the specified element.</span></span>  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a><span data-ttu-id="c8db0-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8db0-109">Example</span></span>  
 <span data-ttu-id="c8db0-110">Nell'esempio seguente vengono <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> usati <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> e per creare <xref:System.Windows.Forms.TreeView> un oggetto che mostra un intero [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] sottoalbero di elementi presenti nella visualizzazione controlli e abilitati.</span><span class="sxs-lookup"><span data-stu-id="c8db0-110">The following example uses <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> and <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> to create a <xref:System.Windows.Forms.TreeView> that shows an entire subtree of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements that are in the control view and that are enabled.</span></span>  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a><span data-ttu-id="c8db0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8db0-111">See also</span></span>

- [<span data-ttu-id="c8db0-112">Ottenere elementi di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="c8db0-112">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)

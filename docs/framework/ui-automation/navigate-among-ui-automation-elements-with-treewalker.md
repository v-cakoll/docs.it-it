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
ms.openlocfilehash: 5c14a660481ed14c0d9f379c80f2d6934a3b6dcb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443165"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a><span data-ttu-id="356ed-102">Navigare tra gli elementi di automazione interfaccia utente utilizzando TreeWalker</span><span class="sxs-lookup"><span data-stu-id="356ed-102">Navigate Among UI Automation Elements with TreeWalker</span></span>
> [!NOTE]
> <span data-ttu-id="356ed-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="356ed-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="356ed-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="356ed-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="356ed-105">Questo argomento contiene codice di esempio che illustra come spostarsi tra [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elementi usando la classe <xref:System.Windows.Automation.TreeWalker>.</span><span class="sxs-lookup"><span data-stu-id="356ed-105">This topic contains example code that shows how to navigate among [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements by using the <xref:System.Windows.Automation.TreeWalker> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="356ed-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="356ed-106">Example</span></span>  
 <span data-ttu-id="356ed-107">Nell'esempio seguente viene usato <xref:System.Windows.Automation.TreeWalker.GetParent%2A> per scorrere l'albero [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] fino a trovare l'elemento radice o desktop.</span><span class="sxs-lookup"><span data-stu-id="356ed-107">The following example uses <xref:System.Windows.Automation.TreeWalker.GetParent%2A> to walk up the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tree until it finds the root element, or desktop.</span></span> <span data-ttu-id="356ed-108">Elemento appena sotto, ovvero la finestra padre dell'elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="356ed-108">The element just below that is the parent window of the specified element.</span></span>  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a><span data-ttu-id="356ed-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="356ed-109">Example</span></span>  
 <span data-ttu-id="356ed-110">Nell'esempio seguente vengono utilizzati <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> e <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> per creare una <xref:System.Windows.Forms.TreeView> che mostra un intero sottoalbero di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elementi presenti nella visualizzazione controlli e abilitati.</span><span class="sxs-lookup"><span data-stu-id="356ed-110">The following example uses <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> and <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> to create a <xref:System.Windows.Forms.TreeView> that shows an entire subtree of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements that are in the control view and that are enabled.</span></span>  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a><span data-ttu-id="356ed-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="356ed-111">See also</span></span>

- [<span data-ttu-id="356ed-112">Obtaining UI Automation Elements</span><span class="sxs-lookup"><span data-stu-id="356ed-112">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)

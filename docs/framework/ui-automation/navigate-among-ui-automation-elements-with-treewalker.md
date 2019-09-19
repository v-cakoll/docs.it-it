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
ms.openlocfilehash: 7ecf6edd37b656f7dd1d7e31506d0dd455592d9b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71042973"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a>Navigare tra gli elementi di automazione interfaccia utente utilizzando TreeWalker
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.  
  
 Questo argomento contiene codice di esempio che illustra come spostarsi tra [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] gli elementi usando la <xref:System.Windows.Automation.TreeWalker> classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene <xref:System.Windows.Automation.TreeWalker.GetParent%2A> usato per scorrere l' [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] albero fino a trovare l'elemento radice o il desktop. Elemento appena sotto, ovvero la finestra padre dell'elemento specificato.  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> usati <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> e per creare <xref:System.Windows.Forms.TreeView> un oggetto che mostra un intero [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] sottoalbero di elementi presenti nella visualizzazione controlli e abilitati.  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a>Vedere anche

- [Ottenere elementi di automazione interfaccia utente](obtaining-ui-automation-elements.md)

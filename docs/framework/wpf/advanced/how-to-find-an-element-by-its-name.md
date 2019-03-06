---
title: 'Procedura: Individuare un elemento in base al nome'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
ms.openlocfilehash: 7405f9ba8db5d4db0ce35ca250f13e456685f39b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351047"
---
# <a name="how-to-find-an-element-by-its-name"></a><span data-ttu-id="53961-102">Procedura: Individuare un elemento in base al nome</span><span class="sxs-lookup"><span data-stu-id="53961-102">How to: Find an Element by Its Name</span></span>
<span data-ttu-id="53961-103">In questo esempio viene descritto come utilizzare il <xref:System.Windows.FrameworkElement.FindName%2A> metodo per trovare un elemento dal relativo <xref:System.Windows.FrameworkElement.Name%2A> valore.</span><span class="sxs-lookup"><span data-stu-id="53961-103">This example describes how to use the <xref:System.Windows.FrameworkElement.FindName%2A> method to find an element by its <xref:System.Windows.FrameworkElement.Name%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53961-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="53961-104">Example</span></span>  
 <span data-ttu-id="53961-105">In questo esempio, il metodo per trovare un particolare elemento in base al relativo nome viene scritto come il gestore di eventi di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="53961-105">In this example, the method to find a particular element by its name is written as the event handler of a button.</span></span> <span data-ttu-id="53961-106">`stackPanel` è il <xref:System.Windows.FrameworkElement.Name%2A> della radice <xref:System.Windows.FrameworkElement> cercato, e il metodo di esempio visivamente indica quindi l'elemento trovato eseguendo il cast come <xref:System.Windows.Controls.TextBlock> e modificare uno del <xref:System.Windows.Controls.TextBlock> visibile [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] proprietà.</span><span class="sxs-lookup"><span data-stu-id="53961-106">`stackPanel` is the <xref:System.Windows.FrameworkElement.Name%2A> of the root <xref:System.Windows.FrameworkElement> being searched, and the example method then visually indicates the found element by casting it as <xref:System.Windows.Controls.TextBlock> and changing one of the <xref:System.Windows.Controls.TextBlock> visible [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] properties.</span></span>  
  
 [!code-csharp[FEFindName#Find](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]

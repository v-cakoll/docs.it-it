---
title: 'Procedura: individuare un elemento in base al nome'
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
helpviewer_keywords: elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 62e5cc9c65afe9da9c77d06c103e99d3ff8d995a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-find-an-element-by-its-name"></a><span data-ttu-id="0b408-102">Procedura: individuare un elemento in base al nome</span><span class="sxs-lookup"><span data-stu-id="0b408-102">How to: Find an Element by Its Name</span></span>
<span data-ttu-id="0b408-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.FrameworkElement.FindName%2A> metodo per trovare un elemento dal relativo <xref:System.Windows.FrameworkElement.Name%2A> valore.</span><span class="sxs-lookup"><span data-stu-id="0b408-103">This example describes how to use the <xref:System.Windows.FrameworkElement.FindName%2A> method to find an element by its <xref:System.Windows.FrameworkElement.Name%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b408-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b408-104">Example</span></span>  
 <span data-ttu-id="0b408-105">In questo esempio, il metodo per trovare un particolare elemento in base al nome è scritto come il gestore dell'evento di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="0b408-105">In this example, the method to find a particular element by its name is written as the event handler of a button.</span></span> <span data-ttu-id="0b408-106">`stackPanel`è il <xref:System.Windows.FrameworkElement.Name%2A> della radice <xref:System.Windows.FrameworkElement> cercato, e il metodo di esempio indica quindi visivamente l'elemento trovato eseguendo il cast come <xref:System.Windows.Controls.TextBlock> e modifica di uno del <xref:System.Windows.Controls.TextBlock> visibile [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] proprietà.</span><span class="sxs-lookup"><span data-stu-id="0b408-106">`stackPanel` is the <xref:System.Windows.FrameworkElement.Name%2A> of the root <xref:System.Windows.FrameworkElement> being searched, and the example method then visually indicates the found element by casting it as <xref:System.Windows.Controls.TextBlock> and changing one of the <xref:System.Windows.Controls.TextBlock> visible [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] properties.</span></span>  
  
 [!code-csharp[FEFindName#Find](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]

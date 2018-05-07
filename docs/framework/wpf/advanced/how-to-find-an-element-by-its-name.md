---
title: 'Procedura: individuare un elemento in base al nome'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
ms.openlocfilehash: e2d176c9334c0a1d4c10819e0dc9f2c408e41d5d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-find-an-element-by-its-name"></a>Procedura: individuare un elemento in base al nome
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.FrameworkElement.FindName%2A> metodo per trovare un elemento dal relativo <xref:System.Windows.FrameworkElement.Name%2A> valore.  
  
## <a name="example"></a>Esempio  
 In questo esempio, il metodo per trovare un particolare elemento in base al nome è scritto come il gestore dell'evento di un pulsante. `stackPanel` è il <xref:System.Windows.FrameworkElement.Name%2A> della radice <xref:System.Windows.FrameworkElement> cercato, e il metodo di esempio indica quindi visivamente l'elemento trovato eseguendo il cast come <xref:System.Windows.Controls.TextBlock> e modifica di uno del <xref:System.Windows.Controls.TextBlock> visibile [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] proprietà.  
  
 [!code-csharp[FEFindName#Find](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]

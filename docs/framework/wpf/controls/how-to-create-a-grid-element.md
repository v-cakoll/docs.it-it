---
title: 'Procedura: creare un elemento Grid'
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
helpviewer_keywords: Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bd9614aee6e2bf7085b2fbee77993217439320a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-grid-element"></a>Procedura: creare un elemento Grid
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare e utilizzare un'istanza di <xref:System.Windows.Controls.Grid> utilizzando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o codice. In questo esempio vengono utilizzati tre <xref:System.Windows.Controls.ColumnDefinition> oggetti e tre <xref:System.Windows.Controls.RowDefinition> oggetti per creare una griglia che ha nove celle, ad esempio in un foglio di lavoro. Ogni cella contiene un <xref:System.Windows.Controls.TextBlock> elemento che rappresenta i dati e la riga superiore contiene una <xref:System.Windows.Controls.TextBlock> con il <xref:System.Windows.Controls.Grid.ColumnSpan%2A> proprietà applicato. Per visualizzare i limiti di ogni cella, il <xref:System.Windows.Controls.Grid.ShowGridLines%2A> proprietà è abilitata.  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Grid>  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)

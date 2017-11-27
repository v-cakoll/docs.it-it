---
title: 'Procedura: specificare una posizione personalizzata per un controllo Popup'
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
helpviewer_keywords: Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ab9baca1103adf8de96204bdb1b3353a5456b94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-a-custom-popup-position"></a>Procedura: specificare una posizione personalizzata per un controllo Popup
In questo esempio viene illustrato come specificare una posizione personalizzata per un <xref:System.Windows.Controls.Primitives.Popup> controllare quando il <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è impostata su <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.  
  
## <a name="example"></a>Esempio  
 Quando il <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è impostata su <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, <xref:System.Windows.Controls.Primitives.Popup> chiama un'istanza definita del <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegato. Questo delegato restituisce un set di possibili punti relativi all'angolo superiore sinistro dell'area di destinazione e l'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>. Il <xref:System.Windows.Controls.Primitives.Popup> viene posizionato nel punto che offre la migliore visibilità.  
  
 Nell'esempio seguente viene illustrato come definire la posizione di un <xref:System.Windows.Controls.Primitives.Popup> impostando il <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Viene inoltre illustrato come creare e assegnare un <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegato per posizionare il <xref:System.Windows.Controls.Primitives.Popup>.  Il delegato di callback restituisce due <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> oggetti.  Se il <xref:System.Windows.Controls.Primitives.Popup> è nascosto da un bordo dello schermo in corrispondenza della posizione del primo, il <xref:System.Windows.Controls.Primitives.Popup> viene posizionato in corrispondenza della posizione di secondo.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Per l'esempio completo, vedere [Popup Placement Sample](http://go.microsoft.com/fwlink/?LinkID=160032).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [Panoramica sul controllo Popup](../../../../docs/framework/wpf/controls/popup-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)

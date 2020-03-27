---
title: 'Procedura: specificare una posizione personalizzata per un controllo Popup'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: ea8d73c51dd018608b95104f00bf341ff434225c
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344961"
---
# <a name="how-to-specify-a-custom-popup-position"></a>Procedura: specificare una posizione personalizzata per un controllo Popup
In questo esempio viene illustrato come <xref:System.Windows.Controls.Primitives.Popup> specificare <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> una posizione <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>personalizzata per un controllo quando la proprietà è impostata su .  
  
## <a name="example"></a>Esempio  
 Quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> la proprietà <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>è <xref:System.Windows.Controls.Primitives.Popup> impostata su , <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> chiama un'istanza definita del delegato. Questo delegato restituisce un set di possibili punti relativi all'angolo superiore sinistro <xref:System.Windows.Controls.Primitives.Popup>dell'area di destinazione e all'angolo superiore sinistro dell'oggetto . Il <xref:System.Windows.Controls.Primitives.Popup> posizionamento avviene nel punto che offre la migliore visibilità.  
  
 Nell'esempio riportato di seguito <xref:System.Windows.Controls.Primitives.Popup> viene illustrato <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> come <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>definire la posizione di un oggetto impostando la proprietà su . Viene inoltre illustrato come creare <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> e assegnare <xref:System.Windows.Controls.Primitives.Popup>un delegato per posizionare il file .  Il delegato di <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> callback restituisce due oggetti.  Se <xref:System.Windows.Controls.Primitives.Popup> l'oggetto è nascosto da un <xref:System.Windows.Controls.Primitives.Popup> bordo dello schermo nella prima posizione, l'oggetto viene posizionato in corrispondenza della seconda posizione.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Per l'esempio completo, vedere Esempio di [posizionamento popup](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Primitives.Popup>
- [Panoramica sul controllo Popup](popup-overview.md)
- [Procedure relative](popup-how-to-topics.md)

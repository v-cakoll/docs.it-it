---
title: 'Procedura: spostarsi indietro nella cronologia di navigazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 9acbc5d3388a8df0ec7d7b5326f449f092f0cb03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546672"
---
# <a name="how-to-navigate-back-through-navigation-history"></a>Procedura: spostarsi indietro nella cronologia di navigazione
In questo esempio viene illustrato come passare a voci presenti nella cronologia di navigazione.  
  
## <a name="example"></a>Esempio  
 Codice che è in esecuzione dal contenuto ospitato in un <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> utilizzare <xref:System.Windows.Navigation.NavigationService>, o [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] possibile spostarsi indietro nella cronologia di navigazione, una voce alla volta.  
  
 Spostamento all'indietro di una voce richiede il controllo per verificare che siano presenti voci nella cronologia di navigazione all'indietro, controllando il **CanGoBack** proprietà, prima dello spostamento all'indietro di una voce, chiamando la **GoBack** metodo. Questo comportamento è illustrato nell'esempio seguente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoBack** e **GoBack** implementate dal <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, e <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Se si chiama **GoBack**, e non sono presenti voci nella cronologia di navigazione all'indietro, un <xref:System.InvalidOperationException> viene generato.

---
title: 'Procedura: Spostarsi indietro nella cronologia di spostamento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 86590c2794339ac22cbc8ec5e11224736133e870
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817972"
---
# <a name="how-to-navigate-back-through-navigation-history"></a>Procedura: Spostarsi indietro nella cronologia di spostamento
Questo esempio illustra come passare alle voci nella cronologia di navigazione indietro.  
  
## <a name="example"></a>Esempio  
 Il codice eseguito dal contenuto ospitato in un oggetto <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> utilizzando <xref:System.Windows.Navigation.NavigationService>o Internet Explorer può tornare alla cronologia di navigazione, una voce alla volta.  
  
 Per spostarsi indietro di una voce è necessario prima verificare che siano presenti voci nella cronologia di navigazione indietro, controllando la proprietà **CanGoBack** , prima di tornare indietro di una voce, chiamando il metodo **GoBack** . Questo è illustrato nell'esempio seguente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoBack** e **GoBack** sono implementati <xref:System.Windows.Navigation.NavigationWindow>da <xref:System.Windows.Controls.Frame>, e <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Se si chiama **GoBack**e non sono presenti voci nella cronologia di navigazione indietro, viene <xref:System.InvalidOperationException> generato un oggetto.

---
title: 'Procedura: Spostarsi in avanti o indietro nella cronologia di spostamento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: 85d3562246170901d83d6314caec5747d52fb9a0
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817959"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>Procedura: Spostarsi in avanti o indietro nella cronologia di spostamento
Questo esempio illustra come spostarsi in secondo piano o tornare alle voci nella cronologia di navigazione.  
  
## <a name="example"></a>Esempio  
 Il codice che viene eseguito dal contenuto negli host seguenti può spostarsi in diretta o indietro nella cronologia di navigazione, una voce alla volta.  
  
- <xref:System.Windows.Navigation.NavigationWindow>usando<xref:System.Windows.Navigation.NavigationService>  
  
- <xref:System.Windows.Controls.Frame>usando<xref:System.Windows.Navigation.NavigationService>  
  
- Internet Explorer  
  
 Prima di poter spostarsi in un secondo momento, è necessario verificare che siano presenti voci nella cronologia di navigazione in diretta controllando la proprietà **CanGoForward** . Per spostarsi in una voce, chiamare il metodo **GoForward** . Questo è illustrato nell'esempio seguente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 Prima di poter spostarsi indietro di una voce, è necessario verificare che siano presenti voci nella cronologia di navigazione indietro controllando la proprietà **CanGoBack** . Per spostarsi indietro di una voce, viene chiamato il metodo **GoBack** . Questo è illustrato nell'esempio seguente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**, **GoForward**, **CanGoBack**e **GoBack** sono implementati da <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>e <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Se si chiama **GoForward**e non sono presenti voci nella cronologia di navigazione in diretta o se si chiama **GoBack**e non sono presenti voci nella cronologia di navigazione indietro, viene <xref:System.InvalidOperationException> generata un'eccezione.

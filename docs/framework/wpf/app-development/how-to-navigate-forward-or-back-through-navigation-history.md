---
title: 'Procedura: Navigare in avanti o indietro nella cronologia di navigazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: 4c20ebfab45a24cf34b1476fb94dae6913fb4d99
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366660"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>Procedura: Navigare in avanti o indietro nella cronologia di navigazione
In questo esempio viene illustrato come spostarsi in avanti o indietro per le voci nella cronologia di navigazione.  
  
## <a name="example"></a>Esempio  
 Codice eseguito dai contenuti i seguenti host possibile spostarsi in avanti o indietro nella cronologia di navigazione, una voce alla volta.  
  
-   <xref:System.Windows.Navigation.NavigationWindow> Utilizzo <xref:System.Windows.Navigation.NavigationService>  
  
-   <xref:System.Windows.Controls.Frame> Utilizzo <xref:System.Windows.Navigation.NavigationService>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 Prima è possibile spostarsi in avanti di una voce, è necessario verificare che siano presenti voci nella cronologia di navigazione avanti controllando il **CanGoForward** proprietà. Per spostarsi avanti di una voce, si chiama il **GoForward** (metodo). Come illustrato nell'esempio seguente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 Prima è possibile spostarsi indietro di una voce, è prima di tutto necessario verificare che siano presenti voci nella cronologia di navigazione indietro controllando il **CanGoBack** proprietà. Per spostarsi indietro di una voce, si chiama il **GoBack** (metodo). Come illustrato nell'esempio seguente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**, **GoForward**, **CanGoBack**, e **GoBack** implementate da <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, e <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Se si chiama **GoForward**, e non sono presenti voci nella cronologia di navigazione avanti oppure se si chiama **GoBack**, e non sono presenti voci nella cronologia di navigazione indietro un <xref:System.InvalidOperationException> viene generata un'eccezione.

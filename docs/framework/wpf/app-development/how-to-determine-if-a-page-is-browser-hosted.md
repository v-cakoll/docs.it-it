---
title: 'Procedura: determinare se una pagina è ospitata in un browser'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: c4cb1065807d16c1d1f5a95c8ac9c9cbe5a0fdab
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424697"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a>Procedura: determinare se una pagina è ospitata in un browser
Questo esempio illustra come determinare se una <xref:System.Windows.Controls.Page> è ospitata in un browser.  
  
## <a name="example"></a>Esempio  
 Un <xref:System.Windows.Controls.Page> può essere indipendente dall'host e, di conseguenza, può essere caricato in diversi tipi di host, tra cui una <xref:System.Windows.Controls.Frame>, un <xref:System.Windows.Navigation.NavigationWindow>o un browser. Questo problema può verificarsi quando si dispone di un assembly di libreria che contiene una o più pagine e a cui fa riferimento più applicazioni host autonome e visualizzabili (XBAP).  
  
 Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> per determinare se una <xref:System.Windows.Controls.Page> è ospitata in un browser.  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>

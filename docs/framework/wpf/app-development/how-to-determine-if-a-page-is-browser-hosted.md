---
title: 'Procedura: Determinare se una pagina è ospitata su browser'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: d154de2f885101d1bd0c4613dfb1604be8acbe6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947810"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a>Procedura: Determinare se una pagina è ospitata su browser
In questo esempio viene illustrato come determinare se un <xref:System.Windows.Controls.Page> è ospitato in un browser.  
  
## <a name="example"></a>Esempio  
 Oggetto <xref:System.Windows.Controls.Page> può essere indipendente dall'host e, di conseguenza, può essere caricato in diversi tipi di host, inclusi una <xref:System.Windows.Controls.Frame>, un <xref:System.Windows.Navigation.NavigationWindow>, o un browser. Questa situazione può verificarsi quando si dispone di un assembly della libreria che contiene una o più pagine e che viene fatto riferimento da più autonomo esplorabile ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) ospitano le applicazioni.  
  
 Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> per determinare se un <xref:System.Windows.Controls.Page> è ospitato in un browser.  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>

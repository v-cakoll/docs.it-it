---
title: 'Procedura: determinare se una pagina è ospitata da Browser'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: 6eb83429cb4f9dac5f3561b41997d24bcaa2c62f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545897"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a>Procedura: determinare se una pagina è ospitata da Browser
In questo esempio viene illustrato come determinare se un <xref:System.Windows.Controls.Page> è ospitato in un browser.  
  
## <a name="example"></a>Esempio  
 Oggetto <xref:System.Windows.Controls.Page> può essere indipendente dall'host e, di conseguenza, può essere caricato in diversi tipi di host, inclusi un <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>, o un browser. Questa situazione può verificarsi quando si dispone di un assembly della libreria che contiene una o più pagine, e che è esplorabile e a cui fa riferimento più autonomo ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) ospitare applicazioni.  
  
 Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> per determinare se un <xref:System.Windows.Controls.Page> è ospitato in un browser.  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Frame>  
 <xref:System.Windows.Controls.Page>

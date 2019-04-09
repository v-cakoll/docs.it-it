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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107146"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a><span data-ttu-id="5dada-102">Procedura: Determinare se una pagina è ospitata su browser</span><span class="sxs-lookup"><span data-stu-id="5dada-102">How to: Determine If a Page is Browser Hosted</span></span>
<span data-ttu-id="5dada-103">In questo esempio viene illustrato come determinare se un <xref:System.Windows.Controls.Page> è ospitato in un browser.</span><span class="sxs-lookup"><span data-stu-id="5dada-103">This example demonstrates how to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dada-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="5dada-104">Example</span></span>  
 <span data-ttu-id="5dada-105">Oggetto <xref:System.Windows.Controls.Page> può essere indipendente dall'host e, di conseguenza, può essere caricato in diversi tipi di host, inclusi una <xref:System.Windows.Controls.Frame>, un <xref:System.Windows.Navigation.NavigationWindow>, o un browser.</span><span class="sxs-lookup"><span data-stu-id="5dada-105">A <xref:System.Windows.Controls.Page> can be host agnostic and, consequently, can be loaded into several different types of hosts, including a <xref:System.Windows.Controls.Frame>, a <xref:System.Windows.Navigation.NavigationWindow>, or a browser.</span></span> <span data-ttu-id="5dada-106">Questa situazione può verificarsi quando si dispone di un assembly della libreria che contiene una o più pagine e che viene fatto riferimento da più autonomo esplorabile ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) ospitano le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="5dada-106">This can happen when you have a library assembly that contains one or more pages, and which is referenced by multiple standalone and browsable ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) host applications.</span></span>  
  
 <span data-ttu-id="5dada-107">Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> per determinare se un <xref:System.Windows.Controls.Page> è ospitato in un browser.</span><span class="sxs-lookup"><span data-stu-id="5dada-107">The following example demonstrates how to use <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a><span data-ttu-id="5dada-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dada-108">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>

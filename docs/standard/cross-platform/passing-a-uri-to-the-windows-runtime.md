---
title: Passaggio di un URI a Windows Runtime
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7a31a1246fe311c36e7457327c79aeeef30e7813
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="passing-a-uri-to-the-windows-runtime"></a>Passaggio di un URI a Windows Runtime
I metodi di Windows Runtime accettano solo URI assoluti. Se si passa un URI relativo a un metodo [!INCLUDE[wrt](../../../includes/wrt-md.md)], viene generata un'eccezione <xref:System.ArgumentException>. Motivo: quando si usa il [!INCLUDE[wrt](../../../includes/wrt-md.md)] nel codice .NET Framework, il <xref:Windows.Foundation.Uri?displayProperty=nameWithType> classe viene visualizzata come <xref:System.Uri?displayProperty=nameWithType> in Intellisense. Il <xref:System.Uri?displayProperty=nameWithType> classe accetta URI relativi, ma la <xref:Windows.Foundation.Uri?displayProperty=nameWithType> non dalla classe. Questo accade anche per i metodi esposti nei componenti [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Se il componente espone un metodo che accetta un URI, la firma nel codice include <xref:System.Uri?displayProperty=nameWithType>. Agli utenti del componente, tuttavia, la firma include <xref:Windows.Foundation.Uri?displayProperty=nameWithType>. Un URI che viene passato al componente deve essere un URI assoluto.  
  
 In questo argomento viene illustrato come rilevare un URI assoluto e come crearne uno quando si fa riferimento a una risorsa nel pacchetto dell'app.  
  
## <a name="detecting-and-using-an-absolute-uri"></a>Rilevamento e utilizzo di un URI assoluto  
 Usare la proprietà <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> per verificare che un URI sia assoluto prima di passarlo a [!INCLUDE[wrt](../../../includes/wrt-md.md)]. È consigliabile usare questa proprietà anziché ricevere l'eccezione <xref:System.ArgumentException> e gestirla.  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>Uso di un URI assoluto per una risorsa nel pacchetto dell'app  
 Se si vuole specificare un URI per una risorsa contenuta nel pacchetto dell'app, è possibile usare lo schema `ms-appx` o `ms-appx-web` per creare un URI assoluto.  
  
 Nell'esempio seguente viene illustrato come impostare il [origine](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) proprietà per un [WebView](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) controllo e [origine](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) proprietà per un [immagine](http://msdn.microsoft.com/library/windows/apps/br242752.aspx) controllo per le risorse contenute in una cartella denominata pagine, con XAML e codice.  
  
 [!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
 Per ulteriori informazioni su questi schemi, vedere [schemi URI](http://msdn.microsoft.com/library/windows/apps/jj655406.aspx) in Windows Dev Center.  
  
## <a name="see-also"></a>Vedere anche  
 [.NET Framework Support for Windows Store Apps and Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (Supporto di .NET Framework per le app di Windows Store e Windows Runtime)

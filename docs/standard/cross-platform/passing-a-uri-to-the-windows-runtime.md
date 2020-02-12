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
ms.openlocfilehash: 71d427c2d602efbd92dc0128b1fada85a987904a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123623"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a>Passaggio di un URI a Windows Runtime
I metodi di Windows Runtime accettano solo URI assoluti. Se si passa un URI relativo a un metodo di Windows Runtime, viene generata un'eccezione <xref:System.ArgumentException>. Ecco perché: quando si usa il Windows Runtime nel codice .NET Framework, la classe <xref:Windows.Foundation.Uri?displayProperty=nameWithType> viene visualizzata come <xref:System.Uri?displayProperty=nameWithType> in IntelliSense. La classe <xref:System.Uri?displayProperty=nameWithType> supporta gli URI relativi, ma la classe <xref:Windows.Foundation.Uri?displayProperty=nameWithType> non lo è. Questo vale anche per i metodi esposti nei componenti Windows Runtime. Se il componente espone un metodo che accetta un URI, la firma nel codice include <xref:System.Uri?displayProperty=nameWithType>. Tuttavia, per gli utenti del componente, la firma include <xref:Windows.Foundation.Uri?displayProperty=nameWithType>. Un URI che viene passato al componente deve essere un URI assoluto.  
  
In questo argomento viene illustrato come rilevare un URI assoluto e come crearne uno quando si fa riferimento a una risorsa nel pacchetto dell'app.  
  
## <a name="detecting-and-using-an-absolute-uri"></a>Rilevamento e utilizzo di un URI assoluto  
Utilizzare la proprietà <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> per assicurarsi che un URI sia assoluto prima di passarlo al Windows Runtime. È consigliabile usare questa proprietà anziché ricevere l'eccezione <xref:System.ArgumentException> e gestirla.  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>Uso di un URI assoluto per una risorsa nel pacchetto dell'app  
Se si vuole specificare un URI per una risorsa contenuta nel pacchetto dell'app, è possibile usare lo schema `ms-appx` o `ms-appx-web` per creare un URI assoluto.  
  
Nell'esempio seguente viene illustrato come impostare la proprietà <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> per un controllo <xref:Windows.UI.Xaml.Controls.WebView> e la proprietà <xref:Windows.UI.Xaml.Controls.Image.Source%2A> per un controllo <xref:Windows.UI.Xaml.Controls.Image> per le risorse contenute in una cartella denominata Pages, utilizzando XAML e il codice.  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
Per ulteriori informazioni su questi schemi, vedere [schemi URI](/windows/uwp/app-resources/uri-schemes) nel centro per sviluppatori Windows.  
  
## <a name="see-also"></a>Vedere anche

- [.NET Framework Support for Windows Store Apps and Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (Supporto di .NET Framework per le app di Windows Store e Windows Runtime)

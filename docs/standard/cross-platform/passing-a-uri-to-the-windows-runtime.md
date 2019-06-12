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
ms.openlocfilehash: c489ec893ea335c8fafc904cf2a12162580ec266
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025432"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a>Passaggio di un URI a Windows Runtime
I metodi di Windows Runtime accettano solo URI assoluti. Se si passa un URI relativo a un metodo di Windows Runtime, un <xref:System.ArgumentException> viene generata un'eccezione. La ragione di questo comportamento è la seguente: Quando si usa il Runtime di Windows nel codice di .NET Framework, il <xref:Windows.Foundation.Uri?displayProperty=nameWithType> classe viene visualizzata come <xref:System.Uri?displayProperty=nameWithType> in Intellisense. Il <xref:System.Uri?displayProperty=nameWithType> classe accetta URI relativi, ma il <xref:Windows.Foundation.Uri?displayProperty=nameWithType> non dalla classe. Questo vale anche per i metodi che esposti nei componenti di Windows Runtime. Se il componente espone un metodo che accetta un URI, la firma nel codice include <xref:System.Uri?displayProperty=nameWithType>. Tuttavia, per gli utenti del componente, la firma include <xref:Windows.Foundation.Uri?displayProperty=nameWithType>. Un URI che viene passato al componente deve essere un URI assoluto.  
  
In questo argomento viene illustrato come rilevare un URI assoluto e come crearne uno quando si fa riferimento a una risorsa nel pacchetto dell'app.  
  
## <a name="detecting-and-using-an-absolute-uri"></a>Rilevamento e utilizzo di un URI assoluto  
Usare il <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> proprietà per assicurarsi che un URI sia assoluto prima di passarli al Runtime di Windows. È consigliabile usare questa proprietà anziché ricevere l'eccezione <xref:System.ArgumentException> e gestirla.  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>Uso di un URI assoluto per una risorsa nel pacchetto dell'app  
Se si vuole specificare un URI per una risorsa contenuta nel pacchetto dell'app, è possibile usare lo schema `ms-appx` o `ms-appx-web` per creare un URI assoluto.  
  
Nell'esempio seguente viene illustrato come impostare il <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> proprietà per un <xref:Windows.UI.Xaml.Controls.WebView> controllo e il <xref:Windows.UI.Xaml.Controls.Image.Source%2A> proprietà per un <xref:Windows.UI.Xaml.Controls.Image> controllo alle risorse contenute in una cartella denominata Pages usando sia XAML sia codice.  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
Per altre informazioni su questi schemi, vedere [schemi URI](/windows/uwp/app-resources/uri-schemes) in Windows Dev Center.  
  
## <a name="see-also"></a>Vedere anche

- [.NET Framework Support for Windows Store Apps and Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (Supporto di .NET Framework per le app di Windows Store e Windows Runtime)

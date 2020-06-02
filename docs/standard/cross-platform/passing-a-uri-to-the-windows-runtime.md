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
ms.openlocfilehash: 7152fb02abf430c0d0e27b82550e4006e3958e93
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288888"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a>Passaggio di un URI a Windows Runtime
I metodi di Windows Runtime accettano solo URI assoluti. Se si passa un URI relativo a un metodo di Windows Runtime, <xref:System.ArgumentException> viene generata un'eccezione. Ecco perché: quando si usa il Windows Runtime nel codice .NET Framework, la <xref:Windows.Foundation.Uri?displayProperty=nameWithType> classe viene visualizzata come <xref:System.Uri?displayProperty=nameWithType> in IntelliSense. La <xref:System.Uri?displayProperty=nameWithType> classe consente gli URI relativi, ma <xref:Windows.Foundation.Uri?displayProperty=nameWithType> non la classe. Questo vale anche per i metodi esposti nei componenti Windows Runtime. Se il componente espone un metodo che accetta un URI, la firma nel codice include <xref:System.Uri?displayProperty=nameWithType>. Tuttavia, per gli utenti del componente, la firma include <xref:Windows.Foundation.Uri?displayProperty=nameWithType> . Un URI che viene passato al componente deve essere un URI assoluto.  
  
In questo argomento viene illustrato come rilevare un URI assoluto e come crearne uno quando si fa riferimento a una risorsa nel pacchetto dell'app.  
  
## <a name="detecting-and-using-an-absolute-uri"></a>Rilevamento e utilizzo di un URI assoluto  
Utilizzare la <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> proprietà per verificare che un URI sia assoluto prima di passarlo al Windows Runtime. È consigliabile usare questa proprietà anziché ricevere l'eccezione <xref:System.ArgumentException> e gestirla.  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>Uso di un URI assoluto per una risorsa nel pacchetto dell'app  
Se si vuole specificare un URI per una risorsa contenuta nel pacchetto dell'app, è possibile usare lo schema `ms-appx` o `ms-appx-web` per creare un URI assoluto.  
  
Nell'esempio seguente viene illustrato come impostare la <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> proprietà di un <xref:Windows.UI.Xaml.Controls.WebView> controllo e la <xref:Windows.UI.Xaml.Controls.Image.Source%2A> proprietà di un <xref:Windows.UI.Xaml.Controls.Image> controllo su risorse contenute in una cartella denominata Pages, utilizzando XAML e il codice.  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
Per altre informazioni su questi schemi, vedere [Schemi URI](/windows/uwp/app-resources/uri-schemes) nel Centro sviluppatori Windows.  
  
## <a name="see-also"></a>Vedere anche

- [Supporto .NET Framework per applicazioni Windows Store e Windows Runtime](support-for-windows-store-apps-and-windows-runtime.md)

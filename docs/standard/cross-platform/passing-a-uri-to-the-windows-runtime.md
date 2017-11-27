---
title: Passaggio di un URI a Windows Runtime
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4ef77fb9e196abf046e0d4648a49b5d4d3fad47e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="338f3-102">Passaggio di un URI a Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="338f3-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="338f3-103">I metodi di Windows Runtime accettano solo URI assoluti.</span><span class="sxs-lookup"><span data-stu-id="338f3-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="338f3-104">Se si passa un URI relativo a un metodo [!INCLUDE[wrt](../../../includes/wrt-md.md)], viene generata un'eccezione <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="338f3-104">If you pass a relative URI to a [!INCLUDE[wrt](../../../includes/wrt-md.md)] method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="338f3-105">Motivo: quando si utilizza il [!INCLUDE[wrt](../../../includes/wrt-md.md)] nel codice .NET Framework, il [Windows](http://go.microsoft.com/fwlink/p/?LinkId=238376) classe viene visualizzata come <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span><span class="sxs-lookup"><span data-stu-id="338f3-105">Here's why: When you use the [!INCLUDE[wrt](../../../includes/wrt-md.md)] in .NET Framework code, the [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="338f3-106">Il <xref:System.Uri?displayProperty=nameWithType> classe accetta URI relativi, ma la [Windows](http://go.microsoft.com/fwlink/p/?LinkId=238376) non dalla classe.</span><span class="sxs-lookup"><span data-stu-id="338f3-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) class does not.</span></span> <span data-ttu-id="338f3-107">Questo accade anche per i metodi esposti nei componenti [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="338f3-107">This is also true for methods you expose in [!INCLUDE[wrt](../../../includes/wrt-md.md)] Components.</span></span> <span data-ttu-id="338f3-108">Se il componente espone un metodo che accetta un URI, la firma nel codice include <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="338f3-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="338f3-109">Agli utenti del componente, tuttavia, la firma include [Windows](http://go.microsoft.com/fwlink/p/?LinkId=238376).</span><span class="sxs-lookup"><span data-stu-id="338f3-109">However, to users of your component, the signature includes [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376).</span></span> <span data-ttu-id="338f3-110">Un URI che viene passato al componente deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="338f3-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
 <span data-ttu-id="338f3-111">In questo argomento viene illustrato come rilevare un URI assoluto e come crearne uno quando si fa riferimento a una risorsa nel pacchetto dell'app.</span><span class="sxs-lookup"><span data-stu-id="338f3-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="338f3-112">Rilevamento e utilizzo di un URI assoluto</span><span class="sxs-lookup"><span data-stu-id="338f3-112">Detecting and using an absolute URI</span></span>  
 <span data-ttu-id="338f3-113">Usare la proprietà <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> per verificare che un URI sia assoluto prima di passarlo a [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="338f3-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span></span> <span data-ttu-id="338f3-114">È consigliabile usare questa proprietà anziché ricevere l'eccezione <xref:System.ArgumentException> e gestirla.</span><span class="sxs-lookup"><span data-stu-id="338f3-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="338f3-115">Uso di un URI assoluto per una risorsa nel pacchetto dell'app</span><span class="sxs-lookup"><span data-stu-id="338f3-115">Using an absolute URI for a resource in the app package</span></span>  
 <span data-ttu-id="338f3-116">Se si vuole specificare un URI per una risorsa contenuta nel pacchetto dell'app, è possibile usare lo schema `ms-appx` o `ms-appx-web` per creare un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="338f3-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
 <span data-ttu-id="338f3-117">Nell'esempio seguente viene illustrato come impostare il [origine](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) proprietà per un [WebView](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) controllo e [origine](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) proprietà per un [immagine](http://msdn.microsoft.com/library/windows/apps/br242752.aspx) controllo per le risorse contenute in una cartella denominata pagine, con XAML e codice.</span><span class="sxs-lookup"><span data-stu-id="338f3-117">The following example shows how to set the [Source](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) property for a [WebView](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) control and the [Source](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) property for an [Image](http://msdn.microsoft.com/library/windows/apps/br242752.aspx) control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
 [!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
 <span data-ttu-id="338f3-118">Per ulteriori informazioni su questi schemi, vedere [schemi URI](http://msdn.microsoft.com/library/windows/apps/jj655406.aspx) in Windows Dev Center.</span><span class="sxs-lookup"><span data-stu-id="338f3-118">For more information about these schemes, see [URI schemes](http://msdn.microsoft.com/library/windows/apps/jj655406.aspx) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="338f3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="338f3-119">See Also</span></span>  
 <span data-ttu-id="338f3-120">[.NET Framework Support for Windows Store Apps and Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (Supporto di .NET Framework per le app di Windows Store e Windows Runtime)</span><span class="sxs-lookup"><span data-stu-id="338f3-120">[.NET Framework Support for Windows Store Apps and Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)</span></span>

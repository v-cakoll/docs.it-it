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
ms.openlocfilehash: c5ce0d4ac2b95dc4d51e785e3a00026f56c13d2c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2018
ms.locfileid: "50220707"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="bfb9b-102">Passaggio di un URI a Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="bfb9b-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="bfb9b-103">I metodi di Windows Runtime accettano solo URI assoluti.</span><span class="sxs-lookup"><span data-stu-id="bfb9b-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="bfb9b-104">Se si passa un URI relativo a un metodo [!INCLUDE[wrt](../../../includes/wrt-md.md)], viene generata un'eccezione <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="bfb9b-104">If you pass a relative URI to a [!INCLUDE[wrt](../../../includes/wrt-md.md)] method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="bfb9b-105">Motivo: quando si usa la [!INCLUDE[wrt](../../../includes/wrt-md.md)] nel codice di .NET Framework, il <xref:Windows.Foundation.Uri?displayProperty=nameWithType> classe viene visualizzata come <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span><span class="sxs-lookup"><span data-stu-id="bfb9b-105">Here's why: When you use the [!INCLUDE[wrt](../../../includes/wrt-md.md)] in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="bfb9b-106">Il <xref:System.Uri?displayProperty=nameWithType> classe accetta URI relativi, ma il <xref:Windows.Foundation.Uri?displayProperty=nameWithType> non dalla classe.</span><span class="sxs-lookup"><span data-stu-id="bfb9b-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="bfb9b-107">Questo accade anche per i metodi esposti nei componenti [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfb9b-107">This is also true for methods you expose in [!INCLUDE[wrt](../../../includes/wrt-md.md)] Components.</span></span> <span data-ttu-id="bfb9b-108">Se il componente espone un metodo che accetta un URI, la firma nel codice include <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bfb9b-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bfb9b-109">Tuttavia, per gli utenti del componente, la firma include <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bfb9b-109">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bfb9b-110">Un URI che viene passato al componente deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="bfb9b-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
<span data-ttu-id="bfb9b-111">In questo argomento viene illustrato come rilevare un URI assoluto e come crearne uno quando si fa riferimento a una risorsa nel pacchetto dell'app.</span><span class="sxs-lookup"><span data-stu-id="bfb9b-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="bfb9b-112">Rilevamento e utilizzo di un URI assoluto</span><span class="sxs-lookup"><span data-stu-id="bfb9b-112">Detecting and using an absolute URI</span></span>  
<span data-ttu-id="bfb9b-113">Usare la proprietà <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> per verificare che un URI sia assoluto prima di passarlo a [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfb9b-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span></span> <span data-ttu-id="bfb9b-114">È consigliabile usare questa proprietà anziché ricevere l'eccezione <xref:System.ArgumentException> e gestirla.</span><span class="sxs-lookup"><span data-stu-id="bfb9b-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="bfb9b-115">Uso di un URI assoluto per una risorsa nel pacchetto dell'app</span><span class="sxs-lookup"><span data-stu-id="bfb9b-115">Using an absolute URI for a resource in the app package</span></span>  
<span data-ttu-id="bfb9b-116">Se si vuole specificare un URI per una risorsa contenuta nel pacchetto dell'app, è possibile usare lo schema `ms-appx` o `ms-appx-web` per creare un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="bfb9b-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
<span data-ttu-id="bfb9b-117">Nell'esempio seguente viene illustrato come impostare il <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> proprietà per un <xref:Windows.UI.Xaml.Controls.WebView> controllo e il <xref:Windows.UI.Xaml.Controls.Image.Source%2A> proprietà per un <xref:Windows.UI.Xaml.Controls.Image> controllo alle risorse contenute in una cartella denominata Pages usando sia XAML sia codice.</span><span class="sxs-lookup"><span data-stu-id="bfb9b-117">The following example shows how to set the <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> property for a <xref:Windows.UI.Xaml.Controls.WebView> control and the <xref:Windows.UI.Xaml.Controls.Image.Source%2A> property for an <xref:Windows.UI.Xaml.Controls.Image> control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
<span data-ttu-id="bfb9b-118">Per altre informazioni su questi schemi, vedere [schemi URI](/windows/uwp/app-resources/uri-schemes) in Windows Dev Center.</span><span class="sxs-lookup"><span data-stu-id="bfb9b-118">For more information about these schemes, see [URI schemes](/windows/uwp/app-resources/uri-schemes) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfb9b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfb9b-119">See also</span></span>

- <span data-ttu-id="bfb9b-120">[.NET Framework Support for Windows Store Apps and Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (Supporto di .NET Framework per le app di Windows Store e Windows Runtime)</span><span class="sxs-lookup"><span data-stu-id="bfb9b-120">[.NET Framework Support for Windows Store Apps and Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)</span></span>

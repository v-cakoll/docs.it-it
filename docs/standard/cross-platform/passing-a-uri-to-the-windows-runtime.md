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
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="9268d-102">Passaggio di un URI a Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="9268d-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="9268d-103">I metodi di Windows Runtime accettano solo URI assoluti.</span><span class="sxs-lookup"><span data-stu-id="9268d-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="9268d-104">Se si passa un URI relativo a un metodo di Windows Runtime, <xref:System.ArgumentException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9268d-104">If you pass a relative URI to a Windows Runtime method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="9268d-105">Ecco perché: quando si usa il Windows Runtime nel codice .NET Framework, la <xref:Windows.Foundation.Uri?displayProperty=nameWithType> classe viene visualizzata come <xref:System.Uri?displayProperty=nameWithType> in IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="9268d-105">Here's why: When you use the Windows Runtime in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="9268d-106">La <xref:System.Uri?displayProperty=nameWithType> classe consente gli URI relativi, ma <xref:Windows.Foundation.Uri?displayProperty=nameWithType> non la classe.</span><span class="sxs-lookup"><span data-stu-id="9268d-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="9268d-107">Questo vale anche per i metodi esposti nei componenti Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="9268d-107">This is also true for methods you expose in Windows Runtime Components.</span></span> <span data-ttu-id="9268d-108">Se il componente espone un metodo che accetta un URI, la firma nel codice include <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9268d-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9268d-109">Tuttavia, per gli utenti del componente, la firma include <xref:Windows.Foundation.Uri?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9268d-109">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9268d-110">Un URI che viene passato al componente deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="9268d-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
<span data-ttu-id="9268d-111">In questo argomento viene illustrato come rilevare un URI assoluto e come crearne uno quando si fa riferimento a una risorsa nel pacchetto dell'app.</span><span class="sxs-lookup"><span data-stu-id="9268d-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="9268d-112">Rilevamento e utilizzo di un URI assoluto</span><span class="sxs-lookup"><span data-stu-id="9268d-112">Detecting and using an absolute URI</span></span>  
<span data-ttu-id="9268d-113">Utilizzare la <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> proprietà per verificare che un URI sia assoluto prima di passarlo al Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="9268d-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the Windows Runtime.</span></span> <span data-ttu-id="9268d-114">È consigliabile usare questa proprietà anziché ricevere l'eccezione <xref:System.ArgumentException> e gestirla.</span><span class="sxs-lookup"><span data-stu-id="9268d-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="9268d-115">Uso di un URI assoluto per una risorsa nel pacchetto dell'app</span><span class="sxs-lookup"><span data-stu-id="9268d-115">Using an absolute URI for a resource in the app package</span></span>  
<span data-ttu-id="9268d-116">Se si vuole specificare un URI per una risorsa contenuta nel pacchetto dell'app, è possibile usare lo schema `ms-appx` o `ms-appx-web` per creare un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="9268d-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
<span data-ttu-id="9268d-117">Nell'esempio seguente viene illustrato come impostare la <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> proprietà di un <xref:Windows.UI.Xaml.Controls.WebView> controllo e la <xref:Windows.UI.Xaml.Controls.Image.Source%2A> proprietà di un <xref:Windows.UI.Xaml.Controls.Image> controllo su risorse contenute in una cartella denominata Pages, utilizzando XAML e il codice.</span><span class="sxs-lookup"><span data-stu-id="9268d-117">The following example shows how to set the <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> property for a <xref:Windows.UI.Xaml.Controls.WebView> control and the <xref:Windows.UI.Xaml.Controls.Image.Source%2A> property for an <xref:Windows.UI.Xaml.Controls.Image> control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
<span data-ttu-id="9268d-118">Per altre informazioni su questi schemi, vedere [Schemi URI](/windows/uwp/app-resources/uri-schemes) nel Centro sviluppatori Windows.</span><span class="sxs-lookup"><span data-stu-id="9268d-118">For more information about these schemes, see [URI schemes](/windows/uwp/app-resources/uri-schemes) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9268d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9268d-119">See also</span></span>

- [<span data-ttu-id="9268d-120">Supporto .NET Framework per applicazioni Windows Store e Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="9268d-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](support-for-windows-store-apps-and-windows-runtime.md)

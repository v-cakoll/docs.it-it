---
title: MEF per .NET per app Windows Store
ms.date: 03/30/2017
ms.assetid: 7667770e-d163-4ad6-a303-085cf73db2f2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2c6f28a88c709c27df82250fcbdc22de210e93a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663297"
---
# <a name="mef-for-net-for-windows-store-apps"></a><span data-ttu-id="ccaa9-102">MEF per .NET per app Windows Store</span><span class="sxs-lookup"><span data-stu-id="ccaa9-102">MEF for .NET for Windows Store Apps</span></span>
<span data-ttu-id="ccaa9-103"><xref:System.Composition?displayProperty=nameWithType> e i relativi spazi dei nomi figlio contengono i tipi per sviluppare app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] estendibili mediante Managed Extensibility Framework (MEF).</span><span class="sxs-lookup"><span data-stu-id="ccaa9-103"><xref:System.Composition?displayProperty=nameWithType> and its child namespaces contain types for developing extensible [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps with Managed Extensibility Framework (MEF).</span></span> <span data-ttu-id="ccaa9-104">Questi spazi dei nomi fanno parte del subset [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] per il sistema operativo [!INCLUDE[win8](../../../includes/win8-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccaa9-104">These namespaces are part of the [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] subset for the [!INCLUDE[win8](../../../includes/win8-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="ccaa9-105">Questi spazi dei nomi non fanno parte della libreria di classi principale distribuita con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ccaa9-105">These namespaces are not part of the core class library distributed with the .NET Framework.</span></span> <span data-ttu-id="ccaa9-106">Per installare questi spazi dei nomi, aprire il progetto in Visual Studio, scegliere **Gestisci pacchetti NuGet** dal menu **Progetto** e cercare online il pacchetto Microsoft.Composition.</span><span class="sxs-lookup"><span data-stu-id="ccaa9-106">To install these namespaces, open your project in Visual Studio, choose **Manage NuGet Packages** from the **Project** menu, and search online for the Microsoft.Composition package.</span></span>  
  
-   <span data-ttu-id="ccaa9-107"><xref:System.Composition?displayProperty=nameWithType> fornisce classi che costituiscono il framework MEF di base per le app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccaa9-107"><xref:System.Composition?displayProperty=nameWithType> provides classes that constitute the core MEF for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
-   <span data-ttu-id="ccaa9-108"><xref:System.Composition.Convention?displayProperty=nameWithType> fornisce i tipi che supportano l'uso di MEF con un modello di configurazione basato sulle convenzioni.</span><span class="sxs-lookup"><span data-stu-id="ccaa9-108"><xref:System.Composition.Convention?displayProperty=nameWithType> provides types that support using MEF with a convention-based configuration model.</span></span>  
  
-   <span data-ttu-id="ccaa9-109"><xref:System.Composition.Hosting?displayProperty=nameWithType> fornisce tipi MEF utili agli sviluppatori di applicazioni host.</span><span class="sxs-lookup"><span data-stu-id="ccaa9-109"><xref:System.Composition.Hosting?displayProperty=nameWithType> provides MEF types that are useful to developers of host applications.</span></span>  
  
-   <span data-ttu-id="ccaa9-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType> fornire i tipi MEF usati internamente dal motore di composizione.</span><span class="sxs-lookup"><span data-stu-id="ccaa9-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType> provides MEF types used internally by the composition engine.</span></span>  
  
 <span data-ttu-id="ccaa9-111">Per altre informazioni su [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] e un elenco degli spazi dei nomi e dei tipi contenuti, vedere [Panoramica di .NET per le app di Windows Store](https://go.microsoft.com/fwlink/p/?LinkID=238312) nel Centro sviluppatori Windows.</span><span class="sxs-lookup"><span data-stu-id="ccaa9-111">For more information about [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] and a list of namespaces and types that it contains, see [.NET for Windows Store apps overview](https://go.microsoft.com/fwlink/p/?LinkID=238312) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccaa9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccaa9-112">See also</span></span>
- [<span data-ttu-id="ccaa9-113">Panoramica di .NET per le app di Windows Store</span><span class="sxs-lookup"><span data-stu-id="ccaa9-113">.NET for Windows Store apps overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=238312)
- [<span data-ttu-id="ccaa9-114">.NET per app di Windows Store – API supportate</span><span class="sxs-lookup"><span data-stu-id="ccaa9-114">.NET for Windows Store apps – supported APIs</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=247912)
- [<span data-ttu-id="ccaa9-115">Managed Extensibility Framework (MEF)</span><span class="sxs-lookup"><span data-stu-id="ccaa9-115">Managed Extensibility Framework (MEF)</span></span>](../../../docs/framework/mef/index.md)

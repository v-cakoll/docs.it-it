---
title: GetCustomUI
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 88c2873a5929e25335b0c6ef64f8121e31177ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getcustomui"></a><span data-ttu-id="b9c2a-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="b9c2a-102">GetCustomUI</span></span>
<span data-ttu-id="b9c2a-103">Chiamato da PresentationHost.exe per ottenere lo stato personalizzato e messaggi di errore dall'host, se implementata.</span><span class="sxs-lookup"><span data-stu-id="b9c2a-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9c2a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9c2a-104">Syntax</span></span>  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9c2a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b9c2a-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="b9c2a-106">[out] Un puntatore all'assembly che contiene l'interfaccia utente di stato fornita dall'host.</span><span class="sxs-lookup"><span data-stu-id="b9c2a-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="b9c2a-107">[out] Il nome della classe che è l'interfaccia utente di stato fornita dall'host, preferibilmente una [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file con <xref:System.Windows.Controls.Page> elemento di primo livello.</span><span class="sxs-lookup"><span data-stu-id="b9c2a-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="b9c2a-108">Questa classe si trova nell'assembly specificato da `pwzProgressAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="b9c2a-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="b9c2a-109">[out] Un puntatore all'assembly che contiene l'interfaccia utente di errore fornita dall'host.</span><span class="sxs-lookup"><span data-stu-id="b9c2a-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="b9c2a-110">[out] Il nome della classe che corrisponde all'utente di errore fornita dall'host dell'interfaccia, preferibilmente un file XAML con <xref:System.Windows.Controls.Page> elemento di primo livello.</span><span class="sxs-lookup"><span data-stu-id="b9c2a-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="b9c2a-111">Questa classe si trova nell'assembly specificato da `pwzErrorAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="b9c2a-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b9c2a-112">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b9c2a-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="b9c2a-113">HRESULT: ignorato.</span><span class="sxs-lookup"><span data-stu-id="b9c2a-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9c2a-114">Note</span><span class="sxs-lookup"><span data-stu-id="b9c2a-114">Remarks</span></span>  
 <span data-ttu-id="b9c2a-115">Un'applicazione host potrebbe essere un tema interfacce utente predefinite di PresentationHost.exe potrebbero non essere conforme alle specifico.</span><span class="sxs-lookup"><span data-stu-id="b9c2a-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="b9c2a-116">In questo caso, è possibile implementare l'applicazione host [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) per restituire lo stato di avanzamento e di errore interfacce utente per PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="b9c2a-116">If this is the case, the host application can implement [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="b9c2a-117">Chiama sempre PresentationHost.exe [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) prima di utilizzare le interfacce utente predefinite.</span><span class="sxs-lookup"><span data-stu-id="b9c2a-117">PresentationHost.exe will always call [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="b9c2a-118">Questa funzione viene chiamata una volta durante l'inizializzazione di PresentationHost.</span><span class="sxs-lookup"><span data-stu-id="b9c2a-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9c2a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9c2a-119">See Also</span></span>  
 [<span data-ttu-id="b9c2a-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="b9c2a-120">IWpfHostSupport</span></span>](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)

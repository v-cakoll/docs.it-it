---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: ff68c30c4e58cebb70c59352593d7b084413dce8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548646"
---
# <a name="getcustomui"></a><span data-ttu-id="63388-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="63388-102">GetCustomUI</span></span>
<span data-ttu-id="63388-103">Chiamato da PresentationHost.exe per ottenere lo stato personalizzato e messaggi di errore dall'host, se implementata.</span><span class="sxs-lookup"><span data-stu-id="63388-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63388-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63388-104">Syntax</span></span>  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63388-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="63388-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="63388-106">[out] Un puntatore all'assembly che contiene l'interfaccia utente di stato fornita dall'host.</span><span class="sxs-lookup"><span data-stu-id="63388-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="63388-107">[out] Il nome della classe che è l'interfaccia utente di stato fornita dall'host, preferibilmente una [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file con <xref:System.Windows.Controls.Page> elemento di primo livello.</span><span class="sxs-lookup"><span data-stu-id="63388-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="63388-108">Questa classe si trova nell'assembly specificato da `pwzProgressAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="63388-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="63388-109">[out] Un puntatore all'assembly che contiene l'interfaccia utente di errore fornita dall'host.</span><span class="sxs-lookup"><span data-stu-id="63388-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="63388-110">[out] Il nome della classe che corrisponde all'utente di errore fornita dall'host dell'interfaccia, preferibilmente un file XAML con <xref:System.Windows.Controls.Page> elemento di primo livello.</span><span class="sxs-lookup"><span data-stu-id="63388-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="63388-111">Questa classe si trova nell'assembly specificato da `pwzErrorAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="63388-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="63388-112">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="63388-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="63388-113">HRESULT: ignorato.</span><span class="sxs-lookup"><span data-stu-id="63388-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63388-114">Note</span><span class="sxs-lookup"><span data-stu-id="63388-114">Remarks</span></span>  
 <span data-ttu-id="63388-115">Un'applicazione host potrebbe essere un tema interfacce utente predefinite di PresentationHost.exe potrebbero non essere conforme alle specifico.</span><span class="sxs-lookup"><span data-stu-id="63388-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="63388-116">In questo caso, è possibile implementare l'applicazione host [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) per restituire lo stato di avanzamento e di errore interfacce utente per PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="63388-116">If this is the case, the host application can implement [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="63388-117">Chiama sempre PresentationHost.exe [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) prima di utilizzare le interfacce utente predefinite.</span><span class="sxs-lookup"><span data-stu-id="63388-117">PresentationHost.exe will always call [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="63388-118">Questa funzione viene chiamata una volta durante l'inizializzazione di PresentationHost.</span><span class="sxs-lookup"><span data-stu-id="63388-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63388-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63388-119">See Also</span></span>  
 [<span data-ttu-id="63388-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="63388-120">IWpfHostSupport</span></span>](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)

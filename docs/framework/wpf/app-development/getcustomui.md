---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: 623ff5d14db6ae9cc5999aa184b81d6b22f4b201
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365009"
---
# <a name="getcustomui"></a><span data-ttu-id="3c4f5-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="3c4f5-102">GetCustomUI</span></span>
<span data-ttu-id="3c4f5-103">Chiamato dal PresentationHost.exe per ottenere lo stato personalizzato e messaggi di errore dall'host, se è implementato.</span><span class="sxs-lookup"><span data-stu-id="3c4f5-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c4f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c4f5-104">Syntax</span></span>  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c4f5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3c4f5-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="3c4f5-106">[out] Un puntatore all'assembly che contiene l'interfaccia utente lo stato di avanzamento fornita dall'host.</span><span class="sxs-lookup"><span data-stu-id="3c4f5-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="3c4f5-107">[out] Il nome della classe che è l'interfaccia utente lo stato di avanzamento fornita dall'host, preferibilmente una [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file con <xref:System.Windows.Controls.Page> elemento di primo livello.</span><span class="sxs-lookup"><span data-stu-id="3c4f5-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="3c4f5-108">Questa classe si trova nell'assembly specificato da `pwzProgressAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="3c4f5-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="3c4f5-109">[out] Un puntatore all'assembly che contiene l'interfaccia utente di errore fornito dall'host.</span><span class="sxs-lookup"><span data-stu-id="3c4f5-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="3c4f5-110">[out] Il nome della classe che corrisponde all'utente di errore fornito dall'host di interfaccia, preferibilmente un file XAML con <xref:System.Windows.Controls.Page> elemento di primo livello.</span><span class="sxs-lookup"><span data-stu-id="3c4f5-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="3c4f5-111">Questa classe si trova nell'assembly specificato da `pwzErrorAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="3c4f5-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3c4f5-112">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3c4f5-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="3c4f5-113">HRESULT: Ignorato.</span><span class="sxs-lookup"><span data-stu-id="3c4f5-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c4f5-114">Note</span><span class="sxs-lookup"><span data-stu-id="3c4f5-114">Remarks</span></span>  
 <span data-ttu-id="3c4f5-115">Un'applicazione host può avere un tema specifico che interfacce utente predefinite del PresentationHost.exe potrebbero non essere conforme a.</span><span class="sxs-lookup"><span data-stu-id="3c4f5-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="3c4f5-116">In questo caso, l'applicazione host può implementare [GetCustomUI](getcustomui.md) per restituire lo stato di avanzamento ed errore interfacce utente a PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="3c4f5-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="3c4f5-117">Chiama sempre PresentationHost.exe [GetCustomUI](getcustomui.md) prima di usare le interfacce utente predefinite.</span><span class="sxs-lookup"><span data-stu-id="3c4f5-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="3c4f5-118">Questa funzione viene chiamata una volta durante l'inizializzazione di PresentationHost.</span><span class="sxs-lookup"><span data-stu-id="3c4f5-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c4f5-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c4f5-119">See also</span></span>
- [<span data-ttu-id="3c4f5-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="3c4f5-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)

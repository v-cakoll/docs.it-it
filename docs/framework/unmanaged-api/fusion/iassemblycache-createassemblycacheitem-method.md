---
title: Metodo IAssemblyCache::CreateAssemblyCacheItem
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 476f28b37efef483b31ad548d3db62c820d536c5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489059"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="0420f-102">Metodo IAssemblyCache::CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="0420f-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="0420f-103">Ottiene un riferimento a una nuova [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="0420f-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0420f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0420f-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0420f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0420f-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="0420f-106">[in] Flag definiti in Fusion.</span><span class="sxs-lookup"><span data-stu-id="0420f-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="0420f-107">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="0420f-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="0420f-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="0420f-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="0420f-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="0420f-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="0420f-110">[in] Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="0420f-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="0420f-111">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="0420f-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="0420f-112">[out] L'oggetto restituito `IAssemblyCacheItem` puntatore.</span><span class="sxs-lookup"><span data-stu-id="0420f-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="0420f-113">[in, optional] In formato non canonico, delimitati da virgole `name=value` coppie.</span><span class="sxs-lookup"><span data-stu-id="0420f-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0420f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0420f-114">Requirements</span></span>  
 <span data-ttu-id="0420f-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0420f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0420f-116">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="0420f-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0420f-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0420f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0420f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0420f-118">See also</span></span>
- [<span data-ttu-id="0420f-119">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="0420f-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="0420f-120">Interfaccia IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="0420f-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)

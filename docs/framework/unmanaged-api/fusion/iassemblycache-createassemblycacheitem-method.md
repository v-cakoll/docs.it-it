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
ms.openlocfilehash: a19ea52007edcc1930a2be46059a35b9cbebdc52
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650390"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="9e1f6-102">Metodo IAssemblyCache::CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="9e1f6-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="9e1f6-103">Ottiene un riferimento a una nuova [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="9e1f6-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e1f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e1f6-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e1f6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9e1f6-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="9e1f6-106">[in] Flag definiti in Fusion.</span><span class="sxs-lookup"><span data-stu-id="9e1f6-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="9e1f6-107">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="9e1f6-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="9e1f6-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="9e1f6-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="9e1f6-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="9e1f6-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="9e1f6-110">[in] Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="9e1f6-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="9e1f6-111">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="9e1f6-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="9e1f6-112">[out] L'oggetto restituito `IAssemblyCacheItem` puntatore.</span><span class="sxs-lookup"><span data-stu-id="9e1f6-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="9e1f6-113">[in, optional] In formato non canonico, delimitati da virgole `name=value` coppie.</span><span class="sxs-lookup"><span data-stu-id="9e1f6-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e1f6-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9e1f6-114">Requirements</span></span>  
 <span data-ttu-id="9e1f6-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e1f6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e1f6-116">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9e1f6-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9e1f6-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e1f6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e1f6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e1f6-118">See also</span></span>

- [<span data-ttu-id="9e1f6-119">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="9e1f6-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="9e1f6-120">Interfaccia IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="9e1f6-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)

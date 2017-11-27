---
title: Metodo IAssemblyCache::CreateAssemblyCacheItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCache.CreateAssemblyCacheItem
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 84291d3dea34aba43889baeb1f6e3d501f71b782
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="9c68f-102">Metodo IAssemblyCache::CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="9c68f-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="9c68f-103">Ottiene un riferimento a un nuovo [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="9c68f-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c68f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c68f-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c68f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9c68f-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="9c68f-106">[in] Flag definiti in Fusion.</span><span class="sxs-lookup"><span data-stu-id="9c68f-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="9c68f-107">Sono supportati i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="9c68f-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="9c68f-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="9c68f-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="9c68f-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0X00000002)</span><span class="sxs-lookup"><span data-stu-id="9c68f-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="9c68f-110">[in] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="9c68f-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="9c68f-111">`pvReserved`deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="9c68f-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="9c68f-112">[out] L'oggetto restituito `IAssemblyCacheItem` puntatore.</span><span class="sxs-lookup"><span data-stu-id="9c68f-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="9c68f-113">[in, facoltativo] Coppie, separati da virgola `name=value` coppie.</span><span class="sxs-lookup"><span data-stu-id="9c68f-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c68f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9c68f-114">Requirements</span></span>  
 <span data-ttu-id="9c68f-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c68f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c68f-116">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9c68f-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9c68f-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c68f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c68f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c68f-118">See Also</span></span>  
 [<span data-ttu-id="9c68f-119">IAssemblyCache (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9c68f-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [<span data-ttu-id="9c68f-120">IAssemblyCacheItem (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9c68f-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)

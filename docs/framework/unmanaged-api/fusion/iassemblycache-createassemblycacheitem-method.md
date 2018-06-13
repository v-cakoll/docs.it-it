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
ms.openlocfilehash: c45257a76127adf2bcf9ab356639d4754d151bf6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430684"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="a5a9a-102">Metodo IAssemblyCache::CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="a5a9a-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="a5a9a-103">Ottiene un riferimento a un nuovo [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="a5a9a-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5a9a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5a9a-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5a9a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a5a9a-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="a5a9a-106">[in] Flag definiti in Fusion.</span><span class="sxs-lookup"><span data-stu-id="a5a9a-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="a5a9a-107">Sono supportati i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="a5a9a-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="a5a9a-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="a5a9a-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="a5a9a-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0X00000002)</span><span class="sxs-lookup"><span data-stu-id="a5a9a-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="a5a9a-110">[in] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="a5a9a-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="a5a9a-111">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="a5a9a-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="a5a9a-112">[out] L'oggetto restituito `IAssemblyCacheItem` puntatore.</span><span class="sxs-lookup"><span data-stu-id="a5a9a-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="a5a9a-113">[in, facoltativo] Coppie, separati da virgola `name=value` coppie.</span><span class="sxs-lookup"><span data-stu-id="a5a9a-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5a9a-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a5a9a-114">Requirements</span></span>  
 <span data-ttu-id="a5a9a-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5a9a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5a9a-116">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a5a9a-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a5a9a-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5a9a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5a9a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5a9a-118">See Also</span></span>  
 [<span data-ttu-id="a5a9a-119">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="a5a9a-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [<span data-ttu-id="a5a9a-120">Interfaccia IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="a5a9a-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)

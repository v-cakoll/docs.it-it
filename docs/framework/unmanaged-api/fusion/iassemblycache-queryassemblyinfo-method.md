---
title: Metodo IAssemblyCache::QueryAssemblyInfo
ms.date: 03/30/2017
api_name:
- IAssemblyCache.QueryAssemblyInfo
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::QueryAssemblyInfo
helpviewer_keywords:
- IAssemblyCache::QueryAssemblyInfo method [.NET Framework fusion]
- QueryAssemblyInfo method [.NET Framework fusion]
ms.assetid: 09313cb5-06f6-43bd-94f4-1055c6b0c99a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81b647032b2e9474e3b4472552ed884cec92ffc3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216419"
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="b3754-102">Metodo IAssemblyCache::QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="b3754-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="b3754-103">Ottiene i dati richiesti sull'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="b3754-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3754-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3754-104">Syntax</span></span>  
  
```  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3754-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b3754-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="b3754-106">[in] Flag definiti in Fusion.</span><span class="sxs-lookup"><span data-stu-id="b3754-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="b3754-107">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3754-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="b3754-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="b3754-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
-   <span data-ttu-id="b3754-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="b3754-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="b3754-110">[in] Il nome dell'assembly per cui verranno recuperati i dati.</span><span class="sxs-lookup"><span data-stu-id="b3754-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="b3754-111">[in, out] Un' [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) struttura che contiene i dati relativi all'assembly.</span><span class="sxs-lookup"><span data-stu-id="b3754-111">[in, out] An [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3754-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b3754-112">Requirements</span></span>  
 <span data-ttu-id="b3754-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3754-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3754-114">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b3754-114">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="b3754-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b3754-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b3754-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3754-116">See also</span></span>

- [<span data-ttu-id="b3754-117">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="b3754-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)

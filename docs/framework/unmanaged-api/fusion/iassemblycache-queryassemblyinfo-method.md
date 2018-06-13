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
ms.openlocfilehash: 6935a72bb99e636b3732958ee88ad224b401513b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430720"
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="1b992-102">Metodo IAssemblyCache::QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="1b992-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="1b992-103">Ottiene i dati richiesti sull'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="1b992-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b992-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b992-104">Syntax</span></span>  
  
```  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b992-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1b992-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="1b992-106">[in] Flag definiti in Fusion.</span><span class="sxs-lookup"><span data-stu-id="1b992-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="1b992-107">Sono supportati i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="1b992-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="1b992-108">QUERYASMINFO_FLAG_VALIDATE (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="1b992-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
-   <span data-ttu-id="1b992-109">QUERYASMINFO_FLAG_GETSIZE (0X00000002)</span><span class="sxs-lookup"><span data-stu-id="1b992-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="1b992-110">[in] Il nome dell'assembly per cui recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="1b992-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="1b992-111">[in, out] Un [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) struttura che contiene dati relativi all'assembly.</span><span class="sxs-lookup"><span data-stu-id="1b992-111">[in, out] An [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b992-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b992-112">Requirements</span></span>  
 <span data-ttu-id="1b992-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b992-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b992-114">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="1b992-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1b992-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b992-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b992-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b992-116">See Also</span></span>  
 [<span data-ttu-id="1b992-117">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="1b992-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)

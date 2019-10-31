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
ms.openlocfilehash: e975db68252e866a0bf7898f1c9d3cbe67bbe24f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134575"
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="58fb0-102">Metodo IAssemblyCache::QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="58fb0-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="58fb0-103">Ottiene i dati richiesti sull'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="58fb0-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58fb0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58fb0-104">Syntax</span></span>  
  
```cpp  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58fb0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="58fb0-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="58fb0-106">in Flag definiti in Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="58fb0-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="58fb0-107">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="58fb0-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="58fb0-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="58fb0-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
- <span data-ttu-id="58fb0-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="58fb0-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="58fb0-110">in Nome dell'assembly per cui verranno recuperati i dati.</span><span class="sxs-lookup"><span data-stu-id="58fb0-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="58fb0-111">[in, out] Struttura [ASSEMBLY_INFO](assembly-info-structure.md) che contiene i dati relativi all'assembly.</span><span class="sxs-lookup"><span data-stu-id="58fb0-111">[in, out] An [ASSEMBLY_INFO](assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58fb0-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58fb0-112">Requirements</span></span>  
 <span data-ttu-id="58fb0-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58fb0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58fb0-114">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="58fb0-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="58fb0-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58fb0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58fb0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58fb0-116">See also</span></span>

- [<span data-ttu-id="58fb0-117">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="58fb0-117">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)

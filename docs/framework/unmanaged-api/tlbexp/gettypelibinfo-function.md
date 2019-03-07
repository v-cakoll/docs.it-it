---
title: Funzione GetTypeLibInfo
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88516a5ab7fa6ce3cd27422b32cb467a94f50f92
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492777"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="5ec2e-102">Funzione GetTypeLibInfo</span><span class="sxs-lookup"><span data-stu-id="5ec2e-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="5ec2e-103">Restituisce informazioni sulla libreria dei tipi specificata esaminando relativa [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) struttura.</span><span class="sxs-lookup"><span data-stu-id="5ec2e-103">Returns information about the specified type library by examining its [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ec2e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ec2e-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ec2e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5ec2e-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="5ec2e-106">[in] Il nome di file della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="5ec2e-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="5ec2e-107">[out] Il GUID della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="5ec2e-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="5ec2e-108">[out] L'ID di localizzazione della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="5ec2e-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="5ec2e-109">[out] Oggetto [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag che identifica il sistema operativo di destinazione della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="5ec2e-109">[out] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="5ec2e-110">I valori comuni sono SYS_WIN32 e SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="5ec2e-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="5ec2e-111">[out] Il numero di versione principale della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="5ec2e-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="5ec2e-112">Ad esempio, per la versione *x. y*, il numero di versione principale viene *x*.</span><span class="sxs-lookup"><span data-stu-id="5ec2e-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="5ec2e-113">[out] Il numero di versione secondaria della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="5ec2e-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="5ec2e-114">Ad esempio, per la versione *x. y*, è il numero di versione secondaria *y*.</span><span class="sxs-lookup"><span data-stu-id="5ec2e-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ec2e-115">Note</span><span class="sxs-lookup"><span data-stu-id="5ec2e-115">Remarks</span></span>  
 <span data-ttu-id="5ec2e-116">Il `GetTypeLibInfo` funzione viene chiamata dal [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="5ec2e-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="5ec2e-117">Questo strumento genera una libreria dei tipi che descrive i tipi in un assembly di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="5ec2e-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="5ec2e-118">Se qualsiasi parametro è null, la funzione restituisce un `HRESULT` di `E_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="5ec2e-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="5ec2e-119">In caso contrario restituirà `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="5ec2e-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ec2e-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5ec2e-120">Requirements</span></span>  
 <span data-ttu-id="5ec2e-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ec2e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ec2e-122">**Intestazione:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="5ec2e-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="5ec2e-123">**Libreria:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="5ec2e-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="5ec2e-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ec2e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ec2e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ec2e-125">See also</span></span>
- [<span data-ttu-id="5ec2e-126">Funzioni di supporto Tlbexp</span><span class="sxs-lookup"><span data-stu-id="5ec2e-126">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="5ec2e-127">Funzione LoadTypeLibEx dell'</span><span class="sxs-lookup"><span data-stu-id="5ec2e-127">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)

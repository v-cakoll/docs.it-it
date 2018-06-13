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
ms.openlocfilehash: 56a9b97f37240e385dbd1788bafea62578d687a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457868"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="912de-102">Funzione GetTypeLibInfo</span><span class="sxs-lookup"><span data-stu-id="912de-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="912de-103">Restituisce informazioni sulla libreria dei tipi specificata esaminando il [TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) struttura.</span><span class="sxs-lookup"><span data-stu-id="912de-103">Returns information about the specified type library by examining its [TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="912de-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="912de-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="912de-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="912de-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="912de-106">[in] Il nome del file della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="912de-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="912de-107">[out] Il GUID della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="912de-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="912de-108">[out] L'ID di localizzazione della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="912de-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="912de-109">[out] Oggetto [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) flag che identifica il sistema operativo di destinazione per la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="912de-109">[out] A [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="912de-110">Valori comuni sono SYS_WIN32 e SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="912de-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="912de-111">[out] Il numero di versione principale della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="912de-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="912de-112">Ad esempio, per la versione *x. y*, il numero di versione principale è *x*.</span><span class="sxs-lookup"><span data-stu-id="912de-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="912de-113">[out] Il numero di versione secondaria della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="912de-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="912de-114">Ad esempio, per la versione *x. y*, il numero di versione secondaria è *y*.</span><span class="sxs-lookup"><span data-stu-id="912de-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="912de-115">Note</span><span class="sxs-lookup"><span data-stu-id="912de-115">Remarks</span></span>  
 <span data-ttu-id="912de-116">Il `GetTypeLibInfo` funzione viene chiamata il [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="912de-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="912de-117">Questo strumento genera una libreria dei tipi che descrive i tipi in un assembly di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="912de-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="912de-118">Se qualsiasi parametro è null, la funzione restituisce un `HRESULT` di `E_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="912de-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="912de-119">In caso contrario restituirà `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="912de-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="912de-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="912de-120">Requirements</span></span>  
 <span data-ttu-id="912de-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="912de-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="912de-122">**Intestazione:** TlbRef. H</span><span class="sxs-lookup"><span data-stu-id="912de-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="912de-123">**Libreria:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="912de-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="912de-124">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="912de-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="912de-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="912de-125">See Also</span></span>  
 [<span data-ttu-id="912de-126">Funzioni di supporto Tlbexp</span><span class="sxs-lookup"><span data-stu-id="912de-126">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 <span data-ttu-id="912de-127">[Funzione LoadTypeLibEx dell'](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)</span><span class="sxs-lookup"><span data-stu-id="912de-127">[LoadTypeLibEx Function](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)</span></span>

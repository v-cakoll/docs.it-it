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
ms.openlocfilehash: e64a0512e05965b3da2e7486e986ee34ca8a20d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73104308"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="15139-102">Funzione GetTypeLibInfo</span><span class="sxs-lookup"><span data-stu-id="15139-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="15139-103">Restituisce informazioni sulla libreria dei tipi specificata esaminando la relativa struttura [TLIBATTR](https://docs.microsoft.com/windows/win32/api/oaidl/ns-oaidl-tlibattr) .</span><span class="sxs-lookup"><span data-stu-id="15139-103">Returns information about the specified type library by examining its [TLIBATTR](https://docs.microsoft.com/windows/win32/api/oaidl/ns-oaidl-tlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15139-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15139-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15139-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="15139-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="15139-106">in Nome del file della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="15139-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="15139-107">out GUID della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="15139-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="15139-108">out ID di localizzazione della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="15139-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="15139-109">out Flag [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) che identifica il sistema operativo di destinazione per la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="15139-109">[out] A [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="15139-110">I valori comuni sono SYS_WIN32 e SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="15139-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="15139-111">out Numero di versione principale della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="15139-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="15139-112">Per la versione *x. y*, ad esempio, il numero di versione principale è *x*.</span><span class="sxs-lookup"><span data-stu-id="15139-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="15139-113">out Numero della versione secondaria della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="15139-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="15139-114">Per la versione *x. y*, ad esempio, il numero di versione secondario è *y*.</span><span class="sxs-lookup"><span data-stu-id="15139-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15139-115">Note</span><span class="sxs-lookup"><span data-stu-id="15139-115">Remarks</span></span>  
 <span data-ttu-id="15139-116">La funzione `GetTypeLibInfo` viene chiamata da [Tlbexp. exe (utilità di esportazione della libreria dei tipi)](../../tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="15139-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="15139-117">Questo strumento genera una libreria dei tipi che descrive i tipi in un assembly Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="15139-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="15139-118">Se un parametro è null, la funzione restituisce un `HRESULT` di `E_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="15139-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="15139-119">In caso contrario restituirà `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="15139-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15139-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="15139-120">Requirements</span></span>  
 <span data-ttu-id="15139-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15139-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15139-122">**Intestazione:** TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="15139-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="15139-123">**Libreria:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="15139-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="15139-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15139-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15139-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15139-125">See also</span></span>

- [<span data-ttu-id="15139-126">Funzioni di supporto Tlbexp</span><span class="sxs-lookup"><span data-stu-id="15139-126">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="15139-127">LoadTypeLibEx (funzione)</span><span class="sxs-lookup"><span data-stu-id="15139-127">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)

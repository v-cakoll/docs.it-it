---
title: Funzione PreBindAssemblyEx
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
ms.openlocfilehash: db3ba3380d1fc30a8f34683618b5cc326d7d1906
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123049"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="8ba19-102">Funzione PreBindAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="8ba19-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="8ba19-103">Ottiene il nome visualizzato post-criteri per un assembly.</span><span class="sxs-lookup"><span data-stu-id="8ba19-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="8ba19-104">Questa funzione supporta l'infrastruttura .NET Framework e non può essere usata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="8ba19-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ba19-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ba19-105">Syntax</span></span>  
  
```cpp  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ba19-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8ba19-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="8ba19-107">in Identifica il contesto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8ba19-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="8ba19-108">in Identifica il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8ba19-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="8ba19-109">in Identifica l'assembly padre.</span><span class="sxs-lookup"><span data-stu-id="8ba19-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="8ba19-110">Questo parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="8ba19-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="8ba19-111">in Identifica la versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="8ba19-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="8ba19-112">out Contiene il nome visualizzato post-criteri.</span><span class="sxs-lookup"><span data-stu-id="8ba19-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="8ba19-113">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="8ba19-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8ba19-114">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="8ba19-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ba19-115">Note</span><span class="sxs-lookup"><span data-stu-id="8ba19-115">Remarks</span></span>  
 <span data-ttu-id="8ba19-116">Il parametro di output `ppNamePostPolicy` viene impostato solo se la funzione restituisce HRESULT FUSION_E_REF_DEF_MISMATCH.</span><span class="sxs-lookup"><span data-stu-id="8ba19-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="8ba19-117">In caso contrario, è null.</span><span class="sxs-lookup"><span data-stu-id="8ba19-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ba19-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ba19-118">Requirements</span></span>  
 <span data-ttu-id="8ba19-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ba19-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ba19-120">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="8ba19-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8ba19-121">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8ba19-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ba19-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ba19-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ba19-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ba19-123">See also</span></span>

- [<span data-ttu-id="8ba19-124">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="8ba19-124">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)

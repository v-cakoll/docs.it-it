---
title: Funzione GetAssemblyIdentityFromFile
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: feb8e5c56ee6ea766cd5f1d10af42699777db453
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654889"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="fa7b9-102">Funzione GetAssemblyIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="fa7b9-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="fa7b9-103">Ottiene un puntatore a un `IUnknown` oggetto con l'oggetto specificato `IID` nell'assembly nel percorso del file specificato.</span><span class="sxs-lookup"><span data-stu-id="fa7b9-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa7b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa7b9-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa7b9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fa7b9-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="fa7b9-106">[in] Un percorso valido per l'assembly richiesto.</span><span class="sxs-lookup"><span data-stu-id="fa7b9-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="fa7b9-107">[in] Il `IID` dell'interfaccia da restituire.</span><span class="sxs-lookup"><span data-stu-id="fa7b9-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="fa7b9-108">[out] Puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="fa7b9-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa7b9-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fa7b9-109">Requirements</span></span>  
 <span data-ttu-id="fa7b9-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa7b9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa7b9-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="fa7b9-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fa7b9-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa7b9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa7b9-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa7b9-113">See also</span></span>
- [<span data-ttu-id="fa7b9-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="fa7b9-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="fa7b9-115">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="fa7b9-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)

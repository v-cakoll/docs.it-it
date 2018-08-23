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
ms.openlocfilehash: 6dfb0b404413351761d269c800be19e75acfb41f
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754479"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="5b03a-102">Funzione GetAssemblyIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="5b03a-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="5b03a-103">Ottiene un puntatore a un `IUnknown` oggetto con l'oggetto specificato `IID` nell'assembly nel percorso del file specificato.</span><span class="sxs-lookup"><span data-stu-id="5b03a-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b03a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b03a-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5b03a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5b03a-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="5b03a-106">[in] Un percorso valido per l'assembly richiesto.</span><span class="sxs-lookup"><span data-stu-id="5b03a-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="5b03a-107">[in] Il `IID` dell'interfaccia da restituire.</span><span class="sxs-lookup"><span data-stu-id="5b03a-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="5b03a-108">[out] Puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="5b03a-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b03a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b03a-109">Requirements</span></span>  
 <span data-ttu-id="5b03a-110">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b03a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b03a-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5b03a-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5b03a-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b03a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b03a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b03a-113">See Also</span></span>  
 [<span data-ttu-id="5b03a-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="5b03a-114">IUnknown</span></span>](/cpp/atl/iunknown)  
 [<span data-ttu-id="5b03a-115">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="5b03a-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)

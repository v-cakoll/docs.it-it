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
ms.openlocfilehash: 581c675cfb69503e6366471a469ffed1a2d13b1a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745237"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="8fadf-102">Funzione GetAssemblyIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="8fadf-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="8fadf-103">Ottiene un puntatore a un `IUnknown` oggetto con l'oggetto specificato `IID` nell'assembly nel percorso del file specificato.</span><span class="sxs-lookup"><span data-stu-id="8fadf-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fadf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8fadf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fadf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8fadf-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="8fadf-106">[in] Un percorso valido per l'assembly richiesto.</span><span class="sxs-lookup"><span data-stu-id="8fadf-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="8fadf-107">[in] Il `IID` dell'interfaccia da restituire.</span><span class="sxs-lookup"><span data-stu-id="8fadf-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="8fadf-108">[out] Puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="8fadf-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fadf-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8fadf-109">Requirements</span></span>  
 <span data-ttu-id="8fadf-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fadf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fadf-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="8fadf-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8fadf-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fadf-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fadf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fadf-113">See also</span></span>

- [<span data-ttu-id="8fadf-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="8fadf-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="8fadf-115">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="8fadf-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)

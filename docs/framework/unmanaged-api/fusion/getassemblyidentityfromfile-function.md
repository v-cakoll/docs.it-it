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
ms.openlocfilehash: 2657ac619bb86bc200de9ce229bf82e4339f78d6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796291"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="108f9-102">Funzione GetAssemblyIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="108f9-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="108f9-103">Ottiene un puntatore a un `IUnknown` oggetto con l'oggetto `IID` specificato nell'assembly nel percorso del file specificato.</span><span class="sxs-lookup"><span data-stu-id="108f9-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="108f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="108f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="108f9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="108f9-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="108f9-106">in Percorso valido dell'assembly richiesto.</span><span class="sxs-lookup"><span data-stu-id="108f9-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="108f9-107">in `IID` Dell'interfaccia da restituire.</span><span class="sxs-lookup"><span data-stu-id="108f9-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="108f9-108">out Puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="108f9-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="108f9-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="108f9-109">Requirements</span></span>  
 <span data-ttu-id="108f9-110">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="108f9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="108f9-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="108f9-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="108f9-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="108f9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="108f9-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="108f9-113">See also</span></span>

- [<span data-ttu-id="108f9-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="108f9-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="108f9-115">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="108f9-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)

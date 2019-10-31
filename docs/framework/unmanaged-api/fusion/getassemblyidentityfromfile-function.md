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
ms.openlocfilehash: 50ec5a23db4d2460480bcc3e463ecd88e7470bde
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134528"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="83554-102">Funzione GetAssemblyIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="83554-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="83554-103">Ottiene un puntatore a un oggetto `IUnknown` con il `IID` specificato nell'assembly nel percorso del file specificato.</span><span class="sxs-lookup"><span data-stu-id="83554-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83554-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83554-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="83554-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="83554-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="83554-106">in Percorso valido dell'assembly richiesto.</span><span class="sxs-lookup"><span data-stu-id="83554-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="83554-107">in `IID` dell'interfaccia da restituire.</span><span class="sxs-lookup"><span data-stu-id="83554-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="83554-108">out Puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="83554-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83554-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83554-109">Requirements</span></span>  
 <span data-ttu-id="83554-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83554-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83554-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="83554-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="83554-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83554-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83554-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83554-113">See also</span></span>

- [<span data-ttu-id="83554-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="83554-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="83554-115">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="83554-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)

---
title: Funzione CallFunctionShim
ms.date: 03/30/2017
api_name:
- CallFunctionShim
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CallFunctionShim
helpviewer_keywords:
- CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31d93ac427ec67726c9456d623aeb683c9029ccd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773770"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="26c32-102">Funzione CallFunctionShim</span><span class="sxs-lookup"><span data-stu-id="26c32-102">CallFunctionShim Function</span></span>
<span data-ttu-id="26c32-103">Effettua una chiamata alla funzione che ha il nome specificato e i parametri nella libreria specificata.</span><span class="sxs-lookup"><span data-stu-id="26c32-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="26c32-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="26c32-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26c32-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26c32-105">Syntax</span></span>  
  
```cpp  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26c32-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="26c32-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="26c32-107">[in] Il nome della libreria che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="26c32-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="26c32-108">[in] Il nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="26c32-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="26c32-109">[in] Il primo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="26c32-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="26c32-110">[in] Il secondo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="26c32-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="26c32-111">[in] La versione della libreria che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="26c32-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="26c32-112">[in] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="26c32-112">[in] Reserved for future use.</span></span> <span data-ttu-id="26c32-113">Passare zero in questo parametro.</span><span class="sxs-lookup"><span data-stu-id="26c32-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26c32-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="26c32-114">Requirements</span></span>  
 <span data-ttu-id="26c32-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26c32-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26c32-116">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="26c32-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="26c32-117">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="26c32-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26c32-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26c32-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c32-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26c32-119">See also</span></span>

- [<span data-ttu-id="26c32-120">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="26c32-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

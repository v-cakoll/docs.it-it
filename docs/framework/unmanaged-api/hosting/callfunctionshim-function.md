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
ms.openlocfilehash: 44f343fa6d9f620145c707e5987ecaedf17dcba8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478986"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="b154c-102">Funzione CallFunctionShim</span><span class="sxs-lookup"><span data-stu-id="b154c-102">CallFunctionShim Function</span></span>
<span data-ttu-id="b154c-103">Effettua una chiamata alla funzione che ha il nome specificato e i parametri nella libreria specificata.</span><span class="sxs-lookup"><span data-stu-id="b154c-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="b154c-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b154c-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b154c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b154c-105">Syntax</span></span>  
  
```  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b154c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b154c-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="b154c-107">[in] Il nome della libreria che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="b154c-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="b154c-108">[in] Il nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="b154c-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="b154c-109">[in] Il primo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="b154c-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="b154c-110">[in] Il secondo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="b154c-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="b154c-111">[in] La versione della libreria che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="b154c-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="b154c-112">[in] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="b154c-112">[in] Reserved for future use.</span></span> <span data-ttu-id="b154c-113">Passare zero in questo parametro.</span><span class="sxs-lookup"><span data-stu-id="b154c-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b154c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b154c-114">Requirements</span></span>  
 <span data-ttu-id="b154c-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b154c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b154c-116">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b154c-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b154c-117">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b154c-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b154c-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b154c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b154c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b154c-119">See also</span></span>
- [<span data-ttu-id="b154c-120">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="b154c-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

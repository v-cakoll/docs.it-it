---
title: Funzione CallFunctionShim
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CallFunctionShim
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CallFunctionShim
helpviewer_keywords: CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12c399c876a244d0c27e34b41e08c284d7429bac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="f3636-102">Funzione CallFunctionShim</span><span class="sxs-lookup"><span data-stu-id="f3636-102">CallFunctionShim Function</span></span>
<span data-ttu-id="f3636-103">Effettua una chiamata alla funzione che contiene i parametri e il nome specificato nella libreria specificata.</span><span class="sxs-lookup"><span data-stu-id="f3636-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="f3636-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3636-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3636-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3636-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="f3636-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f3636-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="f3636-107">[in] Il nome della libreria che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="f3636-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="f3636-108">[in] Il nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="f3636-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="f3636-109">[in] Il primo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="f3636-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="f3636-110">[in] Il secondo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="f3636-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="f3636-111">[in] La versione della libreria che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="f3636-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="f3636-112">[in] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="f3636-112">[in] Reserved for future use.</span></span> <span data-ttu-id="f3636-113">Passare a zero in questo parametro.</span><span class="sxs-lookup"><span data-stu-id="f3636-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3636-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3636-114">Requirements</span></span>  
 <span data-ttu-id="f3636-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3636-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3636-116">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="f3636-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3636-117">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f3636-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3636-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3636-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3636-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3636-119">See Also</span></span>  
 [<span data-ttu-id="f3636-120">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="f3636-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

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
ms.openlocfilehash: 0e6e2e237887ff273ba73e2568c84d2aaaa38383
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="679b9-102">Funzione CallFunctionShim</span><span class="sxs-lookup"><span data-stu-id="679b9-102">CallFunctionShim Function</span></span>
<span data-ttu-id="679b9-103">Effettua una chiamata alla funzione che contiene i parametri e il nome specificato nella libreria specificata.</span><span class="sxs-lookup"><span data-stu-id="679b9-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="679b9-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="679b9-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="679b9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="679b9-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="679b9-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="679b9-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="679b9-107">[in] Il nome della libreria che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="679b9-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="679b9-108">[in] Il nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="679b9-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="679b9-109">[in] Il primo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="679b9-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="679b9-110">[in] Il secondo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="679b9-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="679b9-111">[in] La versione della libreria che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="679b9-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="679b9-112">[in] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="679b9-112">[in] Reserved for future use.</span></span> <span data-ttu-id="679b9-113">Passare a zero in questo parametro.</span><span class="sxs-lookup"><span data-stu-id="679b9-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="679b9-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="679b9-114">Requirements</span></span>  
 <span data-ttu-id="679b9-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="679b9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="679b9-116">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="679b9-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="679b9-117">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="679b9-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="679b9-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="679b9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="679b9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="679b9-119">See Also</span></span>  
 [<span data-ttu-id="679b9-120">Funzioni di Hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="679b9-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

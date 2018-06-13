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
ms.openlocfilehash: 1060ca140db0304c8e5667f7fdf9624b3ac2b64a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429283"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="6fefb-102">Funzione CallFunctionShim</span><span class="sxs-lookup"><span data-stu-id="6fefb-102">CallFunctionShim Function</span></span>
<span data-ttu-id="6fefb-103">Effettua una chiamata alla funzione che contiene i parametri e il nome specificato nella libreria specificata.</span><span class="sxs-lookup"><span data-stu-id="6fefb-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="6fefb-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fefb-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fefb-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6fefb-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="6fefb-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6fefb-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="6fefb-107">[in] Il nome della libreria che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="6fefb-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="6fefb-108">[in] Il nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="6fefb-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="6fefb-109">[in] Il primo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="6fefb-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="6fefb-110">[in] Il secondo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="6fefb-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="6fefb-111">[in] La versione della libreria che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="6fefb-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="6fefb-112">[in] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="6fefb-112">[in] Reserved for future use.</span></span> <span data-ttu-id="6fefb-113">Passare a zero in questo parametro.</span><span class="sxs-lookup"><span data-stu-id="6fefb-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fefb-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6fefb-114">Requirements</span></span>  
 <span data-ttu-id="6fefb-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fefb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fefb-116">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="6fefb-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6fefb-117">**Libreria:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6fefb-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6fefb-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fefb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fefb-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fefb-119">See Also</span></span>  
 [<span data-ttu-id="6fefb-120">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="6fefb-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

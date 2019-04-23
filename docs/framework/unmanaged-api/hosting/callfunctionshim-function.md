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
ms.openlocfilehash: 7aeb813cafbf5b18739c4574c386398ac3c7a77b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180479"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="20556-102">Funzione CallFunctionShim</span><span class="sxs-lookup"><span data-stu-id="20556-102">CallFunctionShim Function</span></span>
<span data-ttu-id="20556-103">Effettua una chiamata alla funzione che ha il nome specificato e i parametri nella libreria specificata.</span><span class="sxs-lookup"><span data-stu-id="20556-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="20556-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20556-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20556-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20556-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="20556-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="20556-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="20556-107">[in] Il nome della libreria che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="20556-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="20556-108">[in] Il nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="20556-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="20556-109">[in] Il primo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="20556-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="20556-110">[in] Il secondo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="20556-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="20556-111">[in] La versione della libreria che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="20556-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="20556-112">[in] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="20556-112">[in] Reserved for future use.</span></span> <span data-ttu-id="20556-113">Passare zero in questo parametro.</span><span class="sxs-lookup"><span data-stu-id="20556-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20556-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="20556-114">Requirements</span></span>  
 <span data-ttu-id="20556-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20556-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20556-116">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="20556-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20556-117">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="20556-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20556-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20556-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20556-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20556-119">See also</span></span>

- [<span data-ttu-id="20556-120">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="20556-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

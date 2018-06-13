---
title: Funzione GetRealProcAddress
ms.date: 03/30/2017
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 256afe9a4304654ddb263a0671db7525f3bedcba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429637"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="b854a-102">Funzione GetRealProcAddress</span><span class="sxs-lookup"><span data-stu-id="b854a-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="b854a-103">Ottiene l'indirizzo della funzione specificata esportata dall'ultima versione installata di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b854a-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="b854a-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b854a-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b854a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b854a-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b854a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b854a-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="b854a-107">[in] Il nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="b854a-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="b854a-108">[out] Posizione che riceve un puntatore all'indirizzo della funzione.</span><span class="sxs-lookup"><span data-stu-id="b854a-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b854a-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b854a-109">Return Value</span></span>  
 <span data-ttu-id="b854a-110">Questo metodo restituisce codici di errore standard del modello COM (Component Object), come definito nel file Winerror. H, oltre ai seguenti valori definiti in CorError.</span><span class="sxs-lookup"><span data-stu-id="b854a-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="b854a-111">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="b854a-111">Return code</span></span>|<span data-ttu-id="b854a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b854a-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b854a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b854a-113">S_OK</span></span>|<span data-ttu-id="b854a-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="b854a-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="b854a-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b854a-115">E_POINTER</span></span>|<span data-ttu-id="b854a-116">`ppv` non è valido.</span><span class="sxs-lookup"><span data-stu-id="b854a-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="b854a-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="b854a-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="b854a-118">La funzione non viene esportata dal runtime.</span><span class="sxs-lookup"><span data-stu-id="b854a-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b854a-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b854a-119">Requirements</span></span>  
 <span data-ttu-id="b854a-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b854a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b854a-121">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="b854a-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b854a-122">**Libreria:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b854a-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b854a-123">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b854a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b854a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b854a-124">See Also</span></span>  
 [<span data-ttu-id="b854a-125">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="b854a-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

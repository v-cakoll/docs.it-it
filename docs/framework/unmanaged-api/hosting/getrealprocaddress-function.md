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
ms.openlocfilehash: 5d4723fbf2311316184cb77c90754d7e037badcd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628080"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="f92f7-102">Funzione GetRealProcAddress</span><span class="sxs-lookup"><span data-stu-id="f92f7-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="f92f7-103">Ottiene l'indirizzo della funzione specificata esportata dall'ultima versione installata di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f92f7-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="f92f7-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f92f7-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f92f7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f92f7-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f92f7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f92f7-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="f92f7-107">[in] Il nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="f92f7-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="f92f7-108">[out] Il percorso che riceve un puntatore all'indirizzo della funzione.</span><span class="sxs-lookup"><span data-stu-id="f92f7-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f92f7-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f92f7-109">Return Value</span></span>  
 <span data-ttu-id="f92f7-110">Questo metodo restituisce codici di errore standard modello COM (Component Object), come definito nel file Winerror. H, oltre ai valori seguenti definiti in CorError.</span><span class="sxs-lookup"><span data-stu-id="f92f7-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="f92f7-111">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="f92f7-111">Return code</span></span>|<span data-ttu-id="f92f7-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f92f7-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f92f7-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f92f7-113">S_OK</span></span>|<span data-ttu-id="f92f7-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="f92f7-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="f92f7-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f92f7-115">E_POINTER</span></span>|<span data-ttu-id="f92f7-116">`ppv` non è valido.</span><span class="sxs-lookup"><span data-stu-id="f92f7-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="f92f7-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="f92f7-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="f92f7-118">La funzione non viene esportata dalla fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f92f7-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f92f7-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f92f7-119">Requirements</span></span>  
 <span data-ttu-id="f92f7-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f92f7-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f92f7-121">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f92f7-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f92f7-122">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f92f7-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f92f7-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f92f7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f92f7-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f92f7-124">See also</span></span>

- [<span data-ttu-id="f92f7-125">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="f92f7-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

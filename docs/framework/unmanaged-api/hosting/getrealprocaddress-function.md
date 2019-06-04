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
ms.openlocfilehash: 40cd5b6298012ef4dc21987a2a2dbe95c02a0ff2
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490359"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="ca763-102">Funzione GetRealProcAddress</span><span class="sxs-lookup"><span data-stu-id="ca763-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="ca763-103">Ottiene l'indirizzo della funzione specificata esportata dall'ultima versione installata di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ca763-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="ca763-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ca763-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca763-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca763-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca763-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ca763-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="ca763-107">[in] Il nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="ca763-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="ca763-108">[out] Il percorso che riceve un puntatore all'indirizzo della funzione.</span><span class="sxs-lookup"><span data-stu-id="ca763-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca763-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ca763-109">Return Value</span></span>  
 <span data-ttu-id="ca763-110">Questo metodo restituisce codici di errore standard modello COM (Component Object), come definito nel file Winerror. H, oltre ai valori seguenti definiti in CorError.</span><span class="sxs-lookup"><span data-stu-id="ca763-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="ca763-111">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="ca763-111">Return code</span></span>|<span data-ttu-id="ca763-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca763-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ca763-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca763-113">S_OK</span></span>|<span data-ttu-id="ca763-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ca763-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="ca763-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ca763-115">E_POINTER</span></span>|<span data-ttu-id="ca763-116">`ppv` non è valido.</span><span class="sxs-lookup"><span data-stu-id="ca763-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="ca763-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="ca763-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="ca763-118">La funzione non viene esportata dalla fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ca763-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca763-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca763-119">Requirements</span></span>  
 <span data-ttu-id="ca763-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca763-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca763-121">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ca763-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca763-122">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ca763-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca763-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca763-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca763-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca763-124">See also</span></span>

- [<span data-ttu-id="ca763-125">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="ca763-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

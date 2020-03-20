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
ms.openlocfilehash: 4c914e00987053b1c1e9e00bf8e54632175e1de8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178167"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="04f54-102">Funzione GetRealProcAddress</span><span class="sxs-lookup"><span data-stu-id="04f54-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="04f54-103">Ottiene l'indirizzo della funzione specificata esportata dall'ultima versione installata di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="04f54-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="04f54-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="04f54-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04f54-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04f54-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04f54-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="04f54-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="04f54-107">[in] Nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="04f54-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="04f54-108">[fuori] Posizione che riceve un puntatore all'indirizzo della funzione.</span><span class="sxs-lookup"><span data-stu-id="04f54-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04f54-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="04f54-109">Return Value</span></span>  
 <span data-ttu-id="04f54-110">Questo metodo restituisce codici di errore COM (Component Object Model) standard, come definito in WinError.h, oltre ai seguenti valori definiti in CorError.h.</span><span class="sxs-lookup"><span data-stu-id="04f54-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="04f54-111">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="04f54-111">Return code</span></span>|<span data-ttu-id="04f54-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04f54-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="04f54-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="04f54-113">S_OK</span></span>|<span data-ttu-id="04f54-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="04f54-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="04f54-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="04f54-115">E_POINTER</span></span>|<span data-ttu-id="04f54-116">`ppv` non è valido.</span><span class="sxs-lookup"><span data-stu-id="04f54-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="04f54-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="04f54-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="04f54-118">La funzione non viene esportata dal runtime.</span><span class="sxs-lookup"><span data-stu-id="04f54-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="04f54-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="04f54-119">Requirements</span></span>  
 <span data-ttu-id="04f54-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04f54-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04f54-121">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="04f54-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04f54-122">**Biblioteca:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="04f54-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04f54-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04f54-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f54-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04f54-124">See also</span></span>

- [<span data-ttu-id="04f54-125">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="04f54-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

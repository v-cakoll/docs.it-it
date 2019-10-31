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
ms.openlocfilehash: 9dffc3d197b05bb71443aa60c101260daabadadd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136401"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="fb518-102">Funzione GetRealProcAddress</span><span class="sxs-lookup"><span data-stu-id="fb518-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="fb518-103">Ottiene l'indirizzo della funzione specificata esportata dalla versione installata più recente del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="fb518-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="fb518-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fb518-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb518-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fb518-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb518-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="fb518-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="fb518-107">in Nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="fb518-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="fb518-108">out Posizione che riceve un puntatore all'indirizzo della funzione.</span><span class="sxs-lookup"><span data-stu-id="fb518-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb518-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fb518-109">Return Value</span></span>  
 <span data-ttu-id="fb518-110">Questo metodo restituisce i codici di errore standard Component Object Model (COM), come definito in WinError. h, oltre ai valori seguenti definiti in CorError. h.</span><span class="sxs-lookup"><span data-stu-id="fb518-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="fb518-111">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="fb518-111">Return code</span></span>|<span data-ttu-id="fb518-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb518-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="fb518-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb518-113">S_OK</span></span>|<span data-ttu-id="fb518-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="fb518-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="fb518-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="fb518-115">E_POINTER</span></span>|<span data-ttu-id="fb518-116">`ppv` non è valido.</span><span class="sxs-lookup"><span data-stu-id="fb518-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="fb518-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="fb518-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="fb518-118">La funzione non viene esportata dal runtime.</span><span class="sxs-lookup"><span data-stu-id="fb518-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb518-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fb518-119">Requirements</span></span>  
 <span data-ttu-id="fb518-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb518-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb518-121">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fb518-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb518-122">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fb518-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb518-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb518-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb518-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb518-124">See also</span></span>

- [<span data-ttu-id="fb518-125">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="fb518-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

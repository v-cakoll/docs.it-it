---
title: Funzione LoadStringRC
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
ms.openlocfilehash: 56ae7b7cf3b577bfe41ebd0bdd98e0da68047b44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176240"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="48f4b-102">Funzione LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="48f4b-102">LoadStringRC Function</span></span>
<span data-ttu-id="48f4b-103">Converte un valore HRESULT in un messaggio di errore utilizzando le impostazioni cultura predefinite del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="48f4b-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="48f4b-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="48f4b-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48f4b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48f4b-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48f4b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="48f4b-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="48f4b-107">[in] Un HRESULT.</span><span class="sxs-lookup"><span data-stu-id="48f4b-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="48f4b-108">[fuori] Buffer che contiene il messaggio di errore al completamento.</span><span class="sxs-lookup"><span data-stu-id="48f4b-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="48f4b-109">[in] Dimensione del buffer dei messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="48f4b-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="48f4b-110">[in] Ignorato.</span><span class="sxs-lookup"><span data-stu-id="48f4b-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48f4b-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="48f4b-111">Return Value</span></span>  
 <span data-ttu-id="48f4b-112">Questo metodo restituisce i codici di errore COM (Component Object Model) standard, come definito in WinError.h, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="48f4b-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="48f4b-113">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="48f4b-113">Return code</span></span>|<span data-ttu-id="48f4b-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="48f4b-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="48f4b-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="48f4b-115">S_OK</span></span>|<span data-ttu-id="48f4b-116">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="48f4b-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="48f4b-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="48f4b-117">E_INVALIDARG</span></span>|<span data-ttu-id="48f4b-118">`szBuffer`è null `iMax` o è zero (0).</span><span class="sxs-lookup"><span data-stu-id="48f4b-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48f4b-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="48f4b-119">Remarks</span></span>  
 <span data-ttu-id="48f4b-120">Se il metodo non `szBuffer` viene completato correttamente, contiene una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="48f4b-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48f4b-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48f4b-121">Requirements</span></span>  
 <span data-ttu-id="48f4b-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48f4b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48f4b-123">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="48f4b-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48f4b-124">**Biblioteca:** MSCorEE.dll e Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="48f4b-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="48f4b-125">Utilizzare MSCorEE.dll anziché Mscorwks.dll per assicurarsi che sia destinata alla versione corretta di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="48f4b-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="48f4b-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48f4b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f4b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48f4b-127">See also</span></span>

- [<span data-ttu-id="48f4b-128">Funzione LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="48f4b-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="48f4b-129">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="48f4b-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

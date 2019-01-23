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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3e6230d245ad36b8d5346aa3b6f8911ef008b61
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526847"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="af279-102">Funzione LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="af279-102">LoadStringRC Function</span></span>
<span data-ttu-id="af279-103">Converte un valore HRESULT in un messaggio di errore usando le impostazioni cultura predefinite del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="af279-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="af279-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af279-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af279-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af279-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af279-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="af279-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="af279-107">[in] Un valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="af279-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="af279-108">[out] Un buffer che contiene il messaggio di errore dopo il corretto completamento.</span><span class="sxs-lookup"><span data-stu-id="af279-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="af279-109">[in] Le dimensioni del buffer di messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="af279-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="af279-110">[in] Ignorato.</span><span class="sxs-lookup"><span data-stu-id="af279-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af279-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="af279-111">Return Value</span></span>  
 <span data-ttu-id="af279-112">Questo metodo restituisce codici di errore standard modello COM (Component Object), come definito nel file Winerror. H, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="af279-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="af279-113">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="af279-113">Return code</span></span>|<span data-ttu-id="af279-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af279-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="af279-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="af279-115">S_OK</span></span>|<span data-ttu-id="af279-116">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="af279-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="af279-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="af279-117">E_INVALIDARG</span></span>|<span data-ttu-id="af279-118">`szBuffer` è null o `iMax` è zero (0).</span><span class="sxs-lookup"><span data-stu-id="af279-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af279-119">Note</span><span class="sxs-lookup"><span data-stu-id="af279-119">Remarks</span></span>  
 <span data-ttu-id="af279-120">Se il metodo non viene completato correttamente, `szBuffer` contiene una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="af279-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af279-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="af279-121">Requirements</span></span>  
 <span data-ttu-id="af279-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af279-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af279-123">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="af279-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af279-124">**Libreria:** Mscoree. dll e mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="af279-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="af279-125">Usare Mscoree. dll invece di Mscorwks. dll per verificare che da usare come destinazione la versione corretta di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="af279-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="af279-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af279-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af279-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af279-127">See also</span></span>
- [<span data-ttu-id="af279-128">Funzione LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="af279-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="af279-129">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="af279-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

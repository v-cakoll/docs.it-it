---
title: Funzione LoadStringRCEx
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c3185bdc0776d6536458ce03c348ed77b8ba0b9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499095"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="72d8f-102">Funzione LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="72d8f-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="72d8f-103">Converte un valore HRESULT a un messaggio di errore appropriato per le impostazioni cultura specificate.</span><span class="sxs-lookup"><span data-stu-id="72d8f-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="72d8f-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72d8f-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72d8f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72d8f-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72d8f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="72d8f-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="72d8f-107">[in] Un identificatore delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="72d8f-107">[in] A culture identifier.</span></span> <span data-ttu-id="72d8f-108">Passare -1 per `lcid` usare le impostazioni cultura predefinite.</span><span class="sxs-lookup"><span data-stu-id="72d8f-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="72d8f-109">[in] Un valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="72d8f-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="72d8f-110">[out] Un buffer che contiene il messaggio di errore dopo il corretto completamento.</span><span class="sxs-lookup"><span data-stu-id="72d8f-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="72d8f-111">[in] Le dimensioni del buffer di messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="72d8f-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="72d8f-112">[in] Ignorato.</span><span class="sxs-lookup"><span data-stu-id="72d8f-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="72d8f-113">[out] Puntatore alla lunghezza del messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="72d8f-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72d8f-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="72d8f-114">Return Value</span></span>  
 <span data-ttu-id="72d8f-115">Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="72d8f-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="72d8f-116">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="72d8f-116">Return code</span></span>|<span data-ttu-id="72d8f-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72d8f-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="72d8f-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="72d8f-118">S_OK</span></span>|<span data-ttu-id="72d8f-119">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="72d8f-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="72d8f-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="72d8f-120">E_INVALIDARG</span></span>|<span data-ttu-id="72d8f-121">`szBuffer` è null, o `iMax` è zero (0).</span><span class="sxs-lookup"><span data-stu-id="72d8f-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72d8f-122">Note</span><span class="sxs-lookup"><span data-stu-id="72d8f-122">Remarks</span></span>  
 <span data-ttu-id="72d8f-123">Se il metodo non viene completato correttamente, `szBuffer` contiene una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="72d8f-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72d8f-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="72d8f-124">Requirements</span></span>  
 <span data-ttu-id="72d8f-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72d8f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72d8f-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="72d8f-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="72d8f-127">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="72d8f-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72d8f-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72d8f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72d8f-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72d8f-129">See also</span></span>
- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="72d8f-130">Funzione LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="72d8f-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="72d8f-131">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="72d8f-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

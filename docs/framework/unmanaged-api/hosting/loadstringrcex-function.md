---
title: Funzione LoadStringRCEx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoadStringRCEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: LoadStringRCEx
helpviewer_keywords: LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3467ebcd0b821c2313f3535c5b594ef664546e4a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="e7765-102">Funzione LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="e7765-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="e7765-103">Converte un valore HRESULT a un messaggio di errore appropriato per le impostazioni cultura specificate.</span><span class="sxs-lookup"><span data-stu-id="e7765-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="e7765-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7765-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7765-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7765-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="e7765-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e7765-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="e7765-107">[in] Un identificatore delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="e7765-107">[in] A culture identifier.</span></span> <span data-ttu-id="e7765-108">Passare -1 `lcid` per utilizzare le impostazioni cultura predefinite.</span><span class="sxs-lookup"><span data-stu-id="e7765-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="e7765-109">[in] Un valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="e7765-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="e7765-110">[out] Un buffer che contiene il messaggio di errore dopo il completamento.</span><span class="sxs-lookup"><span data-stu-id="e7765-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="e7765-111">[in] Le dimensioni del buffer di messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="e7765-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="e7765-112">[in] Ignorato.</span><span class="sxs-lookup"><span data-stu-id="e7765-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="e7765-113">[out] Puntatore alla lunghezza del messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="e7765-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7765-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e7765-114">Return Value</span></span>  
 <span data-ttu-id="e7765-115">Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="e7765-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="e7765-116">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="e7765-116">Return code</span></span>|<span data-ttu-id="e7765-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7765-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="e7765-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="e7765-118">S_OK</span></span>|<span data-ttu-id="e7765-119">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e7765-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="e7765-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e7765-120">E_INVALIDARG</span></span>|<span data-ttu-id="e7765-121">`szBuffer`è null, o `iMax` è zero (0).</span><span class="sxs-lookup"><span data-stu-id="e7765-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7765-122">Note</span><span class="sxs-lookup"><span data-stu-id="e7765-122">Remarks</span></span>  
 <span data-ttu-id="e7765-123">Se il metodo non viene completata correttamente, `szBuffer` contiene una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="e7765-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7765-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e7765-124">Requirements</span></span>  
 <span data-ttu-id="e7765-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7765-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7765-126">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e7765-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7765-127">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e7765-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7765-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7765-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7765-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7765-129">See Also</span></span>  
 <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="e7765-130">LoadStringRC (funzione)</span><span class="sxs-lookup"><span data-stu-id="e7765-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 [<span data-ttu-id="e7765-131">Funzioni di Hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="e7765-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

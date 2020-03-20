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
ms.openlocfilehash: a300c2679ef11a84edb2ab89c8dea96e445c9ee3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177987"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="eee62-102">Funzione LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="eee62-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="eee62-103">Converte un valore HRESULT in un messaggio di errore appropriato per le impostazioni cultura specificate.</span><span class="sxs-lookup"><span data-stu-id="eee62-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="eee62-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="eee62-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eee62-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eee62-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,
    [in]  UINT    iResouceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet,
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eee62-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="eee62-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="eee62-107">[in] Identificatore delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="eee62-107">[in] A culture identifier.</span></span> <span data-ttu-id="eee62-108">Passare -1 `lcid` per utilizzare le impostazioni cultura predefinite.</span><span class="sxs-lookup"><span data-stu-id="eee62-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="eee62-109">[in] Un HRESULT.</span><span class="sxs-lookup"><span data-stu-id="eee62-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="eee62-110">[fuori] Buffer che contiene il messaggio di errore al completamento.</span><span class="sxs-lookup"><span data-stu-id="eee62-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="eee62-111">[in] Dimensione del buffer dei messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="eee62-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="eee62-112">[in] Ignorato.</span><span class="sxs-lookup"><span data-stu-id="eee62-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="eee62-113">[fuori] Puntatore alla lunghezza del messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="eee62-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eee62-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="eee62-114">Return Value</span></span>  
 <span data-ttu-id="eee62-115">Questo metodo restituisce codici di errore COM standard, come definito in WinError.h, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="eee62-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="eee62-116">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="eee62-116">Return code</span></span>|<span data-ttu-id="eee62-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eee62-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="eee62-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="eee62-118">S_OK</span></span>|<span data-ttu-id="eee62-119">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="eee62-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="eee62-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="eee62-120">E_INVALIDARG</span></span>|<span data-ttu-id="eee62-121">`szBuffer`è null `iMax` o è zero (0).</span><span class="sxs-lookup"><span data-stu-id="eee62-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eee62-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="eee62-122">Remarks</span></span>  
 <span data-ttu-id="eee62-123">Se il metodo non `szBuffer` viene completato correttamente, contiene una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="eee62-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eee62-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eee62-124">Requirements</span></span>  
 <span data-ttu-id="eee62-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eee62-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eee62-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eee62-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eee62-127">**Biblioteca:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="eee62-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eee62-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eee62-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee62-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eee62-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="eee62-130">Funzione LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="eee62-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="eee62-131">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="eee62-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

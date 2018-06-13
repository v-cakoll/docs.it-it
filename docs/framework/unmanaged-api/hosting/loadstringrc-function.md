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
ms.openlocfilehash: 463bcf451574700d02f933d024ea5c24cedd259d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441815"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="08cb3-102">Funzione LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="08cb3-102">LoadStringRC Function</span></span>
<span data-ttu-id="08cb3-103">Converte un valore HRESULT in un messaggio di errore utilizzando le impostazioni cultura predefinite del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="08cb3-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="08cb3-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08cb3-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08cb3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08cb3-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08cb3-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="08cb3-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="08cb3-107">[in] Un valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="08cb3-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="08cb3-108">[out] Un buffer che contiene il messaggio di errore dopo il completamento.</span><span class="sxs-lookup"><span data-stu-id="08cb3-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="08cb3-109">[in] Le dimensioni del buffer di messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="08cb3-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="08cb3-110">[in] Ignorato.</span><span class="sxs-lookup"><span data-stu-id="08cb3-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08cb3-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="08cb3-111">Return Value</span></span>  
 <span data-ttu-id="08cb3-112">Questo metodo restituisce codici di errore standard del modello COM (Component Object), come definito nel file Winerror. H, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="08cb3-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="08cb3-113">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="08cb3-113">Return code</span></span>|<span data-ttu-id="08cb3-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08cb3-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="08cb3-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="08cb3-115">S_OK</span></span>|<span data-ttu-id="08cb3-116">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="08cb3-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="08cb3-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="08cb3-117">E_INVALIDARG</span></span>|<span data-ttu-id="08cb3-118">`szBuffer` è null o `iMax` è zero (0).</span><span class="sxs-lookup"><span data-stu-id="08cb3-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08cb3-119">Note</span><span class="sxs-lookup"><span data-stu-id="08cb3-119">Remarks</span></span>  
 <span data-ttu-id="08cb3-120">Se il metodo non viene completata correttamente, `szBuffer` contiene una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="08cb3-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08cb3-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08cb3-121">Requirements</span></span>  
 <span data-ttu-id="08cb3-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08cb3-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08cb3-123">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="08cb3-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08cb3-124">**Libreria:** Mscoree. dll e mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="08cb3-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="08cb3-125">Utilizzare MSCorEE.dll anziché Mscorwks.dll per assicurarsi che la versione corretta di .NET Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="08cb3-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="08cb3-126">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08cb3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08cb3-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08cb3-127">See Also</span></span>  
 [<span data-ttu-id="08cb3-128">Funzione LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="08cb3-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 [<span data-ttu-id="08cb3-129">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="08cb3-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

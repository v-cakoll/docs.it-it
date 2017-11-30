---
title: Funzione GetHashFromBlob
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromBlob
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromBlob
helpviewer_keywords: GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 360036cd1578c2845f09f92c09d79e44618abe75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="42a14-102">Funzione GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="42a14-102">GetHashFromBlob Function</span></span>
<span data-ttu-id="42a14-103">Ottiene un hash dell'assembly nell'indirizzo di memoria specificata, utilizzando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="42a14-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="42a14-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="42a14-104">This function has been deprecated.</span></span> <span data-ttu-id="42a14-105">Utilizzare il [ICLRStronName:: GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="42a14-105">Use the [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42a14-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42a14-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42a14-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="42a14-107">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="42a14-108">[in] Un puntatore all'indirizzo del blocco di memoria per eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="42a14-108">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="42a14-109">[in] La lunghezza, espressa in byte, del blocco di memoria.</span><span class="sxs-lookup"><span data-stu-id="42a14-109">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="42a14-110">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="42a14-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="42a14-111">Utilizzare zero per l'algoritmo predefinito.</span><span class="sxs-lookup"><span data-stu-id="42a14-111">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="42a14-112">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="42a14-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="42a14-113">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="42a14-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="42a14-114">[out] Le dimensioni, in byte, dell'oggetto restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="42a14-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42a14-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42a14-115">Requirements</span></span>  
 <span data-ttu-id="42a14-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42a14-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42a14-117">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="42a14-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="42a14-118">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="42a14-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42a14-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42a14-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a14-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42a14-120">See Also</span></span>  
 [<span data-ttu-id="42a14-121">GetHashFromBlob (metodo)</span><span class="sxs-lookup"><span data-stu-id="42a14-121">GetHashFromBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)  
 [<span data-ttu-id="42a14-122">ICLRStrongName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="42a14-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

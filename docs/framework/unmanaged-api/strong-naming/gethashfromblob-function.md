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
ms.workload: dotnet
ms.openlocfilehash: 4564ea36ed8dd4c5de0d1633ba791b47bc2a01b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="21627-102">Funzione GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="21627-102">GetHashFromBlob Function</span></span>
<span data-ttu-id="21627-103">Ottiene un hash dell'assembly nell'indirizzo di memoria specificata, utilizzando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="21627-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="21627-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="21627-104">This function has been deprecated.</span></span> <span data-ttu-id="21627-105">Utilizzare il [ICLRStronName:: GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="21627-105">Use the [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21627-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21627-106">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="21627-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="21627-107">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="21627-108">[in] Un puntatore all'indirizzo del blocco di memoria per eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="21627-108">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="21627-109">[in] La lunghezza, espressa in byte, del blocco di memoria.</span><span class="sxs-lookup"><span data-stu-id="21627-109">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="21627-110">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="21627-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="21627-111">Utilizzare zero per l'algoritmo predefinito.</span><span class="sxs-lookup"><span data-stu-id="21627-111">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="21627-112">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="21627-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="21627-113">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="21627-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="21627-114">[out] Le dimensioni, in byte, dell'oggetto restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="21627-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21627-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="21627-115">Requirements</span></span>  
 <span data-ttu-id="21627-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21627-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21627-117">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="21627-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="21627-118">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="21627-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="21627-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21627-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21627-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21627-120">See Also</span></span>  
 [<span data-ttu-id="21627-121">Metodo GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="21627-121">GetHashFromBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)  
 [<span data-ttu-id="21627-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="21627-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

---
title: Funzione GetHashFromBlob
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 427d93a9aff527d36720c4199782fa104a66f8d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455033"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="1df9e-102">Funzione GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="1df9e-102">GetHashFromBlob Function</span></span>
<span data-ttu-id="1df9e-103">Ottiene un hash dell'assembly nell'indirizzo di memoria specificata, utilizzando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="1df9e-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="1df9e-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="1df9e-104">This function has been deprecated.</span></span> <span data-ttu-id="1df9e-105">Utilizzare il [ICLRStronName:: GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="1df9e-105">Use the [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1df9e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1df9e-106">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="1df9e-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="1df9e-107">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="1df9e-108">[in] Un puntatore all'indirizzo del blocco di memoria per eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="1df9e-108">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="1df9e-109">[in] La lunghezza, espressa in byte, del blocco di memoria.</span><span class="sxs-lookup"><span data-stu-id="1df9e-109">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="1df9e-110">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="1df9e-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="1df9e-111">Utilizzare zero per l'algoritmo predefinito.</span><span class="sxs-lookup"><span data-stu-id="1df9e-111">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="1df9e-112">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="1df9e-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="1df9e-113">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="1df9e-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="1df9e-114">[out] Le dimensioni, in byte, dell'oggetto restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="1df9e-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1df9e-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1df9e-115">Requirements</span></span>  
 <span data-ttu-id="1df9e-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1df9e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1df9e-117">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="1df9e-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1df9e-118">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1df9e-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1df9e-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1df9e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1df9e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1df9e-120">See Also</span></span>  
 [<span data-ttu-id="1df9e-121">Metodo GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="1df9e-121">GetHashFromBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)  
 [<span data-ttu-id="1df9e-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="1df9e-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

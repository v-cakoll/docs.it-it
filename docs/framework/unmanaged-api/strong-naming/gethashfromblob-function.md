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
ms.openlocfilehash: 6ba049723710b378a90d17c67735a05e8a09d05d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636856"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="d8243-102">Funzione GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="d8243-102">GetHashFromBlob Function</span></span>

<span data-ttu-id="d8243-103">Ottiene un hash dell'assembly all'indirizzo di memoria specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="d8243-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="d8243-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="d8243-104">This function has been deprecated.</span></span> <span data-ttu-id="d8243-105">Usare la [GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="d8243-105">Use the [ICLRStrongName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="d8243-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8243-106">Syntax</span></span>

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a><span data-ttu-id="d8243-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8243-107">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="d8243-108">[in] Un puntatore all'indirizzo del blocco di memoria per eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="d8243-108">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="d8243-109">[in] La lunghezza, espressa in byte, del blocco di memoria.</span><span class="sxs-lookup"><span data-stu-id="d8243-109">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="d8243-110">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d8243-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d8243-111">Usa lo zero per l'algoritmo predefinito.</span><span class="sxs-lookup"><span data-stu-id="d8243-111">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="d8243-112">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="d8243-112">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="d8243-113">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d8243-113">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="d8243-114">[out] Le dimensioni, in byte, del valore restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d8243-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="d8243-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8243-115">Requirements</span></span>

<span data-ttu-id="d8243-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8243-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d8243-117">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d8243-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="d8243-118">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d8243-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="d8243-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8243-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d8243-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8243-120">See also</span></span>

- [<span data-ttu-id="d8243-121">Metodo GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="d8243-121">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="d8243-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d8243-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

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
ms.openlocfilehash: 59b4df08157ce14a58393e54b671e8f41b8998ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799226"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="59f56-102">Funzione GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="59f56-102">GetHashFromBlob Function</span></span>

<span data-ttu-id="59f56-103">Ottiene un hash dell'assembly all'indirizzo di memoria specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="59f56-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="59f56-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="59f56-104">This function has been deprecated.</span></span> <span data-ttu-id="59f56-105">Usare invece il metodo [ICLRStrongName:: GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) .</span><span class="sxs-lookup"><span data-stu-id="59f56-105">Use the [ICLRStrongName::GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="59f56-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59f56-106">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="59f56-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="59f56-107">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="59f56-108">in Puntatore all'indirizzo del blocco di memoria di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="59f56-108">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="59f56-109">in Lunghezza, in byte, del blocco di memoria.</span><span class="sxs-lookup"><span data-stu-id="59f56-109">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="59f56-110">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="59f56-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="59f56-111">Usare zero per l'algoritmo predefinito.</span><span class="sxs-lookup"><span data-stu-id="59f56-111">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="59f56-112">out Buffer hash restituito.</span><span class="sxs-lookup"><span data-stu-id="59f56-112">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="59f56-113">in Dimensione massima richiesta di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="59f56-113">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="59f56-114">out Dimensione, in byte, dell'oggetto restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="59f56-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="59f56-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="59f56-115">Requirements</span></span>

<span data-ttu-id="59f56-116">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59f56-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="59f56-117">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="59f56-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="59f56-118">**Libreria** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="59f56-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="59f56-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59f56-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="59f56-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59f56-120">See also</span></span>

- [<span data-ttu-id="59f56-121">Metodo GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="59f56-121">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="59f56-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="59f56-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

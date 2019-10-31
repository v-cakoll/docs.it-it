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
ms.openlocfilehash: d1027aea1d800bda1654b223fec992aa70efd4b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140719"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="d218b-102">Funzione GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="d218b-102">GetHashFromBlob Function</span></span>

<span data-ttu-id="d218b-103">Ottiene un hash dell'assembly all'indirizzo di memoria specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="d218b-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="d218b-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="d218b-104">This function has been deprecated.</span></span> <span data-ttu-id="d218b-105">Usare invece il metodo [ICLRStrongName:: GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d218b-105">Use the [ICLRStrongName::GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="d218b-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d218b-106">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="d218b-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="d218b-107">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="d218b-108">in Puntatore all'indirizzo del blocco di memoria di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="d218b-108">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="d218b-109">in Lunghezza, in byte, del blocco di memoria.</span><span class="sxs-lookup"><span data-stu-id="d218b-109">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="d218b-110">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d218b-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d218b-111">Usare zero per l'algoritmo predefinito.</span><span class="sxs-lookup"><span data-stu-id="d218b-111">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="d218b-112">out Buffer hash restituito.</span><span class="sxs-lookup"><span data-stu-id="d218b-112">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="d218b-113">in Dimensioni massime richieste di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d218b-113">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="d218b-114">out Dimensione, in byte, dell'oggetto restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d218b-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="d218b-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d218b-115">Requirements</span></span>

<span data-ttu-id="d218b-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d218b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d218b-117">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="d218b-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="d218b-118">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d218b-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="d218b-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d218b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d218b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d218b-120">See also</span></span>

- [<span data-ttu-id="d218b-121">Metodo GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="d218b-121">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="d218b-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d218b-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

---
title: Funzione GetHashFromAssemblyFileW
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4b748370ff1aff042923002ad827a0e39d99963
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799275"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="837e5-102">Funzione GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="837e5-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="837e5-103">Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="837e5-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="837e5-104">Il percorso del file di assembly deve essere specificato come stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="837e5-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="837e5-105">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="837e5-105">This function has been deprecated.</span></span> <span data-ttu-id="837e5-106">Usare invece il metodo [ICLRStrongName:: GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) .</span><span class="sxs-lookup"><span data-stu-id="837e5-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="837e5-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="837e5-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="837e5-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="837e5-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="837e5-109">in Percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="837e5-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="837e5-110">Questo parametro deve essere una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="837e5-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="837e5-111">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="837e5-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="837e5-112">Usare zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="837e5-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="837e5-113">out Buffer hash restituito.</span><span class="sxs-lookup"><span data-stu-id="837e5-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="837e5-114">in Dimensione massima richiesta di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="837e5-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="837e5-115">out Dimensione restituita, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="837e5-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="837e5-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="837e5-116">Requirements</span></span>  
 <span data-ttu-id="837e5-117">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="837e5-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="837e5-118">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="837e5-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="837e5-119">**Libreria** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="837e5-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="837e5-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="837e5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="837e5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="837e5-121">See also</span></span>

- [<span data-ttu-id="837e5-122">Metodo GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="837e5-122">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="837e5-123">Metodo GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="837e5-123">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="837e5-124">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="837e5-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

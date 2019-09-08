---
title: Funzione GetHashFromFileW
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd96b5acb22f63b6e06c981119186680d6593a79
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799191"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="d1b63-102">Funzione GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="d1b63-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="d1b63-103">Genera un hash basato sul contenuto del file specificato da una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="d1b63-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="d1b63-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="d1b63-104">This function has been deprecated.</span></span> <span data-ttu-id="d1b63-105">Usare invece il metodo [ICLRStrongName:: GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d1b63-105">Use the [ICLRStrongName::GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1b63-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d1b63-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="d1b63-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="d1b63-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d1b63-108">in Nome Unicode del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="d1b63-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d1b63-109">[in, out] Algoritmo da utilizzare durante la generazione dell'hash.</span><span class="sxs-lookup"><span data-stu-id="d1b63-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="d1b63-110">Gli algoritmi validi sono quelli definiti dalla CryptoAPI Win32.</span><span class="sxs-lookup"><span data-stu-id="d1b63-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="d1b63-111">Se `piHashAlg` è impostato su 0, viene utilizzato l'algoritmo predefinito CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="d1b63-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d1b63-112">out Matrice di byte contenente l'hash generato.</span><span class="sxs-lookup"><span data-stu-id="d1b63-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d1b63-113">in Dimensione massima del buffer a cui `pbHash`punta.</span><span class="sxs-lookup"><span data-stu-id="d1b63-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d1b63-114">out Dimensione, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d1b63-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1b63-115">Note</span><span class="sxs-lookup"><span data-stu-id="d1b63-115">Remarks</span></span>  
 <span data-ttu-id="d1b63-116">Questa funzione è identica a [GetHashFromFile](gethashfromfile-function.md), con la differenza che la specifica del nome file è Unicode anziché ANSI.</span><span class="sxs-lookup"><span data-stu-id="d1b63-116">This function is the same as [GetHashFromFile](gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1b63-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d1b63-117">Requirements</span></span>  
 <span data-ttu-id="d1b63-118">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1b63-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1b63-119">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="d1b63-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d1b63-120">**Libreria** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d1b63-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d1b63-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1b63-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1b63-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1b63-122">See also</span></span>

- [<span data-ttu-id="d1b63-123">Metodo GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="d1b63-123">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="d1b63-124">Metodo GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="d1b63-124">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="d1b63-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d1b63-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

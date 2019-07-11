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
ms.openlocfilehash: 77b164cdec0dd224042e4de3265d14a4991d60ba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771900"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="7444e-102">Funzione GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="7444e-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="7444e-103">Genera un hash basato sul contenuto del file specificato da una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="7444e-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="7444e-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="7444e-104">This function has been deprecated.</span></span> <span data-ttu-id="7444e-105">Usare la [GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="7444e-105">Use the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7444e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7444e-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="7444e-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="7444e-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="7444e-108">[in] Il nome di Unicode del file da hash.</span><span class="sxs-lookup"><span data-stu-id="7444e-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="7444e-109">[in, out] L'algoritmo da utilizzare durante la generazione di hash.</span><span class="sxs-lookup"><span data-stu-id="7444e-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="7444e-110">Gli algoritmi validi sono quelli definiti per la funzione CryptoAPI Win32.</span><span class="sxs-lookup"><span data-stu-id="7444e-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="7444e-111">Se `piHashAlg` è impostato su 0, l'algoritmo predefinito viene utilizzato CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="7444e-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="7444e-112">[out] Matrice di byte contenente il valore hash generato.</span><span class="sxs-lookup"><span data-stu-id="7444e-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="7444e-113">[in] Le dimensioni massime del buffer a cui punta `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="7444e-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="7444e-114">[out] Le dimensioni, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="7444e-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7444e-115">Note</span><span class="sxs-lookup"><span data-stu-id="7444e-115">Remarks</span></span>  
 <span data-ttu-id="7444e-116">Questa funzione equivale [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), ad eccezione del fatto che la specifica del nome file è in formato Unicode anziché ANSI.</span><span class="sxs-lookup"><span data-stu-id="7444e-116">This function is the same as [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7444e-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7444e-117">Requirements</span></span>  
 <span data-ttu-id="7444e-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7444e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7444e-119">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="7444e-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7444e-120">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7444e-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7444e-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7444e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7444e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7444e-122">See also</span></span>

- [<span data-ttu-id="7444e-123">Metodo GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="7444e-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="7444e-124">Metodo GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="7444e-124">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="7444e-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="7444e-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

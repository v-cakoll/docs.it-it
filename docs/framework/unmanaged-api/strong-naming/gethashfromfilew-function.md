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
ms.openlocfilehash: 9be512bab30e08ddeb7deadf8a29263e928549a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134615"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="7f3bf-102">Funzione GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="7f3bf-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="7f3bf-103">Genera un hash basato sul contenuto del file specificato da una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="7f3bf-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="7f3bf-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="7f3bf-104">This function has been deprecated.</span></span> <span data-ttu-id="7f3bf-105">Usare la [GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="7f3bf-105">Use the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f3bf-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f3bf-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="7f3bf-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="7f3bf-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="7f3bf-108">[in] Il nome di Unicode del file da hash.</span><span class="sxs-lookup"><span data-stu-id="7f3bf-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="7f3bf-109">[in, out] L'algoritmo da utilizzare durante la generazione di hash.</span><span class="sxs-lookup"><span data-stu-id="7f3bf-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="7f3bf-110">Gli algoritmi validi sono quelli definiti per la funzione CryptoAPI Win32.</span><span class="sxs-lookup"><span data-stu-id="7f3bf-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="7f3bf-111">Se `piHashAlg` è impostato su 0, l'algoritmo predefinito viene utilizzato CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="7f3bf-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="7f3bf-112">[out] Matrice di byte contenente il valore hash generato.</span><span class="sxs-lookup"><span data-stu-id="7f3bf-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="7f3bf-113">[in] Le dimensioni massime del buffer a cui punta `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="7f3bf-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="7f3bf-114">[out] Le dimensioni, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="7f3bf-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f3bf-115">Note</span><span class="sxs-lookup"><span data-stu-id="7f3bf-115">Remarks</span></span>  
 <span data-ttu-id="7f3bf-116">Questa funzione equivale [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), ad eccezione del fatto che la specifica del nome file è in formato Unicode anziché ANSI.</span><span class="sxs-lookup"><span data-stu-id="7f3bf-116">This function is the same as [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f3bf-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f3bf-117">Requirements</span></span>  
 <span data-ttu-id="7f3bf-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f3bf-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f3bf-119">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="7f3bf-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7f3bf-120">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7f3bf-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="7f3bf-121">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7f3bf-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7f3bf-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f3bf-122">See also</span></span>

- [<span data-ttu-id="7f3bf-123">Metodo GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="7f3bf-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="7f3bf-124">Metodo GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="7f3bf-124">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="7f3bf-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="7f3bf-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

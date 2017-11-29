---
title: Funzione GetHashFromFileW
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromFileW
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromFileW
helpviewer_keywords: GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2c19047f03279b1284ea8b5b8f99785cfaff5146
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="50073-102">Funzione GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="50073-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="50073-103">Genera un hash per il contenuto del file specificato da una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="50073-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="50073-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="50073-104">This function has been deprecated.</span></span> <span data-ttu-id="50073-105">Utilizzare il [ICLRStrongName:: GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="50073-105">Use the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50073-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50073-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="50073-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="50073-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="50073-108">[in] Nome del file hash Unicode.</span><span class="sxs-lookup"><span data-stu-id="50073-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="50073-109">[in, out] L'algoritmo da utilizzare durante la generazione di hash.</span><span class="sxs-lookup"><span data-stu-id="50073-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="50073-110">Gli algoritmi validi sono quelli definiti in CryptoAPI Win32.</span><span class="sxs-lookup"><span data-stu-id="50073-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="50073-111">Se `piHashAlg` è impostato su 0, l'algoritmo predefinito CALG_SHA-1 viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="50073-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="50073-112">[out] Matrice di byte contenente il valore hash generato.</span><span class="sxs-lookup"><span data-stu-id="50073-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="50073-113">[in] La dimensione massima del buffer a cui puntava `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="50073-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="50073-114">[out] Le dimensioni, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="50073-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50073-115">Note</span><span class="sxs-lookup"><span data-stu-id="50073-115">Remarks</span></span>  
 <span data-ttu-id="50073-116">Questa funzione è analoga [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), ad eccezione del fatto che la specifica del nome di file in formato Unicode anziché ANSI.</span><span class="sxs-lookup"><span data-stu-id="50073-116">This function is the same as [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50073-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50073-117">Requirements</span></span>  
 <span data-ttu-id="50073-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50073-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50073-119">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="50073-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="50073-120">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="50073-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50073-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50073-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50073-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50073-122">See Also</span></span>  
 [<span data-ttu-id="50073-123">GetHashFromFileW (metodo)</span><span class="sxs-lookup"><span data-stu-id="50073-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [<span data-ttu-id="50073-124">GetHashFromFile (metodo)</span><span class="sxs-lookup"><span data-stu-id="50073-124">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [<span data-ttu-id="50073-125">ICLRStrongName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="50073-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

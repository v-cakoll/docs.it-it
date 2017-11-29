---
title: Funzione GetHashFromFile
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromFile
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromFile
helpviewer_keywords: GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c8e84881822cbafa8c43c3669f7522c390d5c5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="a7d95-102">Funzione GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="a7d95-102">GetHashFromFile Function</span></span>
<span data-ttu-id="a7d95-103">Genera un hash per il contenuto del file specificato.</span><span class="sxs-lookup"><span data-stu-id="a7d95-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="a7d95-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="a7d95-104">This function has been deprecated.</span></span> <span data-ttu-id="a7d95-105">Utilizzare il [ICLRStrongName:: GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="a7d95-105">Use the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7d95-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7d95-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7d95-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="a7d95-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="a7d95-108">[in] Il nome del file con hash.</span><span class="sxs-lookup"><span data-stu-id="a7d95-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="a7d95-109">[in, out] L'algoritmo da utilizzare durante la generazione di hash.</span><span class="sxs-lookup"><span data-stu-id="a7d95-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="a7d95-110">Gli algoritmi validi sono quelli definiti in CryptoAPI Win32.</span><span class="sxs-lookup"><span data-stu-id="a7d95-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="a7d95-111">Se `piHashAlg` è impostato su 0, l'algoritmo predefinito CALG_SHA-1 viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="a7d95-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="a7d95-112">[out] Matrice di byte contenente il valore hash generato.</span><span class="sxs-lookup"><span data-stu-id="a7d95-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="a7d95-113">[in] La dimensione massima del buffer che `pbHash` punta a.</span><span class="sxs-lookup"><span data-stu-id="a7d95-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="a7d95-114">[out] Le dimensioni, in byte, dell'oggetto restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="a7d95-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7d95-115">Note</span><span class="sxs-lookup"><span data-stu-id="a7d95-115">Remarks</span></span>  
 <span data-ttu-id="a7d95-116">Questa funzione è analoga [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), ad eccezione del fatto che la specifica del nome file è ANSI anziché Unicode.</span><span class="sxs-lookup"><span data-stu-id="a7d95-116">This function is the same as [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7d95-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7d95-117">Requirements</span></span>  
 <span data-ttu-id="a7d95-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7d95-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7d95-119">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="a7d95-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a7d95-120">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7d95-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a7d95-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7d95-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7d95-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7d95-122">See Also</span></span>  
 [<span data-ttu-id="a7d95-123">GetHashFromFile (metodo)</span><span class="sxs-lookup"><span data-stu-id="a7d95-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [<span data-ttu-id="a7d95-124">GetHashFromFileW (metodo)</span><span class="sxs-lookup"><span data-stu-id="a7d95-124">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [<span data-ttu-id="a7d95-125">ICLRStrongName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a7d95-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

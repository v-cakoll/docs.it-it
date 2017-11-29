---
title: Metodo ICLRStrongName::GetHashFromFile
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.GetHashFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bccdb01e098015f61a29ba267da1f3ec37543fcd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="0f754-102">Metodo ICLRStrongName::GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="0f754-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="0f754-103">Genera un hash per il contenuto del file specificato.</span><span class="sxs-lookup"><span data-stu-id="0f754-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f754-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f754-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f754-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0f754-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="0f754-106">[in] Il nome del file con hash.</span><span class="sxs-lookup"><span data-stu-id="0f754-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="0f754-107">[in, out] L'algoritmo da utilizzare durante la generazione di hash.</span><span class="sxs-lookup"><span data-stu-id="0f754-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="0f754-108">Gli algoritmi validi sono quelli definiti in CryptoAPI Win32.</span><span class="sxs-lookup"><span data-stu-id="0f754-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="0f754-109">Se `piHashAlg` è impostato su 0, l'algoritmo predefinito CALG_SHA-1 viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="0f754-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="0f754-110">[out] Matrice di byte contenente il valore hash generato.</span><span class="sxs-lookup"><span data-stu-id="0f754-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="0f754-111">[in] La dimensione massima del buffer che `pbHash` punta a.</span><span class="sxs-lookup"><span data-stu-id="0f754-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="0f754-112">[out] Le dimensioni, in byte, dell'oggetto restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="0f754-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f754-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0f754-113">Return Value</span></span>  
 <span data-ttu-id="0f754-114">`S_OK`Se il metodo viene completato correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="0f754-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f754-115">Note</span><span class="sxs-lookup"><span data-stu-id="0f754-115">Remarks</span></span>  
 <span data-ttu-id="0f754-116">Questo metodo è lo stesso come il [ICLRStrongName:: GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) metodo, ad eccezione del fatto che il nome del file specifica è ANSI anziché Unicode.</span><span class="sxs-lookup"><span data-stu-id="0f754-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f754-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0f754-117">Requirements</span></span>  
 <span data-ttu-id="0f754-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f754-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f754-119">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="0f754-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0f754-120">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0f754-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f754-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f754-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f754-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f754-122">See Also</span></span>  
 [<span data-ttu-id="0f754-123">GetHashFromFileW (metodo)</span><span class="sxs-lookup"><span data-stu-id="0f754-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [<span data-ttu-id="0f754-124">ICLRStrongName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="0f754-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

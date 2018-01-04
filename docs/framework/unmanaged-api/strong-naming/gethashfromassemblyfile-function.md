---
title: Funzione GetHashFromAssemblyFile
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromAssemblyFile
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromAssemblyFile
helpviewer_keywords: GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed5de637f8b8d51e2619ba205d89c753b27722bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="2f003-102">Funzione GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="2f003-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="2f003-103">Ottiene un hash del file di assembly specificato, usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="2f003-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="2f003-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="2f003-104">This function has been deprecated.</span></span> <span data-ttu-id="2f003-105">Utilizzare il [:: GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="2f003-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f003-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f003-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f003-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="2f003-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="2f003-108">[in] Il percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="2f003-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="2f003-109">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="2f003-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="2f003-110">Utilizzare zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="2f003-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="2f003-111">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="2f003-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="2f003-112">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="2f003-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="2f003-113">[out] La dimensione restituita, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="2f003-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f003-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2f003-114">Requirements</span></span>  
 <span data-ttu-id="2f003-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f003-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f003-116">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="2f003-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="2f003-117">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2f003-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2f003-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f003-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f003-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f003-119">See Also</span></span>  
 [<span data-ttu-id="2f003-120">Metodo GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="2f003-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="2f003-121">Metodo GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="2f003-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="2f003-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="2f003-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

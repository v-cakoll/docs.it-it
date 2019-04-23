---
title: Funzione GetHashFromAssemblyFile
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e56a509d08b19cf449177984e7b59481eb7b09a9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092162"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="d6b9b-102">Funzione GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="d6b9b-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="d6b9b-103">Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="d6b9b-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="d6b9b-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="d6b9b-104">This function has been deprecated.</span></span> <span data-ttu-id="d6b9b-105">Usare la [GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="d6b9b-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6b9b-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6b9b-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6b9b-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6b9b-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="d6b9b-108">[in] Il percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="d6b9b-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d6b9b-109">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d6b9b-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d6b9b-110">Usa lo zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="d6b9b-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d6b9b-111">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="d6b9b-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d6b9b-112">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d6b9b-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d6b9b-113">[out] La dimensione restituita, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d6b9b-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6b9b-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d6b9b-114">Requirements</span></span>  
 <span data-ttu-id="d6b9b-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6b9b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6b9b-116">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d6b9b-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d6b9b-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d6b9b-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d6b9b-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6b9b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b9b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6b9b-119">See also</span></span>

- [<span data-ttu-id="d6b9b-120">Metodo GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="d6b9b-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="d6b9b-121">Metodo GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="d6b9b-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="d6b9b-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d6b9b-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

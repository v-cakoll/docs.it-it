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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049401"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="d9bdf-102">Funzione GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="d9bdf-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="d9bdf-103">Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="d9bdf-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-104">This function has been deprecated.</span></span> <span data-ttu-id="d9bdf-105">Usare la [GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9bdf-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9bdf-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9bdf-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="d9bdf-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="d9bdf-108">[in] Il percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d9bdf-109">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d9bdf-110">Usa lo zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d9bdf-111">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d9bdf-112">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d9bdf-113">[out] La dimensione restituita, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9bdf-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d9bdf-114">Requirements</span></span>  
 <span data-ttu-id="d9bdf-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9bdf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9bdf-116">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d9bdf-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d9bdf-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d9bdf-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9bdf-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9bdf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9bdf-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9bdf-119">See also</span></span>

- [<span data-ttu-id="d9bdf-120">Metodo GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="d9bdf-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="d9bdf-121">Metodo GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="d9bdf-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="d9bdf-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d9bdf-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

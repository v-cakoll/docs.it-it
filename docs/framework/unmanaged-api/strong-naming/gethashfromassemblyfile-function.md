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
ms.openlocfilehash: 026115adc01e7dcdac3012255f0378cff6348f89
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780695"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="707a0-102">Funzione GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="707a0-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="707a0-103">Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="707a0-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="707a0-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="707a0-104">This function has been deprecated.</span></span> <span data-ttu-id="707a0-105">Usare la [GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="707a0-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="707a0-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="707a0-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="707a0-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="707a0-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="707a0-108">[in] Il percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="707a0-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="707a0-109">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="707a0-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="707a0-110">Usa lo zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="707a0-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="707a0-111">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="707a0-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="707a0-112">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="707a0-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="707a0-113">[out] La dimensione restituita, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="707a0-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="707a0-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="707a0-114">Requirements</span></span>  
 <span data-ttu-id="707a0-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="707a0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="707a0-116">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="707a0-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="707a0-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="707a0-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="707a0-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="707a0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="707a0-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="707a0-119">See also</span></span>

- [<span data-ttu-id="707a0-120">Metodo GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="707a0-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="707a0-121">Metodo GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="707a0-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="707a0-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="707a0-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

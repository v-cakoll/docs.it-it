---
title: Funzione GetHashFromAssemblyFileW
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 832d66eee14680870e70f1e0e8d40987eff3257f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457574"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="bf503-102">Funzione GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="bf503-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="bf503-103">Ottiene un hash del file di assembly specificato, usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="bf503-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="bf503-104">Il percorso del file di assembly deve essere specificato come stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="bf503-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="bf503-105">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="bf503-105">This function has been deprecated.</span></span> <span data-ttu-id="bf503-106">Utilizzare il [:: GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="bf503-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf503-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf503-107">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf503-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="bf503-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="bf503-109">[in] Il percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="bf503-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="bf503-110">Questo parametro deve essere una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="bf503-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="bf503-111">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="bf503-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="bf503-112">Utilizzare zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="bf503-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="bf503-113">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="bf503-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="bf503-114">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="bf503-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="bf503-115">[out] La dimensione restituita, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="bf503-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf503-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bf503-116">Requirements</span></span>  
 <span data-ttu-id="bf503-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf503-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf503-118">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="bf503-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bf503-119">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="bf503-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf503-120">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf503-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf503-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf503-121">See Also</span></span>  
 [<span data-ttu-id="bf503-122">Metodo GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="bf503-122">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="bf503-123">Metodo GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="bf503-123">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="bf503-124">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="bf503-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

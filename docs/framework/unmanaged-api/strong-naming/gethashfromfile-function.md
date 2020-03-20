---
title: Funzione GetHashFromFile
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
ms.openlocfilehash: ea2b70f37668587fb02513ab54da6c1915e2918d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176981"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="34862-102">Funzione GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="34862-102">GetHashFromFile Function</span></span>
<span data-ttu-id="34862-103">Genera un hash basato sul contenuto del file specificato.</span><span class="sxs-lookup"><span data-stu-id="34862-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="34862-104">Questa funzione è deprecata.</span><span class="sxs-lookup"><span data-stu-id="34862-104">This function has been deprecated.</span></span> <span data-ttu-id="34862-105">Utilizzare invece il metodo [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="34862-105">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34862-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34862-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34862-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="34862-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="34862-108">[in] Nome del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="34862-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="34862-109">[in, out] Algoritmo da utilizzare durante la generazione dell'hash.</span><span class="sxs-lookup"><span data-stu-id="34862-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="34862-110">Gli algoritmi validi sono quelli definiti da Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="34862-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="34862-111">Se `piHashAlg` è impostato su 0, viene utilizzato l'algoritmo predefinito CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="34862-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="34862-112">[fuori] Matrice di byte contenente l'hash generato.</span><span class="sxs-lookup"><span data-stu-id="34862-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="34862-113">[in] Dimensione massima del buffer `pbHash` a cui punta.</span><span class="sxs-lookup"><span data-stu-id="34862-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="34862-114">[fuori] Dimensione, in byte, dell'oggetto restituito. `pbHash`</span><span class="sxs-lookup"><span data-stu-id="34862-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34862-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="34862-115">Remarks</span></span>  
 <span data-ttu-id="34862-116">Questa funzione è uguale a [GetHashFromFileW](gethashfromfilew-function.md), con la differenza che la specifica del nome file è ANSI anziché Unicode.</span><span class="sxs-lookup"><span data-stu-id="34862-116">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34862-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34862-117">Requirements</span></span>  
 <span data-ttu-id="34862-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34862-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34862-119">**Intestazione:** NomeForte.h</span><span class="sxs-lookup"><span data-stu-id="34862-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="34862-120">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="34862-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="34862-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34862-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34862-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34862-122">See also</span></span>

- [<span data-ttu-id="34862-123">Metodo GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="34862-123">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="34862-124">Metodo GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="34862-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="34862-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="34862-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

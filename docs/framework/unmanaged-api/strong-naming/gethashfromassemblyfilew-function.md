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
ms.openlocfilehash: cf7667f0f2a0f77cd793e00a5de8b030b0c53ec8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140706"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="f92b0-102">Funzione GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="f92b0-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="f92b0-103">Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="f92b0-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="f92b0-104">Il percorso del file di assembly deve essere specificato come stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="f92b0-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="f92b0-105">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="f92b0-105">This function has been deprecated.</span></span> <span data-ttu-id="f92b0-106">Usare invece il metodo [ICLRStrongName:: GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f92b0-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f92b0-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f92b0-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f92b0-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="f92b0-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="f92b0-109">in Percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="f92b0-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="f92b0-110">Questo parametro deve essere una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="f92b0-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="f92b0-111">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="f92b0-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="f92b0-112">Usare zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="f92b0-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="f92b0-113">out Buffer hash restituito.</span><span class="sxs-lookup"><span data-stu-id="f92b0-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="f92b0-114">in Dimensioni massime richieste di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f92b0-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="f92b0-115">out Dimensioni restituite, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f92b0-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f92b0-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f92b0-116">Requirements</span></span>  
 <span data-ttu-id="f92b0-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f92b0-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f92b0-118">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="f92b0-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f92b0-119">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f92b0-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f92b0-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f92b0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f92b0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f92b0-121">See also</span></span>

- [<span data-ttu-id="f92b0-122">Metodo GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="f92b0-122">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="f92b0-123">Metodo GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="f92b0-123">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="f92b0-124">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f92b0-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

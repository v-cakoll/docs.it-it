---
title: Funzione GetHashFromHandle
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3eac353252f5a97402cbd883895b3e397c39edd6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799177"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="13f30-102">Funzione GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="13f30-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="13f30-103">Genera un hash basato sul contenuto del file con l'handle di file specificato, usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="13f30-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="13f30-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="13f30-104">This function has been deprecated.</span></span> <span data-ttu-id="13f30-105">Usare invece il metodo [ICLRStrongName:: GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) .</span><span class="sxs-lookup"><span data-stu-id="13f30-105">Use the [ICLRStrongName::GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13f30-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13f30-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13f30-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="13f30-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="13f30-108">in Handle del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="13f30-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="13f30-109">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="13f30-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="13f30-110">Usare zero per l'algoritmo predefinito.</span><span class="sxs-lookup"><span data-stu-id="13f30-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="13f30-111">out Buffer hash restituito.</span><span class="sxs-lookup"><span data-stu-id="13f30-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="13f30-112">in Dimensione massima richiesta di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="13f30-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="13f30-113">out Dimensione, in byte, dell'oggetto restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="13f30-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13f30-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13f30-114">Requirements</span></span>  
 <span data-ttu-id="13f30-115">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13f30-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13f30-116">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="13f30-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="13f30-117">**Libreria** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="13f30-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13f30-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13f30-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f30-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13f30-119">See also</span></span>

- [<span data-ttu-id="13f30-120">Metodo GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="13f30-120">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="13f30-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="13f30-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

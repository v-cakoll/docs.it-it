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
ms.openlocfilehash: dc241324f5844610d7b86b7cb9668f84d4525395
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140656"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="d77cd-102">Funzione GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="d77cd-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="d77cd-103">Genera un hash basato sul contenuto del file con l'handle di file specificato, usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="d77cd-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="d77cd-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="d77cd-104">This function has been deprecated.</span></span> <span data-ttu-id="d77cd-105">Usare invece il metodo [ICLRStrongName:: GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d77cd-105">Use the [ICLRStrongName::GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d77cd-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d77cd-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d77cd-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="d77cd-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="d77cd-108">in Handle del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="d77cd-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d77cd-109">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d77cd-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d77cd-110">Usare zero per l'algoritmo predefinito.</span><span class="sxs-lookup"><span data-stu-id="d77cd-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d77cd-111">out Buffer hash restituito.</span><span class="sxs-lookup"><span data-stu-id="d77cd-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d77cd-112">in Dimensioni massime richieste di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d77cd-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d77cd-113">out Dimensione, in byte, dell'oggetto restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d77cd-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d77cd-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d77cd-114">Requirements</span></span>  
 <span data-ttu-id="d77cd-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d77cd-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d77cd-116">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="d77cd-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d77cd-117">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d77cd-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d77cd-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d77cd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d77cd-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d77cd-119">See also</span></span>

- [<span data-ttu-id="d77cd-120">Metodo GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="d77cd-120">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="d77cd-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d77cd-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

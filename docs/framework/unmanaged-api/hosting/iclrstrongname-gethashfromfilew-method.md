---
title: Metodo ICLRStrongName::GetHashFromFileW
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: 553acc178bc5805b5afef5931fefc8ad74cbac39
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135179"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="ae5bc-102">Metodo ICLRStrongName::GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="ae5bc-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="ae5bc-103">Genera un hash basato sul contenuto del file specificato da una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="ae5bc-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae5bc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae5bc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="ae5bc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ae5bc-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="ae5bc-106">in Nome Unicode del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="ae5bc-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="ae5bc-107">[in, out] Algoritmo da utilizzare durante la generazione dell'hash.</span><span class="sxs-lookup"><span data-stu-id="ae5bc-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="ae5bc-108">Gli algoritmi validi sono quelli definiti dalla CryptoAPI Win32.</span><span class="sxs-lookup"><span data-stu-id="ae5bc-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="ae5bc-109">Se `piHashAlg` è impostato su 0, viene utilizzato l'algoritmo predefinito CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="ae5bc-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="ae5bc-110">out Matrice di byte contenente l'hash generato.</span><span class="sxs-lookup"><span data-stu-id="ae5bc-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="ae5bc-111">in Dimensione massima del buffer a cui punta `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="ae5bc-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="ae5bc-112">out Dimensione, in byte, del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="ae5bc-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae5bc-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ae5bc-113">Return Value</span></span>  
 <span data-ttu-id="ae5bc-114">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="ae5bc-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae5bc-115">Note</span><span class="sxs-lookup"><span data-stu-id="ae5bc-115">Remarks</span></span>  
 <span data-ttu-id="ae5bc-116">Questo metodo è uguale al metodo [ICLRStrongName:: GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) , ad eccezione del fatto che la specifica del nome file è Unicode anziché ANSI.</span><span class="sxs-lookup"><span data-stu-id="ae5bc-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae5bc-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae5bc-117">Requirements</span></span>  
 <span data-ttu-id="ae5bc-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae5bc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae5bc-119">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="ae5bc-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ae5bc-120">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ae5bc-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae5bc-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae5bc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae5bc-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae5bc-122">See also</span></span>

- [<span data-ttu-id="ae5bc-123">Metodo GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="ae5bc-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="ae5bc-124">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="ae5bc-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

---
title: Metodo ICLRStrongName::GetHashFromFile
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
ms.openlocfilehash: e4a5f6440a016176cf06704b342c173b29748e78
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762110"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="068f0-102">Metodo ICLRStrongName::GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="068f0-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="068f0-103">Genera un hash basato sul contenuto del file specificato.</span><span class="sxs-lookup"><span data-stu-id="068f0-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="068f0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="068f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="068f0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="068f0-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="068f0-106">in Nome del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="068f0-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="068f0-107">[in, out] Algoritmo da utilizzare durante la generazione dell'hash.</span><span class="sxs-lookup"><span data-stu-id="068f0-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="068f0-108">Gli algoritmi validi sono quelli definiti dalla CryptoAPI Win32.</span><span class="sxs-lookup"><span data-stu-id="068f0-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="068f0-109">Se `piHashAlg` è impostato su 0, viene utilizzato l'algoritmo predefinito CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="068f0-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="068f0-110">out Matrice di byte contenente l'hash generato.</span><span class="sxs-lookup"><span data-stu-id="068f0-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="068f0-111">in Dimensione massima del buffer `pbHash` a cui punta.</span><span class="sxs-lookup"><span data-stu-id="068f0-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="068f0-112">out Dimensione, in byte, dell'oggetto restituito `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="068f0-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="068f0-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="068f0-113">Return Value</span></span>  
 <span data-ttu-id="068f0-114">`S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="068f0-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="068f0-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="068f0-115">Remarks</span></span>  
 <span data-ttu-id="068f0-116">Questo metodo è uguale al metodo [ICLRStrongName:: GetHashFromFileW](iclrstrongname-gethashfromfilew-method.md) , ad eccezione del fatto che la specifica del nome file è ANSI anziché Unicode.</span><span class="sxs-lookup"><span data-stu-id="068f0-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="068f0-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="068f0-117">Requirements</span></span>  
 <span data-ttu-id="068f0-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="068f0-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="068f0-119">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="068f0-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="068f0-120">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="068f0-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="068f0-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="068f0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="068f0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="068f0-122">See also</span></span>

- [<span data-ttu-id="068f0-123">Metodo GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="068f0-123">GetHashFromFileW Method</span></span>](iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="068f0-124">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="068f0-124">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

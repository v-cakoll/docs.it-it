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
ms.openlocfilehash: 6dbb3360132186c38c007fb5fa12a3724ca145aa
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762097"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="71bcd-102">Metodo ICLRStrongName::GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="71bcd-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="71bcd-103">Genera un hash basato sul contenuto del file specificato da una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="71bcd-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71bcd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71bcd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="71bcd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="71bcd-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="71bcd-106">in Nome Unicode del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="71bcd-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="71bcd-107">[in, out] Algoritmo da utilizzare durante la generazione dell'hash.</span><span class="sxs-lookup"><span data-stu-id="71bcd-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="71bcd-108">Gli algoritmi validi sono quelli definiti dalla CryptoAPI Win32.</span><span class="sxs-lookup"><span data-stu-id="71bcd-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="71bcd-109">Se `piHashAlg` è impostato su 0, viene utilizzato l'algoritmo predefinito CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="71bcd-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="71bcd-110">out Matrice di byte contenente l'hash generato.</span><span class="sxs-lookup"><span data-stu-id="71bcd-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="71bcd-111">in Dimensione massima del buffer a cui punta `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="71bcd-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="71bcd-112">out Dimensione, in byte, di `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="71bcd-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71bcd-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="71bcd-113">Return Value</span></span>  
 <span data-ttu-id="71bcd-114">`S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="71bcd-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71bcd-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="71bcd-115">Remarks</span></span>  
 <span data-ttu-id="71bcd-116">Questo metodo è uguale al metodo [ICLRStrongName:: GetHashFromFile](iclrstrongname-gethashfromfile-method.md) , ad eccezione del fatto che la specifica del nome file è Unicode anziché ANSI.</span><span class="sxs-lookup"><span data-stu-id="71bcd-116">This method is the same as the [ICLRStrongName::GetHashFromFile](iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71bcd-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71bcd-117">Requirements</span></span>  
 <span data-ttu-id="71bcd-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71bcd-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71bcd-119">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="71bcd-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="71bcd-120">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="71bcd-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71bcd-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71bcd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71bcd-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71bcd-122">See also</span></span>

- [<span data-ttu-id="71bcd-123">Metodo GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="71bcd-123">GetHashFromFile Method</span></span>](iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="71bcd-124">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="71bcd-124">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

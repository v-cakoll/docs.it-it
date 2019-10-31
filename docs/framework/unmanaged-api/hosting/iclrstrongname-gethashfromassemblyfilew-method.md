---
title: Metodo ICLRStrongName::GetHashFromAssemblyFileW
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
ms.openlocfilehash: 43a5cd57a8eeaba70f1bb1ffb9cab5bb1a067914
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130957"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="51ceb-102">Metodo ICLRStrongName::GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="51ceb-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="51ceb-103">Genera un hash basato sul contenuto del file specificato da una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="51ceb-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51ceb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51ceb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51ceb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="51ceb-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="51ceb-106">in Percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="51ceb-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="51ceb-107">Questo parametro deve essere una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="51ceb-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="51ceb-108">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="51ceb-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="51ceb-109">Usare zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="51ceb-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="51ceb-110">out Buffer hash restituito.</span><span class="sxs-lookup"><span data-stu-id="51ceb-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="51ceb-111">in Dimensioni massime richieste di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="51ceb-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="51ceb-112">out Dimensioni restituite, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="51ceb-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51ceb-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="51ceb-113">Return Value</span></span>  
 <span data-ttu-id="51ceb-114">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="51ceb-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51ceb-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51ceb-115">Requirements</span></span>  
 <span data-ttu-id="51ceb-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51ceb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51ceb-117">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="51ceb-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="51ceb-118">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="51ceb-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51ceb-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51ceb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51ceb-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51ceb-120">See also</span></span>

- [<span data-ttu-id="51ceb-121">Metodo GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="51ceb-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="51ceb-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="51ceb-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

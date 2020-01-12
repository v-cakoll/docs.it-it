---
title: Metodo ICLRStrongName::GetHashFromAssemblyFile
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
ms.openlocfilehash: 8131a9838cc958405ca23c75c702db5ec65a41c8
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901186"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="d3077-102">Metodo ICLRStrongName::GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="d3077-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="d3077-103">Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="d3077-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3077-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3077-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3077-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d3077-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="d3077-106">in Percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="d3077-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d3077-107">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d3077-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d3077-108">Usare zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="d3077-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d3077-109">out Buffer hash restituito.</span><span class="sxs-lookup"><span data-stu-id="d3077-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d3077-110">in Dimensioni massime richieste di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d3077-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d3077-111">out Dimensioni restituite, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d3077-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3077-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d3077-112">Return Value</span></span>  
 <span data-ttu-id="d3077-113">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="d3077-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3077-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="d3077-114">Requirements</span></span>  
 <span data-ttu-id="d3077-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3077-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3077-116">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="d3077-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d3077-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d3077-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3077-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3077-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3077-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3077-119">See also</span></span>

- [<span data-ttu-id="d3077-120">Metodo GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="d3077-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="d3077-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d3077-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

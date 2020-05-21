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
ms.openlocfilehash: 007de0365bf70b1f4a9a9e0f01807e7fdac19f54
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762149"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="56e92-102">Metodo ICLRStrongName::GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="56e92-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="56e92-103">Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="56e92-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56e92-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56e92-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56e92-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="56e92-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="56e92-106">in Percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="56e92-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="56e92-107">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="56e92-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="56e92-108">Usare zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="56e92-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="56e92-109">out Buffer hash restituito.</span><span class="sxs-lookup"><span data-stu-id="56e92-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="56e92-110">in Dimensione massima richiesta di `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="56e92-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="56e92-111">out Dimensione restituita, in byte, di `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="56e92-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56e92-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="56e92-112">Return Value</span></span>  
 <span data-ttu-id="56e92-113">`S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="56e92-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56e92-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56e92-114">Requirements</span></span>  
 <span data-ttu-id="56e92-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56e92-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56e92-116">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="56e92-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="56e92-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="56e92-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56e92-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56e92-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e92-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56e92-119">See also</span></span>

- [<span data-ttu-id="56e92-120">Metodo GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="56e92-120">GetHashFromAssemblyFileW Method</span></span>](iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="56e92-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="56e92-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

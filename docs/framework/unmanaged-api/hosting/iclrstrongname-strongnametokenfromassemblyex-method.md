---
title: Metodo ICLRStrongName::StrongNameTokenFromAssemblyEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type:
- apiref
ms.openlocfilehash: 71fda266c22c4beb1e1f9c81c84d6c56a0a6110e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092580"
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a><span data-ttu-id="6bd82-102">Metodo ICLRStrongName::StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="6bd82-102">ICLRStrongName::StrongNameTokenFromAssemblyEx Method</span></span>
<span data-ttu-id="6bd82-103">Crea un token con nome sicuro dal file di assembly specificato e restituisce la chiave pubblica rappresentata dal token.</span><span class="sxs-lookup"><span data-stu-id="6bd82-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bd82-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6bd82-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bd82-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6bd82-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="6bd82-106">in Percorso del file eseguibile di tipo PE per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="6bd82-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="6bd82-107">out Token del nome sicuro restituito.</span><span class="sxs-lookup"><span data-stu-id="6bd82-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="6bd82-108">out Dimensione, in byte, del token del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="6bd82-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="6bd82-109">out Chiave pubblica restituita.</span><span class="sxs-lookup"><span data-stu-id="6bd82-109">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="6bd82-110">out Dimensione, in byte, della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="6bd82-110">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6bd82-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6bd82-111">Return Value</span></span>  
 <span data-ttu-id="6bd82-112">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="6bd82-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bd82-113">Note</span><span class="sxs-lookup"><span data-stu-id="6bd82-113">Remarks</span></span>  
 <span data-ttu-id="6bd82-114">Un token di nome sicuro è il formato abbreviato di una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="6bd82-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="6bd82-115">Il token è un hash a 64 bit creato dalla chiave pubblica usata per firmare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="6bd82-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="6bd82-116">Il token fa parte del nome sicuro dell'assembly e può essere letto dai metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="6bd82-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="6bd82-117">Dopo che la chiave è stata recuperata e il token è stato creato, è necessario chiamare il metodo [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="6bd82-117">After the key is retrieved and the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bd82-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6bd82-118">Requirements</span></span>  
 <span data-ttu-id="6bd82-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bd82-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bd82-120">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="6bd82-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6bd82-121">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6bd82-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6bd82-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bd82-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bd82-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bd82-123">See also</span></span>

- [<span data-ttu-id="6bd82-124">Metodo StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="6bd82-124">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="6bd82-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="6bd82-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

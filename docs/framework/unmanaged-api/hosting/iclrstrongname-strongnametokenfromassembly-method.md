---
title: Metodo ICLRStrongName::StrongNameTokenFromAssembly
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type:
- apiref
ms.openlocfilehash: 12677799136e9ca887809e58fba838cb421ea183
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901057"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="8207e-102">Metodo ICLRStrongName::StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="8207e-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="8207e-103">Crea un token con nome sicuro dal file di assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="8207e-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8207e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8207e-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8207e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8207e-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="8207e-106">in Percorso del file eseguibile di tipo PE per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="8207e-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="8207e-107">out Token del nome sicuro restituito.</span><span class="sxs-lookup"><span data-stu-id="8207e-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="8207e-108">out Dimensione, in byte, del token del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="8207e-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8207e-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8207e-109">Return Value</span></span>  
 <span data-ttu-id="8207e-110">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="8207e-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8207e-111">Note</span><span class="sxs-lookup"><span data-stu-id="8207e-111">Remarks</span></span>  
 <span data-ttu-id="8207e-112">Un token di nome sicuro è il formato abbreviato di una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="8207e-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="8207e-113">Il token è un hash a 64 bit creato dalla chiave pubblica usata per firmare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="8207e-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="8207e-114">Il token fa parte del nome sicuro dell'assembly e può essere letto dai metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8207e-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="8207e-115">Dopo aver creato il token, è necessario chiamare il metodo [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="8207e-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8207e-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="8207e-116">Requirements</span></span>  
 <span data-ttu-id="8207e-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8207e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8207e-118">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="8207e-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8207e-119">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8207e-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8207e-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8207e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8207e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8207e-121">See also</span></span>

- [<span data-ttu-id="8207e-122">Metodo StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="8207e-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="8207e-123">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="8207e-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

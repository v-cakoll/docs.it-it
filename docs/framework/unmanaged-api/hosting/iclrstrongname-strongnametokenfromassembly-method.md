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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a2931c16e13d08c1e3e7d5b62e6583102a1b8cd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229251"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="4e131-102">Metodo ICLRStrongName::StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="4e131-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="4e131-103">Crea un token con nome sicuro dal file di assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="4e131-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e131-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e131-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e131-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4e131-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="4e131-106">[in] Il percorso del file eseguibile portabile (PE) per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="4e131-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="4e131-107">[out] Il token restituito con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="4e131-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="4e131-108">[out] Le dimensioni, in byte, del token con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="4e131-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e131-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4e131-109">Return Value</span></span>  
 <span data-ttu-id="4e131-110">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="4e131-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e131-111">Note</span><span class="sxs-lookup"><span data-stu-id="4e131-111">Remarks</span></span>  
 <span data-ttu-id="4e131-112">Un token con nome sicuro è il formato abbreviato di una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="4e131-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="4e131-113">Il token è un hash a 64 bit che viene creato dalla chiave pubblica usata per firmare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="4e131-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="4e131-114">Il token fa parte del nome sicuro dell'assembly e può essere letti dai metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4e131-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="4e131-115">Dopo aver creato il token, è necessario chiamare il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) metodo per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="4e131-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e131-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4e131-116">Requirements</span></span>  
 <span data-ttu-id="4e131-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e131-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e131-118">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="4e131-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4e131-119">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4e131-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e131-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e131-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e131-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e131-121">See also</span></span>

- [<span data-ttu-id="4e131-122">Metodo StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="4e131-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="4e131-123">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="4e131-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

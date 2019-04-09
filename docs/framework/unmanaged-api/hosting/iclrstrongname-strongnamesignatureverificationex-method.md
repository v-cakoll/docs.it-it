---
title: Metodo ICLRStrongName::StrongNameSignatureVerificationEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b36e1d34b874f47f1edb0e1ffe3dc2fe2d87ddcc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124293"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="9e576-102">Metodo ICLRStrongName::StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="9e576-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="9e576-103">Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="9e576-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e576-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e576-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e576-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9e576-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="9e576-106">[in] Il percorso del file di (.exe o DLL) eseguibile portabile per l'assembly da verificare.</span><span class="sxs-lookup"><span data-stu-id="9e576-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="9e576-107">[in] `true` per eseguire la verifica, anche se è necessario eseguire l'override delle impostazioni del Registro di sistema; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9e576-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="9e576-108">[out] `true` se la firma con nome sicuro è stato verificato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9e576-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> `pfWasVerified` <span data-ttu-id="9e576-109">viene inoltre impostata su `false` se la verifica ha avuto esito positivo a causa delle impostazioni del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="9e576-109">is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e576-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9e576-110">Return Value</span></span>  
 `S_OK` <span data-ttu-id="9e576-111">Se la verifica ha avuto esito positivo. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="9e576-111">if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e576-112">Note</span><span class="sxs-lookup"><span data-stu-id="9e576-112">Remarks</span></span>  
 <span data-ttu-id="9e576-113">Il [StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) metodo fornisce una funzionalità simile al [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="9e576-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="9e576-114">Tuttavia, il secondo parametro di input e il parametro di output per [StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) sono di tipo `BOOLEAN` invece di `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="9e576-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e576-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9e576-115">Requirements</span></span>  
 <span data-ttu-id="9e576-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e576-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e576-117">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9e576-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9e576-118">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9e576-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="9e576-119">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9e576-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9e576-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e576-120">See also</span></span>

- [<span data-ttu-id="9e576-121">Metodo StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="9e576-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="9e576-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9e576-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

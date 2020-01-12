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
ms.openlocfilehash: fbc9ea6aab9f0c3d9be95e6affcd04342ce4c5cc
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901079"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="2f875-102">Metodo ICLRStrongName::StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="2f875-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="2f875-103">Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="2f875-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f875-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f875-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f875-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2f875-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="2f875-106">in Percorso del file eseguibile (exe o dll) portatile per l'assembly da verificare.</span><span class="sxs-lookup"><span data-stu-id="2f875-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="2f875-107">[in] `true` per eseguire la verifica, anche se è necessario eseguire l'override delle impostazioni del registro di sistema; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="2f875-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="2f875-108">[out] `true` se la firma del nome sicuro è stata verificata. in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="2f875-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="2f875-109">`pfWasVerified` viene inoltre impostata su `false` se la verifica ha avuto esito positivo a causa delle impostazioni del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="2f875-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f875-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2f875-110">Return Value</span></span>  
 <span data-ttu-id="2f875-111">`S_OK` se la verifica ha avuto esito positivo; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="2f875-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f875-112">Note</span><span class="sxs-lookup"><span data-stu-id="2f875-112">Remarks</span></span>  
 <span data-ttu-id="2f875-113">Il metodo [ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) fornisce una funzionalità simile al metodo [ICLRStrongName:: StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2f875-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="2f875-114">Tuttavia, il secondo parametro di input e il parametro di output per [ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) sono di tipo `BOOLEAN` anziché `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="2f875-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f875-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="2f875-115">Requirements</span></span>  
 <span data-ttu-id="2f875-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f875-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f875-117">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="2f875-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2f875-118">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2f875-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f875-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f875-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f875-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f875-120">See also</span></span>

- [<span data-ttu-id="2f875-121">Metodo StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="2f875-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="2f875-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="2f875-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

---
title: Metodo StrongNameSignatureVerificationEx2
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb4e41f62f5f55969dadd47e80efc56e1c92c94f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768270"
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="34dc1-102">Metodo StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="34dc1-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="34dc1-103">Verifica la firma di un assembly con nome sicuro e fornisce un mapping tra la chiave ECMA e una chiave reale.</span><span class="sxs-lookup"><span data-stu-id="34dc1-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34dc1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34dc1-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34dc1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="34dc1-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="34dc1-106">[in] Il percorso del file di (.exe o DLL) eseguibile portabile per l'assembly da verificare.</span><span class="sxs-lookup"><span data-stu-id="34dc1-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="34dc1-107">[in] `true` per eseguire la verifica, anche se è necessario eseguire l'override delle impostazioni del Registro di sistema; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="34dc1-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="34dc1-108">[in] Un puntatore per il mapping dalla chiave pubblica ECMA per il tasto effettivo usato per la verifica.</span><span class="sxs-lookup"><span data-stu-id="34dc1-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="34dc1-109">[in] La lunghezza della chiave pubblica reale ECMA.</span><span class="sxs-lookup"><span data-stu-id="34dc1-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="34dc1-110">[out] `true` se la firma con nome sicuro è stato verificato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="34dc1-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="34dc1-111">Questo parametro viene impostato anche su `false` se la verifica ha avuto esito positivo a causa delle impostazioni del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="34dc1-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34dc1-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="34dc1-112">Return Value</span></span>  
 <span data-ttu-id="34dc1-113">`S_OK` Se la verifica ha avuto esito positivo. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="34dc1-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34dc1-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34dc1-114">Requirements</span></span>  
 <span data-ttu-id="34dc1-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34dc1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34dc1-116">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="34dc1-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="34dc1-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="34dc1-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34dc1-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34dc1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34dc1-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34dc1-119">See also</span></span>

- [<span data-ttu-id="34dc1-120">Metodo StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="34dc1-120">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="34dc1-121">Metodo StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="34dc1-121">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="34dc1-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="34dc1-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

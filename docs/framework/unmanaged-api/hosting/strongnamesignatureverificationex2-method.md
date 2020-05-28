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
ms.openlocfilehash: 5e6f77b9b5da061a75d23d7f3f7b673754b62afd
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006364"
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="35b06-102">Metodo StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="35b06-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="35b06-103">Verifica la firma di un assembly con nome sicuro e fornisce un mapping dalla chiave ECMA a una chiave reale.</span><span class="sxs-lookup"><span data-stu-id="35b06-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35b06-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35b06-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35b06-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="35b06-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="35b06-106">in Percorso del file eseguibile (exe o dll) portatile per l'assembly da verificare.</span><span class="sxs-lookup"><span data-stu-id="35b06-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="35b06-107">[in] `true` per eseguire la verifica, anche se è necessario eseguire l'override delle impostazioni del registro di sistema; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="35b06-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="35b06-108">in Puntatore al mapping dalla chiave pubblica ECMA alla chiave reale utilizzata per la verifica.</span><span class="sxs-lookup"><span data-stu-id="35b06-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="35b06-109">in Lunghezza della chiave pubblica ECMA reale.</span><span class="sxs-lookup"><span data-stu-id="35b06-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="35b06-110">[out] `true` Se la firma del nome sicuro è stata verificata. in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="35b06-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="35b06-111">Questo parametro viene inoltre impostato su `false` se la verifica ha avuto esito positivo a causa delle impostazioni del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="35b06-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35b06-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="35b06-112">Return Value</span></span>  
 <span data-ttu-id="35b06-113">`S_OK`Se la verifica ha avuto esito positivo; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="35b06-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35b06-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="35b06-114">Requirements</span></span>  
 <span data-ttu-id="35b06-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35b06-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35b06-116">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="35b06-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="35b06-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="35b06-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35b06-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35b06-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35b06-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35b06-119">See also</span></span>

- [<span data-ttu-id="35b06-120">Metodo StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="35b06-120">StrongNameSignatureVerification Method</span></span>](iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="35b06-121">Metodo StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="35b06-121">StrongNameSignatureVerificationEx Method</span></span>](iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="35b06-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="35b06-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

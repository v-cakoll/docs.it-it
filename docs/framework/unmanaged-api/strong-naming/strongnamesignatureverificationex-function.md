---
title: Funzione StrongNameSignatureVerificationEx
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08247c1ec5b868055e4836b3c0fb520a536374e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798925"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="cf431-102">Funzione StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="cf431-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="cf431-103">Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="cf431-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="cf431-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="cf431-104">This function has been deprecated.</span></span> <span data-ttu-id="cf431-105">Usare invece il metodo [ICLRStrongName:: StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cf431-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf431-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf431-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf431-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="cf431-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="cf431-108">in Percorso del file eseguibile (exe o dll) portatile per l'assembly da verificare.</span><span class="sxs-lookup"><span data-stu-id="cf431-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="cf431-109">in per eseguire la verifica, anche se è necessario eseguire l'override delle impostazioni del registro di sistema; in caso contrario, `false`. `true`</span><span class="sxs-lookup"><span data-stu-id="cf431-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="cf431-110">out Se la firma del nome sicuro è stata verificata; in caso contrario, `false`. `true`</span><span class="sxs-lookup"><span data-stu-id="cf431-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="cf431-111">`pfWasVerified`viene anche impostato su `false` se la verifica ha avuto esito positivo a causa delle impostazioni del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="cf431-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf431-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cf431-112">Return Value</span></span>  
 <span data-ttu-id="cf431-113">`true`Se la verifica ha avuto esito positivo; in caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="cf431-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf431-114">Note</span><span class="sxs-lookup"><span data-stu-id="cf431-114">Remarks</span></span>  
 <span data-ttu-id="cf431-115">`StrongNameSignatureVerificationEx`fornisce una funzionalità simile alla funzione [StrongNameSignatureVerification](strongnamesignatureverification-function.md) .</span><span class="sxs-lookup"><span data-stu-id="cf431-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="cf431-116">Tuttavia, il secondo parametro di input e il parametro di `StrongNameSignatureVerificationEx` output per sono `BOOLEAN` di tipo `DWORD`anziché.</span><span class="sxs-lookup"><span data-stu-id="cf431-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf431-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cf431-117">Requirements</span></span>  
 <span data-ttu-id="cf431-118">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf431-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf431-119">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="cf431-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="cf431-120">**Libreria** Incluso come risorsa in mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="cf431-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="cf431-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf431-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf431-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf431-122">See also</span></span>

- [<span data-ttu-id="cf431-123">Metodo StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="cf431-123">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="cf431-124">Metodo StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="cf431-124">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="cf431-125">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="cf431-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

---
title: Metodo ICLRStrongName::StrongNameCompareAssemblies
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
ms.openlocfilehash: 0087636c68d0748ad2b143de9b132278ab9d43f5
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762058"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="9d569-102">Metodo ICLRStrongName::StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="9d569-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="9d569-103">Determina se due assembly differiscono solo per le firme con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="9d569-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d569-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d569-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d569-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9d569-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="9d569-106">in Percorso del primo assembly.</span><span class="sxs-lookup"><span data-stu-id="9d569-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="9d569-107">in Percorso del secondo assembly.</span><span class="sxs-lookup"><span data-stu-id="9d569-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="9d569-108">out Uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d569-108">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="9d569-109">`SN_CMP_DIFFERENT`(0): specifica che gli assembly contengono dati diversi.</span><span class="sxs-lookup"><span data-stu-id="9d569-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="9d569-110">`SN_CMP_IDENTICAL`(1): specifica che gli assembly sono esattamente uguali, incluse le relative firme e checksum.</span><span class="sxs-lookup"><span data-stu-id="9d569-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="9d569-111">`SN_CMP_SIGONLY`(2): specifica che gli assembly differiscono solo per firma e checksum.</span><span class="sxs-lookup"><span data-stu-id="9d569-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d569-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9d569-112">Return Value</span></span>  
 <span data-ttu-id="9d569-113">`S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="9d569-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d569-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9d569-114">Requirements</span></span>  
 <span data-ttu-id="9d569-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d569-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d569-116">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="9d569-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9d569-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9d569-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d569-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d569-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d569-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9d569-119">Remarks</span></span>  
 <span data-ttu-id="9d569-120">La firma con nome sicuro di un assembly è costituita dal nome del testo, dalla versione, dalle impostazioni cultura e dal token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9d569-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d569-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d569-121">See also</span></span>

- [<span data-ttu-id="9d569-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9d569-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

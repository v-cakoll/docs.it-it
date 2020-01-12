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
ms.openlocfilehash: 16b51393c945061efb0e94e48e5388c60472ee11
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899749"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="3d3f0-102">Metodo ICLRStrongName::StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="3d3f0-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="3d3f0-103">Determina se due assembly differiscono solo per le firme con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="3d3f0-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d3f0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d3f0-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d3f0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d3f0-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="3d3f0-106">in Percorso del primo assembly.</span><span class="sxs-lookup"><span data-stu-id="3d3f0-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="3d3f0-107">in Percorso del secondo assembly.</span><span class="sxs-lookup"><span data-stu-id="3d3f0-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="3d3f0-108">out Uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d3f0-108">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="3d3f0-109">`SN_CMP_DIFFERENT` (0): specifica che gli assembly contengono dati diversi.</span><span class="sxs-lookup"><span data-stu-id="3d3f0-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="3d3f0-110">`SN_CMP_IDENTICAL` (1): specifica che gli assembly sono esattamente uguali, incluse le relative firme e checksum.</span><span class="sxs-lookup"><span data-stu-id="3d3f0-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="3d3f0-111">`SN_CMP_SIGONLY` (2): specifica che gli assembly differiscono solo per la firma e il checksum.</span><span class="sxs-lookup"><span data-stu-id="3d3f0-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d3f0-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3d3f0-112">Return Value</span></span>  
 <span data-ttu-id="3d3f0-113">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="3d3f0-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d3f0-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3d3f0-114">Requirements</span></span>  
 <span data-ttu-id="3d3f0-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d3f0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d3f0-116">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="3d3f0-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3d3f0-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3d3f0-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d3f0-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d3f0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d3f0-119">Note</span><span class="sxs-lookup"><span data-stu-id="3d3f0-119">Remarks</span></span>  
 <span data-ttu-id="3d3f0-120">La firma con nome sicuro di un assembly è costituita dal nome del testo, dalla versione, dalle impostazioni cultura e dal token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3d3f0-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d3f0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d3f0-121">See also</span></span>

- [<span data-ttu-id="3d3f0-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="3d3f0-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

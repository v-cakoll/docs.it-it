---
title: Metodo ICLRStrongName::StrongNameGetBlob
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type:
- apiref
ms.openlocfilehash: f93d3f0322de89b2e9ce596329c06b58db9fdcdc
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760303"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="29de2-102">Metodo ICLRStrongName::StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="29de2-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="29de2-103">Completa il buffer specificato con la rappresentazione binaria del file eseguibile presente all'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="29de2-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29de2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29de2-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29de2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="29de2-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="29de2-106">in Percorso valido del file eseguibile da caricare.</span><span class="sxs-lookup"><span data-stu-id="29de2-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="29de2-107">in Buffer in cui caricare il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="29de2-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="29de2-108">[in, out] Dimensione massima richiesta, in byte, di `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="29de2-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="29de2-109">Al ritorno, le dimensioni effettive, in byte, di `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="29de2-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29de2-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="29de2-110">Return Value</span></span>  
 <span data-ttu-id="29de2-111">`S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="29de2-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29de2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="29de2-112">Requirements</span></span>  
 <span data-ttu-id="29de2-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29de2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29de2-114">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="29de2-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="29de2-115">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="29de2-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29de2-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29de2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29de2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29de2-117">See also</span></span>

- [<span data-ttu-id="29de2-118">Metodo StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="29de2-118">StrongNameGetBlobFromImage Method</span></span>](iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="29de2-119">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="29de2-119">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

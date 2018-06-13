---
title: Metodo ICorPublishAppDomain::GetName
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 796f8ea42cc5cbe13729f7b92e15bc214d62734d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423858"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="60f53-102">Metodo ICorPublishAppDomain::GetName</span><span class="sxs-lookup"><span data-stu-id="60f53-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="60f53-103">Ottiene il nome del dominio dell'applicazione che è rappresentato da questo [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="60f53-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60f53-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60f53-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="60f53-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="60f53-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="60f53-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="60f53-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="60f53-107">[out] Un puntatore al numero di caratteri wide, incluso il carattere null, restituito nella `szName` matrice.</span><span class="sxs-lookup"><span data-stu-id="60f53-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="60f53-108">[out] Matrice in cui archiviare il nome.</span><span class="sxs-lookup"><span data-stu-id="60f53-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60f53-109">Note</span><span class="sxs-lookup"><span data-stu-id="60f53-109">Remarks</span></span>  
 <span data-ttu-id="60f53-110">Se `szName` è diverso da null, il `GetName` metodo copia fino a `cchName` caratteri (incluso il carattere di terminazione null) in `szName`.</span><span class="sxs-lookup"><span data-stu-id="60f53-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="60f53-111">Se viene restituito un valore non null in `pcchName`, in cui viene archiviato il numero effettivo di caratteri del nome (incluso il carattere di terminazione null) il `szName` matrice.</span><span class="sxs-lookup"><span data-stu-id="60f53-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="60f53-112">Il `GetName` metodo restituisce un HRESULT S_OK indipendentemente dal numero di caratteri copiato.</span><span class="sxs-lookup"><span data-stu-id="60f53-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60f53-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="60f53-113">Requirements</span></span>  
 <span data-ttu-id="60f53-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60f53-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60f53-115">**Intestazione:** Corpub. idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="60f53-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="60f53-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="60f53-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60f53-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60f53-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f53-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60f53-118">See Also</span></span>  
 [<span data-ttu-id="60f53-119">Interfaccia ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="60f53-119">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)

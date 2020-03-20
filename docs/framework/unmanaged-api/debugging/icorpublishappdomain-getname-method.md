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
ms.openlocfilehash: 762c637696fdf79ccab6702918b5bf962ea55903
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178413"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="8e94c-102">Metodo ICorPublishAppDomain::GetName</span><span class="sxs-lookup"><span data-stu-id="8e94c-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="8e94c-103">Ottiene il nome del dominio applicazione rappresentato da [questo ICorPublishAppDomain.](icorpublishappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="8e94c-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e94c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e94c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e94c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8e94c-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="8e94c-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="8e94c-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="8e94c-107">[fuori] Puntatore al numero di caratteri di tipo "wide", incluso il carattere null, restituito nella `szName` matrice.</span><span class="sxs-lookup"><span data-stu-id="8e94c-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="8e94c-108">[fuori] Matrice in cui archiviare il nome.</span><span class="sxs-lookup"><span data-stu-id="8e94c-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e94c-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8e94c-109">Remarks</span></span>  
 <span data-ttu-id="8e94c-110">Se `szName` non è null, il `GetName` metodo `cchName` copia fino ai caratteri `szName`(incluso il carattere di terminazione null) in .</span><span class="sxs-lookup"><span data-stu-id="8e94c-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="8e94c-111">Se viene restituito un valore `pcchName`diverso da null in , il numero effettivo di caratteri `szName` nel nome (incluso il carattere di terminazione null) viene archiviato nella matrice.</span><span class="sxs-lookup"><span data-stu-id="8e94c-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="8e94c-112">Il `GetName` metodo restituisce un S_OK HRESULT indipendentemente dal numero di caratteri copiati.</span><span class="sxs-lookup"><span data-stu-id="8e94c-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e94c-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e94c-113">Requirements</span></span>  
 <span data-ttu-id="8e94c-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e94c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e94c-115">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="8e94c-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="8e94c-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e94c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e94c-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e94c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e94c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e94c-118">See also</span></span>

- [<span data-ttu-id="8e94c-119">Interfaccia ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="8e94c-119">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)

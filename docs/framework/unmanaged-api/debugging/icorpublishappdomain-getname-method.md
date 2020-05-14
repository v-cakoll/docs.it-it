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
ms.openlocfilehash: e95f96847c6e069758362fb6febc28dc31911bc9
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396289"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="5c97d-102">Metodo ICorPublishAppDomain::GetName</span><span class="sxs-lookup"><span data-stu-id="5c97d-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="5c97d-103">Ottiene il nome del dominio dell'applicazione rappresentato da questo [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5c97d-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c97d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c97d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c97d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c97d-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="5c97d-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="5c97d-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5c97d-107">out Puntatore al numero di caratteri wide, incluso il carattere null, restituito nella `szName` matrice.</span><span class="sxs-lookup"><span data-stu-id="5c97d-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="5c97d-108">out Matrice in cui archiviare il nome.</span><span class="sxs-lookup"><span data-stu-id="5c97d-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c97d-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="5c97d-109">Remarks</span></span>  
 <span data-ttu-id="5c97d-110">Se `szName` è diverso da null, il `GetName` metodo copia fino a `cchName` caratteri (incluso il terminatore null) in `szName` .</span><span class="sxs-lookup"><span data-stu-id="5c97d-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="5c97d-111">Se viene restituito un valore non null in `pcchName` , il numero effettivo di caratteri nel nome, incluso il terminatore null, viene archiviato nella `szName` matrice.</span><span class="sxs-lookup"><span data-stu-id="5c97d-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="5c97d-112">Il `GetName` metodo restituisce un S_OK HRESULT indipendentemente dal numero di caratteri copiati.</span><span class="sxs-lookup"><span data-stu-id="5c97d-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c97d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c97d-113">Requirements</span></span>  
 <span data-ttu-id="5c97d-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c97d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c97d-115">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="5c97d-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5c97d-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c97d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c97d-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c97d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c97d-118">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="5c97d-118">See also</span></span>

- [<span data-ttu-id="5c97d-119">Interfaccia ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="5c97d-119">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)

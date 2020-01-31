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
ms.openlocfilehash: 4325d61d12a66b17f88e5e368cbbc7806d0a3ec5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790711"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="8b836-102">Metodo ICorPublishAppDomain::GetName</span><span class="sxs-lookup"><span data-stu-id="8b836-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="8b836-103">Ottiene il nome del dominio dell'applicazione rappresentato da questo [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="8b836-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b836-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b836-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b836-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8b836-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="8b836-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="8b836-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="8b836-107">out Puntatore al numero di caratteri wide, incluso il carattere null, restituito nella matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="8b836-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="8b836-108">out Matrice in cui archiviare il nome.</span><span class="sxs-lookup"><span data-stu-id="8b836-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b836-109">Note</span><span class="sxs-lookup"><span data-stu-id="8b836-109">Remarks</span></span>  
 <span data-ttu-id="8b836-110">Se `szName` è diverso da null, il metodo `GetName` copia fino a `cchName` caratteri, incluso il terminatore null, in `szName`.</span><span class="sxs-lookup"><span data-stu-id="8b836-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="8b836-111">Se viene restituito un valore non null in `pcchName`, il numero effettivo di caratteri nel nome, incluso il terminatore null, viene archiviato nella matrice di `szName`.</span><span class="sxs-lookup"><span data-stu-id="8b836-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="8b836-112">Il metodo `GetName` restituisce una S_OK HRESULT indipendentemente dal numero di caratteri copiati.</span><span class="sxs-lookup"><span data-stu-id="8b836-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b836-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="8b836-113">Requirements</span></span>  
 <span data-ttu-id="8b836-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b836-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b836-115">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="8b836-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="8b836-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b836-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b836-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b836-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b836-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b836-118">See also</span></span>

- [<span data-ttu-id="8b836-119">Interfaccia ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="8b836-119">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)

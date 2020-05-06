---
title: Funzione _EFN_GetManagedObjectFieldInfo
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
ms.openlocfilehash: 42f7020212dd2db793b7c7d20a15c129157e7261
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860761"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a><span data-ttu-id="f7029-102">\_AAPN\_GetManagedObjectFieldInfo-funzione</span><span class="sxs-lookup"><span data-stu-id="f7029-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="f7029-103">Ottiene l'offset per un campo dall'inizio di un oggetto e il valore del campo, usando il puntatore all'oggetto e il nome di campo forniti.</span><span class="sxs-lookup"><span data-stu-id="f7029-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7029-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7029-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7029-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f7029-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="f7029-106">in Puntatore al client di debug.</span><span class="sxs-lookup"><span data-stu-id="f7029-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="f7029-107">in Puntatore A un oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="f7029-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="f7029-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="f7029-108">szFieldName</span></span>  
 <span data-ttu-id="f7029-109">in Puntatore a un oggetto gestito al nome del campo.</span><span class="sxs-lookup"><span data-stu-id="f7029-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="f7029-110">out Valore del campo.</span><span class="sxs-lookup"><span data-stu-id="f7029-110">[out] The field value.</span></span> <span data-ttu-id="f7029-111">Questo parametro può essere null.</span><span class="sxs-lookup"><span data-stu-id="f7029-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="f7029-112">out Offset da `objAddr` al campo.</span><span class="sxs-lookup"><span data-stu-id="f7029-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="f7029-113">Questo parametro può essere null.</span><span class="sxs-lookup"><span data-stu-id="f7029-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7029-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f7029-114">Remarks</span></span>  
 <span data-ttu-id="f7029-115">Se l'offset è 0, non viene scritto alcun offset.</span><span class="sxs-lookup"><span data-stu-id="f7029-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="f7029-116">Se nel thread non è attualmente presente codice gestito, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con un valore della funzione messaggi 0XA0 e un codice di errore 0x1000.</span><span class="sxs-lookup"><span data-stu-id="f7029-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7029-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7029-117">Requirements</span></span>  
 <span data-ttu-id="f7029-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7029-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7029-119">**Intestazione:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="f7029-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="f7029-120">**Versione .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7029-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7029-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7029-121">See also</span></span>

- [<span data-ttu-id="f7029-122">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="f7029-122">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)

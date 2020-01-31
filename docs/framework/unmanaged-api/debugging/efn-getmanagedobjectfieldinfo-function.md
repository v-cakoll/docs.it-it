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
ms.openlocfilehash: 182424632e4f81dfdf86e87dc6bb2c75c2780fce
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793766"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a><span data-ttu-id="46b01-102">\_AAPN\_funzione GetManagedObjectFieldInfo</span><span class="sxs-lookup"><span data-stu-id="46b01-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="46b01-103">Ottiene l'offset per un campo dall'inizio di un oggetto e il valore del campo, usando il puntatore all'oggetto e il nome di campo forniti.</span><span class="sxs-lookup"><span data-stu-id="46b01-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46b01-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46b01-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46b01-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="46b01-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="46b01-106">in Puntatore al client di debug.</span><span class="sxs-lookup"><span data-stu-id="46b01-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="46b01-107">in Puntatore A un oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="46b01-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="46b01-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="46b01-108">szFieldName</span></span>  
 <span data-ttu-id="46b01-109">in Puntatore a un oggetto gestito al nome del campo.</span><span class="sxs-lookup"><span data-stu-id="46b01-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="46b01-110">out Valore del campo.</span><span class="sxs-lookup"><span data-stu-id="46b01-110">[out] The field value.</span></span> <span data-ttu-id="46b01-111">Questo parametro può essere null.</span><span class="sxs-lookup"><span data-stu-id="46b01-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="46b01-112">out Offset da `objAddr` al campo.</span><span class="sxs-lookup"><span data-stu-id="46b01-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="46b01-113">Questo parametro può essere null.</span><span class="sxs-lookup"><span data-stu-id="46b01-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46b01-114">Note</span><span class="sxs-lookup"><span data-stu-id="46b01-114">Remarks</span></span>  
 <span data-ttu-id="46b01-115">Se l'offset è 0, non viene scritto alcun offset.</span><span class="sxs-lookup"><span data-stu-id="46b01-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="46b01-116">Se nel thread non è attualmente presente codice gestito, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con un valore della funzione messaggi 0XA0 e un codice di errore 0x1000.</span><span class="sxs-lookup"><span data-stu-id="46b01-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46b01-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="46b01-117">Requirements</span></span>  
 <span data-ttu-id="46b01-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46b01-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46b01-119">**Intestazione:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="46b01-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="46b01-120">**Versione .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46b01-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b01-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46b01-121">See also</span></span>

- [<span data-ttu-id="46b01-122">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="46b01-122">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)

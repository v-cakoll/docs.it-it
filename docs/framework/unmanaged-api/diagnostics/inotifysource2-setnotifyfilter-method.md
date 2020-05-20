---
title: Metodo INotifySource2::SetNotifyFilter
ms.date: 03/30/2017
api_name:
- INotifySource2.SetNotifyFilter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type:
- apiref
ms.openlocfilehash: 7ba9f68e102696da107b5cb782c76cb55ed95ee6
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441968"
---
# <a name="inotifysource2setnotifyfilter-method"></a><span data-ttu-id="5a9ed-102">Metodo INotifySource2::SetNotifyFilter</span><span class="sxs-lookup"><span data-stu-id="5a9ed-102">INotifySource2::SetNotifyFilter Method</span></span>
<span data-ttu-id="5a9ed-103">Assegna un filtro di notifica per l'utilizzo con questa origine.</span><span class="sxs-lookup"><span data-stu-id="5a9ed-103">Assigns a notification filter for use with this source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a9ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a9ed-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a9ed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a9ed-105">Parameters</span></span>  
 `in_NotifyFilter`  
 <span data-ttu-id="5a9ed-106">in Combinazione bit per bit dei valori di enumerazione [NOTIFY_FILTER](notify-filter-enumeration.md) che identificano i callback per l'API del debugger.</span><span class="sxs-lookup"><span data-stu-id="5a9ed-106">[in] A bitwise combination of the [NOTIFY_FILTER](notify-filter-enumeration.md) enumeration values that identify callbacks for the debugger API.</span></span>  
  
 `in_pUserThreadFilter`  
 <span data-ttu-id="5a9ed-107">in Puntatore a una struttura [USER_THREAD](user-thread-structure.md) che identifica i thread per l'API del debugger.</span><span class="sxs-lookup"><span data-stu-id="5a9ed-107">[in] A pointer to a [USER_THREAD](user-thread-structure.md) structure that identifies threads for the debugger API.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a9ed-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5a9ed-108">Return Value</span></span>  
 <span data-ttu-id="5a9ed-109">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5a9ed-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a9ed-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a9ed-110">Requirements</span></span>  
 <span data-ttu-id="5a9ed-111">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="5a9ed-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a9ed-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a9ed-112">See also</span></span>

- [<span data-ttu-id="5a9ed-113">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="5a9ed-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="5a9ed-114">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="5a9ed-114">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="5a9ed-115">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="5a9ed-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)

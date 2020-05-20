---
title: Metodo INotifyConnection2::UnregisterNotifySource
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
ms.openlocfilehash: 9d0fcdcd4fe1561f7565586e3327c6d3d7e0fe0a
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442046"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="45e98-102">Metodo INotifyConnection2::UnregisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="45e98-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="45e98-103">Rimuove un oggetto origine notifica specificato dalla connessione.</span><span class="sxs-lookup"><span data-stu-id="45e98-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45e98-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45e98-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45e98-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="45e98-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="45e98-106">in Oggetto notifica di cui annullare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="45e98-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45e98-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="45e98-107">Return Value</span></span>  
 <span data-ttu-id="45e98-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="45e98-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45e98-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45e98-109">Requirements</span></span>  
 <span data-ttu-id="45e98-110">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="45e98-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e98-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45e98-111">See also</span></span>

- [<span data-ttu-id="45e98-112">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="45e98-112">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="45e98-113">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="45e98-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="45e98-114">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="45e98-114">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="45e98-115">Metodo RegisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="45e98-115">RegisterNotifySource Method</span></span>](inotifyconnection2-registernotifysource-method.md)

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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 742be1467d2f1e6eb7d8567ddf85f8e65ea4b8d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229459"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="6e4cd-102">Metodo INotifyConnection2::UnregisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="6e4cd-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="6e4cd-103">Rimuove un oggetto di origine di notifica specificato dalla connessione.</span><span class="sxs-lookup"><span data-stu-id="6e4cd-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e4cd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e4cd-104">Syntax</span></span>  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e4cd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6e4cd-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="6e4cd-106">[in] Oggetto di notifica di cui annullare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="6e4cd-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e4cd-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6e4cd-107">Return Value</span></span>  
 <span data-ttu-id="6e4cd-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="6e4cd-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e4cd-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6e4cd-109">Requirements</span></span>  
 <span data-ttu-id="6e4cd-110">**Intestazione:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="6e4cd-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e4cd-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e4cd-111">See also</span></span>

- [<span data-ttu-id="6e4cd-112">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="6e4cd-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="6e4cd-113">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="6e4cd-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="6e4cd-114">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="6e4cd-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="6e4cd-115">Metodo RegisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="6e4cd-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)

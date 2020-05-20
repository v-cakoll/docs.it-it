---
title: Metodo INotifyConnection2::RegisterNotifySource
ms.date: 03/30/2017
api_name:
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
ms.openlocfilehash: b7fa777466e2c7edd7b3110dd91e776785c63c58
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442072"
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="6ab51-102">Metodo INotifyConnection2::RegisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="6ab51-102">INotifyConnection2::RegisterNotifySource Method</span></span>
<span data-ttu-id="6ab51-103">Installa un'origine di notifica specificata.</span><span class="sxs-lookup"><span data-stu-id="6ab51-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ab51-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ab51-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ab51-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6ab51-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="6ab51-106">in Specifica l'oggetto da utilizzare come origine della notifica.</span><span class="sxs-lookup"><span data-stu-id="6ab51-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="6ab51-107">out Riceve l'oggetto da utilizzare come sink di notifica.</span><span class="sxs-lookup"><span data-stu-id="6ab51-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ab51-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6ab51-108">Return Value</span></span>  
 <span data-ttu-id="6ab51-109">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="6ab51-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ab51-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ab51-110">Requirements</span></span>  
 <span data-ttu-id="6ab51-111">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="6ab51-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ab51-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ab51-112">See also</span></span>

- [<span data-ttu-id="6ab51-113">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="6ab51-113">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="6ab51-114">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="6ab51-114">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="6ab51-115">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="6ab51-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="6ab51-116">Metodo UnregisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="6ab51-116">UnregisterNotifySource Method</span></span>](inotifyconnection2-unregisternotifysource-method.md)

---
title: Metodo IGCThreadControl::ThreadIsBlockingForSuspension
ms.date: 03/30/2017
api_name:
- IGCThreadControl.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type:
- apiref
ms.openlocfilehash: b5f6d7d40274972438a01313bc6aaec475b8e0c6
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805082"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="53111-102">Metodo IGCThreadControl::ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="53111-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="53111-103">Notifica all'host che il thread che sta effettuando la chiamata sta per essere bloccato, ad esempio per un Garbage Collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="53111-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53111-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53111-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="53111-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="53111-105">Remarks</span></span>  
 <span data-ttu-id="53111-106">L'host può scegliere all'interno del `ThreadIsBlockingForSuspension` callback se ripianificare un thread.</span><span class="sxs-lookup"><span data-stu-id="53111-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53111-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="53111-107">Requirements</span></span>  
 <span data-ttu-id="53111-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53111-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53111-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="53111-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53111-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="53111-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53111-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53111-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53111-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53111-112">See also</span></span>

- [<span data-ttu-id="53111-113">Interfaccia IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="53111-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)

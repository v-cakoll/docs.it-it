---
title: Metodo IDebuggerInfo::IsDebuggerAttached
ms.date: 03/30/2017
api_name:
- IDebuggerInfo.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type:
- apiref
ms.openlocfilehash: 95b7a2f6d35104c3353853549dacc783355feb5b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805339"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="3be58-102">Metodo IDebuggerInfo::IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="3be58-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="3be58-103">Ottiene un valore che indica se un debugger gestito è associato a questo processo.</span><span class="sxs-lookup"><span data-stu-id="3be58-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3be58-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3be58-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3be58-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3be58-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="3be58-106">out Puntatore a un valore che è `true` se un debugger gestito è associato al processo; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="3be58-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3be58-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3be58-107">Requirements</span></span>  
 <span data-ttu-id="3be58-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3be58-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3be58-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3be58-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3be58-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3be58-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3be58-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3be58-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be58-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3be58-112">See also</span></span>

- [<span data-ttu-id="3be58-113">Interfaccia IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="3be58-113">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)

---
title: Funzione ProcessUnhandledException (riferimenti alle API non gestita di WPF)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ProcessUnhandledException
api_location: PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bc43b42c2e671e13076ba87ce72e054bd65d107
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="ce247-102">Funzione ProcessUnhandledException (riferimenti alle API non gestita di WPF)</span><span class="sxs-lookup"><span data-stu-id="ce247-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="ce247-103">Questa API supporta l'infrastruttura di Windows Presentation Foundation (WPF) e non deve essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="ce247-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="ce247-104">Utilizzata dall'infrastruttura di Windows Presentation Foundation (WPF) per la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="ce247-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce247-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce247-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce247-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce247-106">Parameters</span></span>  
 <span data-ttu-id="ce247-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="ce247-107">errorMsg</span></span>  
 <span data-ttu-id="ce247-108">Messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="ce247-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce247-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce247-109">Requirements</span></span>  
 <span data-ttu-id="ce247-110">**Piattaforme:** vedere [requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce247-110">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce247-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="ce247-111">**DLL:**</span></span>  
  
 <span data-ttu-id="ce247-112">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="ce247-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="ce247-113">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="ce247-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="ce247-114">**Versione di .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce247-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce247-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce247-115">See Also</span></span>  
 [<span data-ttu-id="ce247-116">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="ce247-116">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)

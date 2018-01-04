---
title: Funzione ForwardTranslateAccelerator (riferimenti alle API non gestita di WPF)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ForwardTranslateAccelerator
api_location: PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cca9c78eaf13e04d22fce9f61ce4a7ab9ee09769
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="25f19-102">Funzione ForwardTranslateAccelerator (riferimenti alle API non gestita di WPF)</span><span class="sxs-lookup"><span data-stu-id="25f19-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="25f19-103">Questa API supporta l'infrastruttura di Windows Presentation Foundation (WPF) e non deve essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="25f19-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="25f19-104">Utilizzata dall'infrastruttura di Windows Presentation Foundation (WPF) per la gestione di windows.</span><span class="sxs-lookup"><span data-stu-id="25f19-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25f19-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25f19-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25f19-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="25f19-106">Parameters</span></span>  
 <span data-ttu-id="25f19-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="25f19-107">pMsg</span></span>  
 <span data-ttu-id="25f19-108">Un puntatore a un messaggio.</span><span class="sxs-lookup"><span data-stu-id="25f19-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="25f19-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="25f19-109">appUnhandled</span></span>  
 <span data-ttu-id="25f19-110">`true`Quando l'app è già stato fornito l'opportunità di gestire il messaggio di input, ma non è gestito. in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="25f19-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25f19-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25f19-111">Requirements</span></span>  
 <span data-ttu-id="25f19-112">**Piattaforme:** vedere [requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25f19-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25f19-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="25f19-113">**DLL:**</span></span>  
  
 <span data-ttu-id="25f19-114">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="25f19-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="25f19-115">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="25f19-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="25f19-116">**Versione di .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25f19-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25f19-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25f19-117">See Also</span></span>  
 [<span data-ttu-id="25f19-118">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="25f19-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)

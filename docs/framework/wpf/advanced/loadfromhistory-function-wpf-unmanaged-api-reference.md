---
title: Funzione LoadFromHistory (riferimenti alle API non gestita di WPF)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: LoadFromHistory
api_location: PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cdb68700ab0c11bbd6b09b83a826dc5ca4faa086
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="fafb0-102">Funzione LoadFromHistory (riferimenti alle API non gestita di WPF)</span><span class="sxs-lookup"><span data-stu-id="fafb0-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="fafb0-103">Questa API supporta l'infrastruttura di Windows Presentation Foundation (WPF) e non deve essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="fafb0-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="fafb0-104">Utilizzata dall'infrastruttura di Windows Presentation Foundation (WPF) per la gestione di windows.</span><span class="sxs-lookup"><span data-stu-id="fafb0-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fafb0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fafb0-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fafb0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="fafb0-106">Parameters</span></span>  
 <span data-ttu-id="fafb0-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="fafb0-107">pHistoryStream</span></span>  
 <span data-ttu-id="fafb0-108">Puntatore a un flusso di informazioni di cronologia.</span><span class="sxs-lookup"><span data-stu-id="fafb0-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="fafb0-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="fafb0-109">pBindCtx</span></span>  
 <span data-ttu-id="fafb0-110">Puntatore a un contesto di associazione.</span><span class="sxs-lookup"><span data-stu-id="fafb0-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fafb0-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fafb0-111">Requirements</span></span>  
 <span data-ttu-id="fafb0-112">**Piattaforme:** vedere [requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fafb0-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fafb0-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="fafb0-113">**DLL:**</span></span>  
  
 <span data-ttu-id="fafb0-114">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="fafb0-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="fafb0-115">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="fafb0-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="fafb0-116">**Versione di .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fafb0-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fafb0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fafb0-117">See Also</span></span>  
 [<span data-ttu-id="fafb0-118">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="fafb0-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)

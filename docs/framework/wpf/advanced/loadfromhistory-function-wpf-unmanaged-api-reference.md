---
title: Funzione LoadFromHistory - Riferimento all'API non gestita WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: be9b8658614e678b4370044a753554859d230fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141575"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="818f3-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span><span class="sxs-lookup"><span data-stu-id="818f3-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="818f3-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere utilizzata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="818f3-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="818f3-104">Utilizzato dall'infrastruttura di Windows Presentation Foundation (WPF) per la gestione delle finestre.</span><span class="sxs-lookup"><span data-stu-id="818f3-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="818f3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="818f3-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="818f3-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="818f3-106">Parameters</span></span>  
 <span data-ttu-id="818f3-107">pHistoryStream (corso)</span><span class="sxs-lookup"><span data-stu-id="818f3-107">pHistoryStream</span></span>  
 <span data-ttu-id="818f3-108">Puntatore a un flusso di informazioni sulla cronologia.</span><span class="sxs-lookup"><span data-stu-id="818f3-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="818f3-109">pBindCtx (informazioni in stato in questo stato indetto in</span><span class="sxs-lookup"><span data-stu-id="818f3-109">pBindCtx</span></span>  
 <span data-ttu-id="818f3-110">Puntatore a un contesto di associazione.</span><span class="sxs-lookup"><span data-stu-id="818f3-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="818f3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="818f3-111">Requirements</span></span>  
 <span data-ttu-id="818f3-112">**Piattaforme:** Vedere Requisiti di sistema [di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="818f3-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="818f3-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="818f3-113">**DLL:**</span></span>  
  
 <span data-ttu-id="818f3-114">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="818f3-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="818f3-115">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="818f3-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="818f3-116">**Versione di .NET Framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="818f3-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="818f3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="818f3-117">See also</span></span>

- [<span data-ttu-id="818f3-118">Riferimenti alle API non gestite WPF</span><span class="sxs-lookup"><span data-stu-id="818f3-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)

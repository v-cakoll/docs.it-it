---
title: Funzione LoadFromHistory (riferimenti alle API WPF non gestite)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: a4480d54390aea2771e2939b0a0825f6c49c3564
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084967"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="d662f-102">Funzione LoadFromHistory (riferimenti alle API WPF non gestite)</span><span class="sxs-lookup"><span data-stu-id="d662f-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="d662f-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="d662f-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="d662f-104">Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di windows.</span><span class="sxs-lookup"><span data-stu-id="d662f-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d662f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d662f-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="d662f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d662f-106">Parameters</span></span>  
 <span data-ttu-id="d662f-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="d662f-107">pHistoryStream</span></span>  
 <span data-ttu-id="d662f-108">Puntatore a un flusso di informazioni di cronologia.</span><span class="sxs-lookup"><span data-stu-id="d662f-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="d662f-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="d662f-109">pBindCtx</span></span>  
 <span data-ttu-id="d662f-110">Puntatore a un contesto di associazione.</span><span class="sxs-lookup"><span data-stu-id="d662f-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d662f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d662f-111">Requirements</span></span>  
 <span data-ttu-id="d662f-112">**Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d662f-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 **<span data-ttu-id="d662f-113">DLL:</span><span class="sxs-lookup"><span data-stu-id="d662f-113">DLL:</span></span>**  
  
 <span data-ttu-id="d662f-114">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="d662f-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="d662f-115">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="d662f-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 **<span data-ttu-id="d662f-116">Versione di .NET framework:</span><span class="sxs-lookup"><span data-stu-id="d662f-116">.NET Framework Version:</span></span>** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d662f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d662f-117">See also</span></span>

- [<span data-ttu-id="d662f-118">Riferimenti alle API non gestite WPF</span><span class="sxs-lookup"><span data-stu-id="d662f-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)

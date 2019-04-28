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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766132"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="154c8-102">Funzione LoadFromHistory (riferimenti alle API WPF non gestite)</span><span class="sxs-lookup"><span data-stu-id="154c8-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="154c8-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="154c8-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="154c8-104">Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di windows.</span><span class="sxs-lookup"><span data-stu-id="154c8-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="154c8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="154c8-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="154c8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="154c8-106">Parameters</span></span>  
 <span data-ttu-id="154c8-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="154c8-107">pHistoryStream</span></span>  
 <span data-ttu-id="154c8-108">Puntatore a un flusso di informazioni di cronologia.</span><span class="sxs-lookup"><span data-stu-id="154c8-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="154c8-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="154c8-109">pBindCtx</span></span>  
 <span data-ttu-id="154c8-110">Puntatore a un contesto di associazione.</span><span class="sxs-lookup"><span data-stu-id="154c8-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="154c8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="154c8-111">Requirements</span></span>  
 <span data-ttu-id="154c8-112">**Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="154c8-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="154c8-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="154c8-113">**DLL:**</span></span>  
  
 <span data-ttu-id="154c8-114">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="154c8-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="154c8-115">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="154c8-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="154c8-116">**Versione di .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="154c8-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="154c8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="154c8-117">See also</span></span>

- [<span data-ttu-id="154c8-118">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="154c8-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)

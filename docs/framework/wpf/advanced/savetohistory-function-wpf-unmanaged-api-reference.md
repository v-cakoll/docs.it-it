---
title: Funzione SaveToHistory (riferimenti alle API WPF non gestite)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- SaveToHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: 6dd101a3-44ad-4143-b228-772156f9b8ff
ms.openlocfilehash: 680c63548482c413a7ceff24a4f38eed589f4682
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745272"
---
# <a name="savetohistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="aa449-102">Funzione SaveToHistory (riferimenti alle API WPF non gestite)</span><span class="sxs-lookup"><span data-stu-id="aa449-102">SaveToHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="aa449-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="aa449-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="aa449-104">Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di windows.</span><span class="sxs-lookup"><span data-stu-id="aa449-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa449-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa449-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveToHistory(  
   __in_ecount(1) IStream* pHistoryStream  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa449-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="aa449-106">Parameters</span></span>  
 <span data-ttu-id="aa449-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="aa449-107">pHistoryStream</span></span>  
 <span data-ttu-id="aa449-108">Un puntatore al flusso di cronologia.</span><span class="sxs-lookup"><span data-stu-id="aa449-108">A pointer to the history stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa449-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aa449-109">Requirements</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa449-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aa449-110">Requirements</span></span>  
 <span data-ttu-id="aa449-111">**Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa449-111">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa449-112">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="aa449-112">**DLL:**</span></span>  
  
 <span data-ttu-id="aa449-113">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="aa449-113">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="aa449-114">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="aa449-114">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="aa449-115">**Versione di .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa449-115">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa449-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa449-116">See also</span></span>
- [<span data-ttu-id="aa449-117">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="aa449-117">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)

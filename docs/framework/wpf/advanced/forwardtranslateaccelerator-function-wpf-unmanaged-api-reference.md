---
title: Funzione ForwardTranslateAccelerator (riferimenti alle API WPF non gestite)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: 4bb7e665bb836dc5f95b14f39179f1d4b9f8173d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080254"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="72348-102">Funzione ForwardTranslateAccelerator (riferimenti alle API WPF non gestite)</span><span class="sxs-lookup"><span data-stu-id="72348-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="72348-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="72348-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="72348-104">Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di windows.</span><span class="sxs-lookup"><span data-stu-id="72348-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72348-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72348-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="72348-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="72348-106">Parameters</span></span>  
 <span data-ttu-id="72348-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="72348-107">pMsg</span></span>  
 <span data-ttu-id="72348-108">Un puntatore a un messaggio.</span><span class="sxs-lookup"><span data-stu-id="72348-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="72348-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="72348-109">appUnhandled</span></span>  
 `true` <span data-ttu-id="72348-110">Quando l'app è già stato fornito l'opportunità di gestire il messaggio di input, ma non è gestito in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="72348-110">when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72348-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="72348-111">Requirements</span></span>  
 <span data-ttu-id="72348-112">**Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72348-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 **<span data-ttu-id="72348-113">DLL:</span><span class="sxs-lookup"><span data-stu-id="72348-113">DLL:</span></span>**  
  
 <span data-ttu-id="72348-114">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="72348-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="72348-115">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="72348-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 **<span data-ttu-id="72348-116">Versione di .NET framework:</span><span class="sxs-lookup"><span data-stu-id="72348-116">.NET Framework Version:</span></span>** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="72348-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72348-117">See also</span></span>

- [<span data-ttu-id="72348-118">Riferimenti alle API non gestite WPF</span><span class="sxs-lookup"><span data-stu-id="72348-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)

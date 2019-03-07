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
ms.openlocfilehash: 2b1914b9a0e478c7ab15fca77b7df952123153ac
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502287"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="a30de-102">Funzione ForwardTranslateAccelerator (riferimenti alle API WPF non gestite)</span><span class="sxs-lookup"><span data-stu-id="a30de-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="a30de-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="a30de-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="a30de-104">Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di windows.</span><span class="sxs-lookup"><span data-stu-id="a30de-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a30de-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a30de-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="a30de-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a30de-106">Parameters</span></span>  
 <span data-ttu-id="a30de-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="a30de-107">pMsg</span></span>  
 <span data-ttu-id="a30de-108">Un puntatore a un messaggio.</span><span class="sxs-lookup"><span data-stu-id="a30de-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="a30de-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="a30de-109">appUnhandled</span></span>  
 <span data-ttu-id="a30de-110">`true` Quando l'app è già stato fornito l'opportunità di gestire il messaggio di input, ma non è gestito in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a30de-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a30de-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a30de-111">Requirements</span></span>  
 <span data-ttu-id="a30de-112">**Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a30de-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a30de-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="a30de-113">**DLL:**</span></span>  
  
 <span data-ttu-id="a30de-114">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="a30de-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="a30de-115">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="a30de-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="a30de-116">**Versione di .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a30de-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a30de-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a30de-117">See also</span></span>
- [<span data-ttu-id="a30de-118">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="a30de-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)

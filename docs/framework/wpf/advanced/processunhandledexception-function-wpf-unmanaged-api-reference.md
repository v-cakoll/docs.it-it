---
title: Funzione ProcessUnhandledException (riferimenti alle API WPF non gestite)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: c3997415c19483a69e66d8fe68c6ec9241f7ad0d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356216"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="1f83e-102">Funzione ProcessUnhandledException (riferimenti alle API WPF non gestite)</span><span class="sxs-lookup"><span data-stu-id="1f83e-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="1f83e-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="1f83e-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="1f83e-104">Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="1f83e-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f83e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f83e-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f83e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1f83e-106">Parameters</span></span>  
 <span data-ttu-id="1f83e-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="1f83e-107">errorMsg</span></span>  
 <span data-ttu-id="1f83e-108">Messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="1f83e-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f83e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1f83e-109">Requirements</span></span>  
 <span data-ttu-id="1f83e-110">**Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f83e-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f83e-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="1f83e-111">**DLL:**</span></span>  
  
 <span data-ttu-id="1f83e-112">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="1f83e-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="1f83e-113">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="1f83e-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="1f83e-114">**Versione di .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f83e-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f83e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f83e-115">See also</span></span>
- [<span data-ttu-id="1f83e-116">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="1f83e-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)

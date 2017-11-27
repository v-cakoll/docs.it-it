---
title: Attivare la funzione (riferimenti alle API non gestita di WPF)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: Acrivate
api_location: PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 68f3f2a29da11a648b8c635667de6493a04ccd54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="9990a-102">Attivare la funzione (riferimenti alle API non gestita di WPF)</span><span class="sxs-lookup"><span data-stu-id="9990a-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="9990a-103">Questa API supporta l'infrastruttura di Windows Presentation Foundation (WPF) e non deve essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="9990a-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="9990a-104">Utilizzata dall'infrastruttura di Windows Presentation Foundation (WPF) per la gestione di windows.</span><span class="sxs-lookup"><span data-stu-id="9990a-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9990a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9990a-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9990a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9990a-106">Parameters</span></span>  
 <span data-ttu-id="9990a-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="9990a-107">pParameters</span></span>  
 <span data-ttu-id="9990a-108">Puntatore a parametri di attivazione della finestra.</span><span class="sxs-lookup"><span data-stu-id="9990a-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="9990a-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="9990a-109">ppInner</span></span>  
 <span data-ttu-id="9990a-110">Un puntatore all'indirizzo di un buffer a elemento singolo contenente un puntatore a un <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> oggetto.</span><span class="sxs-lookup"><span data-stu-id="9990a-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9990a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9990a-111">Requirements</span></span>  
 <span data-ttu-id="9990a-112">**Piattaforme:** vedere [requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9990a-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9990a-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="9990a-113">**DLL:**</span></span>  
  
 <span data-ttu-id="9990a-114">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="9990a-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="9990a-115">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="9990a-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="9990a-116">**Versione di .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9990a-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9990a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9990a-117">See Also</span></span>  
 [<span data-ttu-id="9990a-118">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="9990a-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)

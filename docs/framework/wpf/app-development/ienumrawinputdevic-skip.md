---
title: IEnumRAWINPUTDEVIC:Skip
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e232d2525f9dfa339516f766d417ea9c3ee976c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="7242c-102">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="7242c-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="7242c-103">Indica all'enumeratore di ignorare i successivi `celt` elementi dell'enumerazione in modo che la chiamata successiva a [ienumrawinputdevic: Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) non restituirà gli elementi.</span><span class="sxs-lookup"><span data-stu-id="7242c-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7242c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7242c-104">Syntax</span></span>  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7242c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7242c-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="7242c-106">[in] Numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="7242c-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="7242c-107">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7242c-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="7242c-108">HRESULT: S_OK se il numero di elementi forniti è `celt`; in caso contrario S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="7242c-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>

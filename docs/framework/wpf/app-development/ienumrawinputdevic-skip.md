---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: f7d7df77c54d4551025aa5a344c96083c263f455
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949760"
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="8a534-102">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="8a534-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="8a534-103">Indica all'enumeratore di ignorare i successivi `celt` gli elementi nell'enumerazione in modo che alla successiva chiamata a [ienumrawinputdevic: Next](ienumrawinputdevic-next.md) non restituirà gli elementi.</span><span class="sxs-lookup"><span data-stu-id="8a534-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a534-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a534-104">Syntax</span></span>  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a534-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8a534-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="8a534-106">[in] Numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="8a534-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="8a534-107">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8a534-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="8a534-108">HRESULT: S_OK se il numero di elementi forniti è `celt`; In caso contrario S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="8a534-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>

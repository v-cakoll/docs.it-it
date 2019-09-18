---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: a74f71345a22f6d766c2d5966ca5d2cb33ab756e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053371"
---
# <a name="ienumrawinputdevicskip"></a>IEnumRAWINPUTDEVIC:Skip
Indica all'enumeratore di ignorare gli elementi `celt` successivi nell'enumerazione, in modo che la chiamata successiva a [IEnumRAWINPUTDEVIC: Next](ienumrawinputdevic-next.md) non restituisca tali elementi.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Skip( [in] ULONG celt);  
```  
  
## <a name="parameters"></a>Parametri  
 `celt`  
  
 in Numero di elementi da ignorare.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT: S_OK se il numero di elementi forniti è `celt`; In caso contrario, S_FALSE.

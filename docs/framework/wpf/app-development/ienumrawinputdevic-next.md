---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: c7450a9ababa9cf3cb02d572f5ed84f0791d74e4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053408"
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
`celt` Enumera le strutture [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) successive nell'elenco dell'enumeratore `rgelt` , restituendo tali strutture insieme al numero effettivo di elementi enumerati in. `pceltFetched`  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a>Parametri  
 `celt`  
  
 in Numero di strutture [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) restituite `rgelt`in.  
  
 `rgelt`  
  
 [out] Matrice di dimensione celt (o superiore) per ricevere le strutture RAWINPUTDEVICE enumerate.  
  
 `pceltFetched`  
  
 [out] Puntatore al numero di elementi effettivamente forniti in `rgelt`. Il chiamante può passare `NULL` se `rgelt` è uno.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT: S_OK se il numero di elementi forniti è `celt`; In caso contrario, S_FALSE.

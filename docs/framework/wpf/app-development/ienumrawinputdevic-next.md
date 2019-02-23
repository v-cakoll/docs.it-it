---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: a1f76bf42da9a311633de39e42dee2055fac4a27
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745185"
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
Enumera le `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) nell'elenco dell'enumeratore, che vengono restituiti in strutture `rgelt` insieme al numero effettivo di elementi enumerati in `pceltFetched`.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a>Parametri  
 `celt`  
  
 [in] Numerosi [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) strutture restituite in `rgelt`.  
  
 `rgelt`  
  
 [out] Matrice di dimensione celt (o superiore) per ricevere le strutture RAWINPUTDEVICE enumerate.  
  
 `pceltFetched`  
  
 [out] Puntatore al numero di elementi effettivamente forniti in `rgelt`. Il chiamante può passare `NULL` se `rgelt` è uno.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT: S_OK se il numero di elementi forniti è `celt`; In caso contrario S_FALSE.

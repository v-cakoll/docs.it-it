---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: 329a2cd96346e199ee834856dd6dbfac6175b722
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43481178"
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
Enumera le `celt` [RAWINPUTDEVICE](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) nell'elenco dell'enumeratore, che vengono restituiti in strutture `rgelt` insieme al numero effettivo di elementi enumerati in `pceltFetched`.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a>Parametri  
 `celt`  
  
 [in] Numerosi [RAWINPUTDEVICE](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) strutture restituite in `rgelt`.  
  
 `rgelt`  
  
 [out] Matrice di dimensione celt (o superiore) per ricevere le strutture RAWINPUTDEVICE enumerate.  
  
 `pceltFetched`  
  
 [out] Puntatore al numero di elementi effettivamente forniti in `rgelt`. Il chiamante può passare `NULL` se `rgelt` è uno.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT: S_OK se il numero di elementi forniti è `celt`; in caso contrario S_FALSE.

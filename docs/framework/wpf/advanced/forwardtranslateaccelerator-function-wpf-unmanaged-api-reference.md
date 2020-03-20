---
title: Funzione ForwardTranslateAccelerator - riferimento all'API non gestita WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: a0a01be3000dc53df7855cb74015ba1164206838
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186626"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)
Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere utilizzata direttamente dal codice.  
  
 Utilizzato dall'infrastruttura di Windows Presentation Foundation (WPF) per la gestione delle finestre.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a>Parametri  
 pMsg  
 Puntatore a un messaggio.  
  
 appNon gestito  
 `true`quando all'app è già stata data la possibilità di gestire il messaggio di input, ma non l'ha gestito; in `false`caso contrario, .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere Requisiti di sistema [di .NET Framework](../../get-started/system-requirements.md).  
  
 **DLL:**  
  
 In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll  
  
 In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll  
  
 **Versione di .NET Framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti alle API non gestite WPF](wpf-unmanaged-api-reference.md)

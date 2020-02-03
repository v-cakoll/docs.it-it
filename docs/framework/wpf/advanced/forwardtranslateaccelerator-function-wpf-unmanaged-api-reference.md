---
title: Funzione ForwardTranslateAccelerator-informazioni di riferimento sulle API WPF non gestite
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: f6e8208ffe2c186234f30f31e346ca6b1d0be4c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747044"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>Funzione ForwardTranslateAccelerator (riferimenti alle API non gestite WPF)
Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere usata direttamente dal codice.  
  
 Utilizzato dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di Windows.  
  
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
  
 appUnhandled  
 `true` quando l'app ha già avuto la possibilità di gestire il messaggio di input, ma non lo ha gestito; in caso contrario, `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [.NET Framework requisiti di sistema](../../get-started/system-requirements.md).  
  
 **DLL**  
  
 Nel .NET Framework 3,0 e 3,5: PresentationHostDLL. dll  
  
 In .NET Framework 4 e versioni successive: PresentationHost_v0400. dll  
  
 **Versione .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti alle API non gestite di WPF](wpf-unmanaged-api-reference.md)

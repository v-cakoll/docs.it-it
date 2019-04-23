---
title: Funzione ForwardTranslateAccelerator (riferimenti alle API WPF non gestite)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: 4bb7e665bb836dc5f95b14f39179f1d4b9f8173d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080254"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>Funzione ForwardTranslateAccelerator (riferimenti alle API WPF non gestite)
Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.  
  
 Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di windows.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a>Parametri  
 pMsg  
 Un puntatore a un messaggio.  
  
 appUnhandled  
 `true` Quando l'app è già stato fornito l'opportunità di gestire il messaggio di input, ma non è gestito in caso contrario, `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **DLL:**  
  
 In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll  
  
 In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll  
  
 **Versione di .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti alle API non gestite di WPF](wpf-unmanaged-api-reference.md)

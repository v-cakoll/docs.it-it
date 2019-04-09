---
title: Funzione SaveToHistory (riferimenti alle API WPF non gestite)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- SaveToHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: 6dd101a3-44ad-4143-b228-772156f9b8ff
ms.openlocfilehash: 3f6413558ff1f259e497c6a1c31eb2664f70cc48
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213716"
---
# <a name="savetohistory-function-wpf-unmanaged-api-reference"></a>Funzione SaveToHistory (riferimenti alle API WPF non gestite)
Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.  
  
 Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di windows.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SaveToHistory(  
   __in_ecount(1) IStream* pHistoryStream  
)  
```  
  
## <a name="parameters"></a>Parametri  
 pHistoryStream  
 Un puntatore al flusso di cronologia.  
  
## <a name="requirements"></a>Requisiti  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **DLL:**  
  
 In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll  
  
 In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll  
  
 **Versione di .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti alle API non gestite WPF](wpf-unmanaged-api-reference.md)

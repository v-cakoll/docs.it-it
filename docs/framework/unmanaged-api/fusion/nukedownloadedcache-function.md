---
title: Funzione NukeDownloadedCache
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29f492173a7fd22ab497d6e0096798e164fccf26
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796300"
---
# <a name="nukedownloadedcache-function"></a>Funzione NukeDownloadedCache
Elimina la Download Cache di Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore COM standard, come definito in WinError. h.  
  
## <a name="remarks"></a>Note  
 Il Download Cache CLR è l'area in cui gli assembly con nome sicuro scaricati da un URL vengono archiviati per poter essere riutilizzati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria** Fusion. dll e mscorwks. dll. Usare Fusion. dll invece di mscorwks. dll per assicurarsi di avere come destinazione la versione corretta del .NET Framework.  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione CreateHistoryReader](createhistoryreader-function.md)
- [Funzione GetHistoryFileDirectory](gethistoryfiledirectory-function.md)
- [Funzioni statiche globali Fusion](fusion-global-static-functions.md)

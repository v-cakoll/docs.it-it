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
ms.openlocfilehash: 80891da7d61aa5114d5cc4d8aff4c7ce82020237
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720093"
---
# <a name="nukedownloadedcache-function"></a>Funzione NukeDownloadedCache
Elimina la download cache common language runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H.  
  
## <a name="remarks"></a>Note  
 La download cache CLR è l'area in cui sono archiviati gli assembly con nome sicuro che vengono scaricati da un URL per un eventuale riutilizzo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** Fusion. dll e mscorwks. dll. Usare Fusion. dll invece di Mscorwks. dll per verificare che da usare come destinazione la versione corretta di .NET Framework.  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Funzione CreateHistoryReader](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [Funzione GetHistoryFileDirectory](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)
- [Funzioni statiche globali Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)

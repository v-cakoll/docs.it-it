---
title: Funzione NukeDownloadedCache
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: NukeDownloadedCache
helpviewer_keywords: NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5ff24cf46ab24fe94ab19cee04d9e32ed1a34b53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** Fusion e Mscorwks.dll. Utilizzare il file Fusion.dll anziché Mscorwks.dll per garantire che la versione corretta di .NET Framework di destinazione.  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [CreateHistoryReader (funzione)](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [GetHistoryFileDirectory (funzione)](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 [Funzioni statiche globali Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)

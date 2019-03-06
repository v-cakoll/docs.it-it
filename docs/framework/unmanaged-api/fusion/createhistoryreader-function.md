---
title: Funzione CreateHistoryReader
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e9c9866ee5ee3076d144dc732286ee008cd78c4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487251"
---
# <a name="createhistoryreader-function"></a>Funzione CreateHistoryReader
Crea un lettore di cronologia per il file specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a>Parametri  
 `wzFilePath`  
 [in] Il percorso del file.  
  
 `ppHistoryReader`  
 [out] Al termine dell'esecuzione, contiene un puntatore per il Visualizzatore della cronologia.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore COM standard, come definito nel file Winerror. H, oltre a quelli descritti nella tabella seguente.  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|S_OK|Indica che il metodo è stato completato correttamente.|  
|E_INVALIDARG|Indica che `wzFilePath` o `ppHistoryReader` sono impostate su un riferimento null.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Libreria:** Fusion.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Funzioni statiche globali Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)

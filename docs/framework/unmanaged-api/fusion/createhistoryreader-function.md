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
ms.openlocfilehash: 2710d14d6e73879fd17a6b58659463ea205f2384
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795374"
---
# <a name="createhistoryreader-function"></a>Funzione CreateHistoryReader
Crea un lettore della cronologia per il file specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a>Parametri  
 `wzFilePath`  
 in Percorso del file.  
  
 `ppHistoryReader`  
 out Al termine dell'operazione, contiene un puntatore al lettore della cronologia.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore COM standard come definito in WinError. h, oltre ai valori descritti nella tabella seguente.  
  
|Codice restituito|DESCRIZIONE|  
|-----------------|-----------------|  
|S_OK|Indica che il metodo è stato completato correttamente.|  
|E_INVALIDARG|Indica che `wzFilePath` o `ppHistoryReader` sono impostati su un riferimento null.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Libreria** Fusion. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali Fusion](fusion-global-static-functions.md)

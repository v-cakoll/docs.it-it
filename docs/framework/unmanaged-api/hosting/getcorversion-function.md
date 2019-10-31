---
title: Funzione GetCORVersion
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
ms.openlocfilehash: 1283abaf6b08af1d842d8fe4469f7f6c15e38ec5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136426"
---
# <a name="getcorversion-function"></a>Funzione GetCORVersion
Restituisce il numero di versione del Common Language Runtime (CLR) in esecuzione nel processo corrente.  
  
 Questa funzione è stata deprecata nel .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a>Parametri  
 `pbuffer`  
 Puntatore a un buffer in cui CLR restituisce una stringa che specifica la versione del Runtime attualmente caricata nel processo. La stringa restituita assume lo stesso formato delle stringhe passate a [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), ad esempio, "v 1.0.1216". Se il runtime non è ancora stato caricato nel processo, la funzione restituisce le informazioni di directory appropriate per la versione più recente del runtime installato nel computer.  
  
 `cchBuffer`  
 Numero di caratteri (`WCHAR`s) che possono essere conservati in `pbuffer`.  
  
 `dwLength`  
 Puntatore al numero di caratteri effettivamente restituiti in `pbuffer`. Se `pbuffer` è un puntatore null, il runtime restituisce E_POINTER. Se il numero di caratteri è maggiore della lunghezza di `pbuffer`, il runtime restituisce ERROR_INSUFFICIENT_BUFFER.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

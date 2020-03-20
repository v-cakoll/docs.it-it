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
ms.openlocfilehash: 1f40f27651d2d75cf2c3e4d7d1c21e1f47d402af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178186"
---
# <a name="getcorversion-function"></a>Funzione GetCORVersion
Restituisce il numero di versione di Common Language Runtime (CLR) in esecuzione nel processo corrente.  
  
 Questa funzione è stata deprecata in .NET Framework 4.  
  
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
 Puntatore a un buffer in cui CLR restituisce una stringa che specifica la versione del runtime attualmente caricata nel processo. La stringa restituita ha lo stesso formato delle stringhe passate a [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), ad esempio "v1.0.1216". Se il runtime non è ancora stato caricato nel processo, la funzione restituisce le informazioni di directory appropriate per la versione più recente del runtime installata nel computer.  
  
 `cchBuffer`  
 Il numero di`WCHAR`caratteri (s) `pbuffer`che possono essere contenuti in .  
  
 `dwLength`  
 Puntatore al numero di caratteri `pbuffer`effettivamente restituiti in . Se `pbuffer` è un puntatore null, il runtime restituisce E_POINTER. Se il numero di caratteri è `pbuffer` maggiore della lunghezza di , il runtime restituisce ERROR_INSUFFICIENT_BUFFER.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** Mscoree  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

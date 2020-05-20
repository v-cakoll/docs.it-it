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
ms.openlocfilehash: 23d68e8e4bbd87779e3b49f0c40f5a5ab9f5124f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617217"
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
 Puntatore a un buffer in cui CLR restituisce una stringa che specifica la versione del Runtime attualmente caricata nel processo. La stringa restituita assume lo stesso formato delle stringhe passate a [CorBindToRuntimeEx](corbindtoruntimeex-function.md), ad esempio, "v 1.0.1216". Se il runtime non è ancora stato caricato nel processo, la funzione restituisce le informazioni di directory appropriate per la versione più recente del runtime installato nel computer.  
  
 `cchBuffer`  
 Numero di caratteri `WCHAR` che possono essere conservati in `pbuffer` .  
  
 `dwLength`  
 Puntatore al numero di caratteri effettivamente restituiti in `pbuffer` . Se `pbuffer` è un puntatore null, il runtime restituisce E_POINTER. Se il numero di caratteri è maggiore della lunghezza di `pbuffer` , il runtime restituisce ERROR_INSUFFICIENT_BUFFER.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)

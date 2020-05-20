---
title: Funzione GetCORSystemDirectory
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
ms.openlocfilehash: 137b2e30916cb1934d4389c5668bfb7eb5066064
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617230"
---
# <a name="getcorsystemdirectory-function"></a>Funzione GetCORSystemDirectory
Restituisce la directory di installazione del Common Language Runtime (CLR) che viene caricata nel processo. La directory di installazione è completamente qualificata, ad esempio "c:\Windows\Microsoft.net\framework\v1.0.3705".  
  
 Questa funzione è deprecata. Viene sostituito dal metodo [ICLRRuntimeInfo:: GetRuntimeDirectory](iclrruntimeinfo-getruntimedirectory-method.md) fornito nella .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCORSystemDirectory (
    [out] LPWSTR  pbuffer,
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a>Parametri  
 `pbuffer`  
 out Buffer in cui il runtime restituisce una stringa che contiene il nome completo della directory di installazione per il runtime caricato nel processo. Se il runtime non è ancora stato caricato nel processo, la funzione restituisce le informazioni di directory appropriate per la versione più recente del runtime installato nel computer.  
  
 `cchBuffer`  
 in Dimensione, in byte, di `pbuffer` .  
  
 `dwLength`  
 out Numero di caratteri restituiti in `pbuffer` .  
  
## <a name="remarks"></a>Osservazioni  
  
> [!CAUTION]
> Non utilizzare questa funzione nei processi che eseguono la versione 4 di CLR. Se nel computer è installata una versione precedente di CLR, questa funzione restituisce la directory di installazione per tale versione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)

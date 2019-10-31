---
title: Funzione PreBindAssemblyEx
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
ms.openlocfilehash: db3ba3380d1fc30a8f34683618b5cc326d7d1906
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123049"
---
# <a name="prebindassemblyex-function"></a>Funzione PreBindAssemblyEx
Ottiene il nome visualizzato post-criteri per un assembly.  
  
 Questa funzione supporta l'infrastruttura .NET Framework e non può essere usata direttamente dal codice.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
## <a name="parameters"></a>Parametri  
 `pAppCtx`  
 in Identifica il contesto dell'applicazione.  
  
 `pName`  
 in Identifica il nome dell'assembly.  
  
 `pAsmParent`  
 in Identifica l'assembly padre. Questo parametro viene ignorato.  
  
 `pwzRuntimeVersion`  
 in Identifica la versione del runtime.  
  
 `ppNamePostPolicy`  
 out Contiene il nome visualizzato post-criteri.  
  
 `pvReserved`  
 in Riservato per l'estendibilità futura. `pvReserved` deve essere un riferimento null.  
  
## <a name="remarks"></a>Note  
 Il parametro di output `ppNamePostPolicy` viene impostato solo se la funzione restituisce HRESULT FUSION_E_REF_DEF_MISMATCH. In caso contrario, è null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali Fusion](fusion-global-static-functions.md)

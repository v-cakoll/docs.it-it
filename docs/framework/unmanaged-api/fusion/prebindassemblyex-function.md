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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8aa2d174200db76f5c7a6db43e14bb6904604226
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796336"
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
 in Riservato per l'estendibilità futura. `pvReserved`deve essere un riferimento null.  
  
## <a name="remarks"></a>Note  
 Il `ppNamePostPolicy` parametro di output viene impostato solo se la funzione restituisce HRESULT FUSION_E_REF_DEF_MISMATCH. In caso contrario, è null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali Fusion](fusion-global-static-functions.md)

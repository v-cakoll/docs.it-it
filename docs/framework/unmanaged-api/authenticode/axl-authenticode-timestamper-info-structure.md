---
title: Struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7f4fff4f2c2b3dd04625f4cf50b8b19a0ef6f39
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "43254659"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a>Struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO
Definisce le informazioni su chi ha apposto il timestamp Authenticode.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`cbSize`|Dimensione della struttura.|  
|`dwError`|Codice di errore.|  
|`algHash`|Algoritmo hash.|  
|`ftTimestamp`|Ora del timestamp.|  
|`pChainContext`|Contesto della catena del timestamp.  Vedere le [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) struttura.|  
  
## <a name="see-also"></a>Vedere anche  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)

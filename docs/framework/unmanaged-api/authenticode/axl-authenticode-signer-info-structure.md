---
title: Struttura AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 232c78db32aecd0ee1379d4d969fa0378db4159a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741363"
---
# <a name="axlauthenticodesignerinfo-structure"></a>Struttura AXL_AUTHENTICODE_SIGNER_INFO
Definisce le informazioni su chi ha apposto la firma Authenticode.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`cbSize`|Dimensione della struttura.|  
|`dwError`|Codice di errore.|  
|`algHash`|Algoritmo hash.|  
|`pwszHash`|Hash.|  
|`pwszDescription`|Descrizione.|  
|`pwszDescriptionUrl`|URL della descrizione.|  
|`pChainContext`|Contesto della catena del firmatario. Vedere le [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) struttura.|  
  
## <a name="see-also"></a>Vedere anche

- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)

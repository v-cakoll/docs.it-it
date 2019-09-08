---
title: Struttura AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9aaa0258b53b6b39874c8c99c71ecf53cbdb8f97
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787074"
---
# <a name="axl_authenticode_signer_info-structure"></a>Struttura AXL_AUTHENTICODE_SIGNER_INFO
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
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`cbSize`|Dimensione della struttura.|  
|`dwError`|Codice di errore.|  
|`algHash`|Algoritmo hash.|  
|`pwszHash`|Hash.|  
|`pwszDescription`|Descrizione.|  
|`pwszDescriptionUrl`|URL della descrizione.|  
|`pChainContext`|Contesto della catena del firmatario. Vedere la struttura [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .|  
  
## <a name="see-also"></a>Vedere anche

- [Authenticode](index.md)

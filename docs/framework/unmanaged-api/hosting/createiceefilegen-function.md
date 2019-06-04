---
title: Funzione CreateICeeFileGen
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57163ccfcc6dff343a8bbc7d63564ae6b57b5ff6
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490498"
---
# <a name="createiceefilegen-function"></a>Funzione CreateICeeFileGen
Crea un' [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) oggetto.  
  
 Questa funzione è stata deprecata in .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ceeFileGen`  
 [out] Un puntatore all'indirizzo di un nuovo `ICeeFileGen` oggetto.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce i codici di errore COM standard.  
  
## <a name="remarks"></a>Note  
 Il `ICeeFileGen` oggetto viene usato per creare common language runtime (CLR) i file eseguibili portabili (PE).  
  
 Chiamare il [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) funzione eliminare definitivamente il `ICeeFileGen` al termine dell'oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ICeeFileGen.h  
  
 **Libreria:** MSCorPE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

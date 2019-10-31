---
title: Interfaccia ICLRHostProtectionManager
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
ms.openlocfilehash: 0487a87420c888cf5466f54c28c2d89623260add
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141057"
---
# <a name="iclrhostprotectionmanager-interface"></a>Interfaccia ICLRHostProtectionManager
Consente all'host di bloccare le classi, i metodi, le proprietà e i campi gestiti specifici dall'esecuzione in codice parzialmente attendibile.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[SetEagerSerializeGrantSets](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|Garantisce che alcune condizioni di Race rare che possono causare errori irreversibili di Common Language Runtime (CLR) non verranno mai verificate.|  
|[Metodo SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|Specifica le categorie di tipi e membri gestiti che devono essere bloccati dall'esecuzione in codice parzialmente attendibile.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)

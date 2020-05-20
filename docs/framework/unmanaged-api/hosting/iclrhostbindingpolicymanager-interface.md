---
title: Interfaccia ICLRHostBindingPolicyManager
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
ms.openlocfilehash: 3cf2a945607bf85a51dbec35342ff5ac46878bca
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703573"
---
# <a name="iclrhostbindingpolicymanager-interface"></a>Interfaccia ICLRHostBindingPolicyManager
Fornisce metodi che consentono all'host di valutare i criteri di associazione correnti e di comunicare le modifiche dei criteri per un assembly specificato.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EvaluatePolicy](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|Valuta i criteri di associazione per conto dell'host.|  
|[Metodo ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|Modifica i criteri di associazione per l'assembly specificato e crea una nuova versione del criterio.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
- [Interfaccia IHostAssemblyStore](ihostassemblystore-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)

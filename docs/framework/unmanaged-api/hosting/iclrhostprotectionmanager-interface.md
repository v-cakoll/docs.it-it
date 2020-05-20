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
ms.openlocfilehash: 7b1fc70380fff3c551c56043f49c2deda507e366
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703848"
---
# <a name="iclrhostprotectionmanager-interface"></a>Interfaccia ICLRHostProtectionManager
Consente all'host di bloccare le classi, i metodi, le proprietà e i campi gestiti specifici dall'esecuzione in codice parzialmente attendibile.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[SetEagerSerializeGrantSets](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|Garantisce che alcune condizioni di Race rare che possono causare errori irreversibili di Common Language Runtime (CLR) non verranno mai verificate.|  
|[Metodo SetProtectedCategories](iclrhostprotectionmanager-setprotectedcategories-method.md)|Specifica le categorie di tipi e membri gestiti che devono essere bloccati dall'esecuzione in codice parzialmente attendibile.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EApiCategories](eapicategories-enumeration.md)
- [Interfaccia ICLRControl](iclrcontrol-interface.md)

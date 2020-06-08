---
title: Interfaccia IHostAssemblyManager
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
ms.openlocfilehash: 4e32a36a4cf751bf7c5a2c918fde0122f21b7878
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501592"
---
# <a name="ihostassemblymanager-interface"></a>Interfaccia IHostAssemblyManager
Fornisce metodi che consentono a un host di specificare set di assembly che devono essere caricati dal Common Language Runtime (CLR) o dall'host.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetAssemblyStore](ihostassemblymanager-getassemblystore-method.md)|Ottiene un puntatore a interfaccia a un [IHostAssemblyStore](ihostassemblystore-interface.md) che rappresenta l'elenco di assembly caricati dall'host.|  
|[Metodo GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md)|Ottiene un puntatore a interfaccia a un [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) che rappresenta l'elenco di assembly che l'host prevede venga caricato da CLR.|  
  
## <a name="remarks"></a>Osservazioni  
 L'host non deve implementare `IHostAssemblyManager` o `IHostAssemblyStore` . Se l'host implementa `IHostAssemblyManager` , deve implementare anche `IHostAssemblyStore` .  
  
 Il runtime esegue una query per un oggetto `IHostAssemblyManager` chiamando [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) al momento dell'inizializzazione con un oggetto `IID` di IID_IHostAssemblyManager.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Interfaccia IHostAssemblyStore](ihostassemblystore-interface.md)
- [Interfaccia IHostControl](ihostcontrol-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)

---
title: Interfaccia IHostAssemblyStore
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
ms.openlocfilehash: d7475e2423d4dc6f57e8928514d7991169eef232
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124494"
---
# <a name="ihostassemblystore-interface"></a>Interfaccia IHostAssemblyStore
Fornisce metodi che consentono a un host di caricare assembly e moduli indipendentemente dal Common Language Runtime (CLR).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|Ottiene un riferimento a un assembly a cui non fa riferimento [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) restituito da una chiamata a [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).|  
|[Metodo ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|Risolve un modulo all'interno di un assembly o di un file di risorse collegato (non incorporato).|  
  
## <a name="remarks"></a>Note  
 `IHostAssemblyStore` consente a un host di caricare gli assembly in modo efficiente in base all'identità dell'assembly. L'host carica gli assembly restituendo `IStream` istanze che puntano direttamente ai byte.  
  
 CLR determina se un host ha implementato `IHostAssemblyStore` chiamando `IHostAssemblyManager::GetNonHostAssemblyStores` dopo l'inizializzazione. Questo consente all'host, ad esempio, di controllare l'associazione agli assembly utente, ma di basarsi sul runtime per eseguire l'associazione a .NET Framework assembly.  
  
> [!NOTE]
> Per fornire un'implementazione di `IHostAssemblyStore`, l'host specifica la finalità di risolvere tutti gli assembly a cui non viene fatto riferimento dal `ICLRAssemblyReferenceList` restituiti da `IHostAssemblyManager::GetNonHostStoreAssemblies`.  
  
> [!NOTE]
> Il .NET Framework versione 2,0 non consente all'host di caricare l'immagine nativa di un assembly, come specificato dall'utilità [Generatore di immagini native (Ngen. exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Interfaccia IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

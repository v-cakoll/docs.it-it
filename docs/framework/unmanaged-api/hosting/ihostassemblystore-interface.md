---
title: Interfaccia IHostAssemblyStore
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c795d4baa3030817299f23c3dadf4caf7a5edc5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblystore-interface"></a>Interfaccia IHostAssemblyStore
Fornisce metodi che consentono a un host caricare gli assembly e moduli in modo indipendente da common language runtime (CLR).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|Ottiene un riferimento a un assembly che non fa riferimento il [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) restituito da una chiamata a [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).|  
|[Metodo ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|Risolve un modulo all'interno di un assembly o un file di risorse (non incorporato) collegati.|  
  
## <a name="remarks"></a>Note  
 `IHostAssemblyStore`fornisce un modo per un host caricare gli assembly efficiente in base all'identità dell'assembly. L'host carica gli assembly restituendo `IStream` istanze che puntano direttamente i byte.  
  
 Common Language Runtime determina se un host ha implementato `IHostAssemblyStore` chiamando `IHostAssemblyManager::GetNonHostAssemblyStores` al momento dell'inizializzazione. Ciò consente all'host, ad esempio, per controllare l'associazione di assembly dell'utente, ma per cui si basano sull'ambiente di esecuzione per l'associazione agli assembly .NET Framework.  
  
> [!NOTE]
>  Fornendo un'implementazione di `IHostAssemblyStore`, l'host specifica l'intento di risolvere tutti gli assembly che non fa riferimento il `ICLRAssemblyReferenceList` restituito da `IHostAssemblyManager::GetNonHostStoreAssemblies`.  
  
> [!NOTE]
>  .NET Framework versione 2.0 non fornisce un modo per caricare l'immagine nativa di un assembly, l'host fornito dal [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utilità.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [Interfaccia IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

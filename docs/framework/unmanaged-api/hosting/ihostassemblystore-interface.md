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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4067c1fbcf99c903c892eaec58262d95569114b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173420"
---
# <a name="ihostassemblystore-interface"></a>Interfaccia IHostAssemblyStore
Fornisce metodi che consentono a un host per il caricamento degli assembly e moduli indipendentemente da common language runtime (CLR).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|Ottiene un riferimento a un assembly che non fa riferimento il [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) restituiti da una chiamata a [IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).|  
|[Metodo ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|Risolve un modulo all'interno di un assembly o un file di risorse (non incorporato) collegati.|  
  
## <a name="remarks"></a>Note  
 `IHostAssemblyStore` fornisce un modo per un host caricare gli assembly in modo efficiente in base all'identità dell'assembly. L'host carica gli assembly, restituendo `IStream` istanze che puntano direttamente i byte.  
  
 Il CLR determina se un host è implementata `IHostAssemblyStore` chiamando `IHostAssemblyManager::GetNonHostAssemblyStores` al momento dell'inizializzazione. Ciò consente all'host, ad esempio, per controllare l'associazione di assembly dell'utente, ma affidarsi al runtime di eseguire l'associazione agli assembly .NET Framework.  
  
> [!NOTE]
>  Fornendo un'implementazione di `IHostAssemblyStore`, l'host specifica l'intento di risolvere tutti gli assembly che non fa riferimento il `ICLRAssemblyReferenceList` restituiti da `IHostAssemblyManager::GetNonHostStoreAssemblies`.  
  
> [!NOTE]
>  .NET Framework versione 2.0 non fornisce un modo per caricare l'immagine nativa di un assembly, l'host fornito dal [generatore di immagini Native (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utilità.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Interfaccia IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

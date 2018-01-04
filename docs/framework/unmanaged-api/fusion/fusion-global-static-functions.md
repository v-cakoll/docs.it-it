---
title: Funzioni statiche globali Fusion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged global static functions [.NET Framework], fusion
- fusion global static functions [.NET Framework]
- global static functions [.NET Framework fusion]
ms.assetid: 229b2188-9168-4b44-a987-e1f515494688
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 126edd5f25b56a069a87cd1bd50cce955334a342
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="fusion-global-static-functions"></a>Funzioni statiche globali Fusion
In questa sezione vengono descritte le funzioni statiche globali non gestite utilizzate dall'API Fusion.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Funzione ClearDownloadCache](../../../../docs/framework/unmanaged-api/fusion/cleardownloadcache-function.md)  
 Cancella la cache di assembly globale degli assembly scaricato.  
  
 [Funzione CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 Confronta due identità di assembly per determinare se sono equivalenti.  
  
 [Funzione CreateApplicationContext](../../../../docs/framework/unmanaged-api/fusion/createapplicationcontext-function.md)  
 Solo per uso interno. (Questa funzione supporta l'infrastruttura .NET Framework e non deve essere utilizzato direttamente dal codice).  
  
 [Funzione CreateAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/createassemblycache-function.md)  
 Ottiene un puntatore a un nuovo [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) istanza che rappresenta la global assembly cache.  
  
 [Funzione CreateAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/createassemblyenum-function.md)  
 Ottiene un puntatore a un [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) istanza che rappresenta un elenco di oggetti presenti nell'assembly specificato.  
  
 [Funzione CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)  
 Ottiene un puntatore a un [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) istanza che rappresenta l'identità univoca dell'assembly con il nome specificato.  
  
 [Funzione CreateHistoryReader](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 Crea un lettore di cronologia per il file specificato.  
  
 [Funzione CreateInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/createinstallreferenceenum-function.md)  
 Ottiene un puntatore a un [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) istanza che rappresenta un elenco di riferimenti di un'applicazione per l'assembly specificato.  
  
 [Funzione GetAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/getappidauthority-function.md)  
 Ottiene un puntatore a un [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) che gestisce le chiavi per le identità delle applicazioni e i riferimenti.  
  
 [Funzione GetAssemblyIdentityFromFile](../../../../docs/framework/unmanaged-api/fusion/getassemblyidentityfromfile-function.md)  
 Ottiene un puntatore a un `IUnknown` oggetto con l'oggetto specificato `IID` nell'assembly nel percorso del file specificato.  
  
 [Funzione GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 Ottiene il percorso all'assembly memorizzati nella cache, utilizzando i flag specificati.  
  
 [Funzione GetHistoryFileDirectory](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 Recupera il percorso della directory della cronologia dell'applicazione.  
  
 [Funzione GetIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/getidentityauthority-function.md)  
 Ottiene un puntatore a un [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) che gestisce le chiavi per gli oggetti di codice.  
  
 [Funzione IsFrameworkAssembly](../../../../docs/framework/unmanaged-api/fusion/isframeworkassembly-function.md)  
 Ottiene un valore che indica se l'assembly specificato è stato gestito.  
  
 [Funzione NukeDownloadedCache](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 Elimina la download cache common language runtime.  
  
 [Funzione PreBindAssemblyEx](../../../../docs/framework/unmanaged-api/fusion/prebindassemblyex-function.md)  
 Ottiene il nome visualizzato di post-criteri per un assembly.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Interfacce Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
  
 [Enumerazioni Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [Strutture Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
  
 [Global Assembly Cache](../../../../docs/framework/app-domains/gac.md)

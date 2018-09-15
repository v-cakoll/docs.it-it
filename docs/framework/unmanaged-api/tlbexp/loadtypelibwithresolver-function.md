---
title: Funzione LoadTypeLibWithResolver
ms.date: 03/30/2017
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6a217e2212bb900d7ba83ccdd9cb00d30454baf
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45625724"
---
# <a name="loadtypelibwithresolver-function"></a>Funzione LoadTypeLibWithResolver
Carica una libreria dei tipi e Usa il parametro fornito [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) per risolvere eventuali librerie dei tipi riferimento internamente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
#### <a name="parameters"></a>Parametri  
 `szFile`  
 [in] Percorso del file della libreria dei tipi.  
  
 `regkind`  
 [in] Oggetto [enumerazione REGKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) flag che controlla la modalità di registrazione della libreria dei tipi. I valori possibili sono:  
  
-   `REGKIND_DEFAULT`: Il comportamento di registrazione predefinito da utilizzare.  
  
-   `REGKIND_REGISTER`: Registra questa libreria dei tipi.  
  
-   `REGKIND_NONE`: Non registrare questa libreria dei tipi.  
  
 `pTlbResolver`  
 [in] Un puntatore all'implementazione del [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).  
  
 `pptlib`  
 [out] Un riferimento alla libreria dei tipi in fase di caricamento.  
  
## <a name="return-value"></a>Valore restituito  
 Uno dei valori di HRESULT elencati nella tabella seguente.  
  
|Valore restituito|Significato|  
|------------------|-------------|  
|`S_OK`|Operazione completata.|  
|`E_OUTOFMEMORY`|Memoria insufficiente.|  
|`E_POINTER`|Uno o più degli indicatori di misura non sono validi.|  
|`E_INVALIDARG`|Uno o più argomenti sono validi.|  
|`TYPE_E_IOERROR`|La funzione non è stato possibile scrivere nel file.|  
|`TYPE_E_REGISTRYACCESS`|Non è stato possibile aprire il database di registrazione del sistema.|  
|`TYPE_E_INVALIDSTATE`|Non è stato possibile aprire la libreria dei tipi.|  
|`TYPE_E_CANTLOADLIBRARY`|Non è stato possibile caricare la libreria dei tipi o DLL.|  
  
## <a name="remarks"></a>Note  
 Il [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) chiama il `LoadTypeLibWithResolver` funzione durante il processo di conversione di assembly a libreria dei tipi.  
  
 Questa funzione consente di caricare la libreria dei tipi specificata con accesso minimo al Registro di sistema. La funzione esamina quindi la libreria dei tipi di librerie dei tipi a cui si fa riferimento internamente ognuno dei quali deve essere caricato e aggiunti alla libreria dei tipi padre.  
  
 Prima di caricare una libreria dei tipi riferimento, il percorso del file di riferimento deve essere risolto in un percorso completo del file. Questa operazione viene eseguita tramite il [ResolveTypeLib (metodo)](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) fornito dal [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), che viene passato il `pTlbResolver` parametro.  
  
 Quando è noto il percorso completo del file della libreria dei tipi riferimento, il `LoadTypeLibWithResolver` funzione carica e aggiunge la libreria dei tipi di cui si fa riferimento alla libreria dei tipi padre, la creazione di una libreria dei tipi master combinato.  
  
 Dopo che viene risolto e carica tutte le librerie dei tipi riferimento internamente, la funzione restituisce un riferimento alla libreria dei tipi risolto master nel `pptlib` parametro.  
  
 Il `LoadTypeLibWithResolver` funzione viene in genere chiamata dal [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), che fornisce un proprio interni [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementazione nel `pTlbResolver` parametro.  
  
 Se si chiama `LoadTypeLibWithResolver` direttamente, è necessario fornire il proprio [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** TlbRef. H  
  
 **Libreria:** TlbRef. lib  
  
 **Versione di .NET framework:** 3.5, 3.0, 2.0  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni di supporto Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [Funzione LoadTypeLibEx dell'](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)

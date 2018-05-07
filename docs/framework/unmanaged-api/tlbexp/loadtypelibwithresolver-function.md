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
ms.openlocfilehash: 751794746e26bd8f0ec2cd6db2f62876e78674e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="loadtypelibwithresolver-function"></a>Funzione LoadTypeLibWithResolver
Carica una libreria dei tipi e utilizza il parametro fornito [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) per risolvere qualsiasi tipo riferimento internamente.  
  
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
 [in] Oggetto [enumerazione REGKIND](https://msdn.microsoft.com/library/windows/desktop/ms221159.aspx) flag che determina come viene registrata la libreria dei tipi. I valori possibili sono:  
  
-   `REGKIND_DEFAULT`: Viene usato il comportamento di registrazione predefinito.  
  
-   `REGKIND_REGISTER`: Registrare questa libreria dei tipi.  
  
-   `REGKIND_NONE`: Non registrare la libreria dei tipi.  
  
 `pTlbResolver`  
 [in] Un puntatore all'implementazione del [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).  
  
 `pptlib`  
 [out] Un riferimento alla libreria dei tipi in fase di caricamento.  
  
## <a name="return-value"></a>Valore restituito  
 Uno dei valori HRESULT elencati nella tabella seguente.  
  
|Valore restituito|Significato|  
|------------------|-------------|  
|`S_OK`|Operazione completata.|  
|`E_OUTOFMEMORY`|Memoria insufficiente.|  
|`E_POINTER`|Uno o più dei puntatori non sono validi.|  
|`E_INVALIDARG`|Uno o più argomenti non sono validi.|  
|`TYPE_E_IOERROR`|La funzione non può scrivere nel file.|  
|`TYPE_E_REGISTRYACCESS`|Impossibile aprire il database di sistema di registrazione.|  
|`TYPE_E_INVALIDSTATE`|Non è stato possibile aprire la libreria dei tipi.|  
|`TYPE_E_CANTLOADLIBRARY`|Impossibile caricare la libreria dei tipi o DLL.|  
  
## <a name="remarks"></a>Note  
 Il [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) chiamate di `LoadTypeLibWithResolver` funzione durante il processo di conversione da assembly a libreria.  
  
 Questa funzione consente di caricare la libreria dei tipi specificata con un accesso minimo al Registro di sistema. Quindi, la funzione esamina la libreria dei tipi per cui si fa riferimento internamente librerie dei tipi, ognuno dei quali deve essere caricato e aggiunto alla libreria dei tipi padre.  
  
 Prima di caricare una libreria dei tipi di riferimento, il percorso del file di riferimento deve essere risolto in un percorso completo del file. Questa operazione viene eseguita tramite il [ResolveTypeLib (metodo)](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) forniti dal [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), che viene passato il `pTlbResolver` parametro.  
  
 Quando il percorso completo del file della libreria dei tipi a cui fa riferimento è noto, il `LoadTypeLibWithResolver` funzione carica e aggiunge la libreria dei tipi a cui fa riferimento alla libreria dei tipi padre, la creazione di una libreria dei tipi master combinato.  
  
 Dopo che viene risolto e carica tutte le librerie dei tipi a cui fa riferimento internamente, la funzione restituisce un riferimento alla libreria di tipi master risolta nel `pptlib` parametro.  
  
 Il `LoadTypeLibWithResolver` funzione viene in genere chiamata dal [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), che fornisce il proprio interno [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementazione nel `pTlbResolver` parametro.  
  
 Se si chiama `LoadTypeLibWithResolver` direttamente, è necessario fornire la propria [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** TlbRef. H  
  
 **Libreria:** TlbRef. lib  
  
 **Versione di .NET framework:** 3.5, 3.0, 2.0  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni di supporto Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [Funzione LoadTypeLibEx dell'](https://msdn.microsoft.com/library/windows/desktop/ms221249\(v=vs.85\).aspx)

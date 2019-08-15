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
ms.openlocfilehash: 6b9bec757071a98e085ccdeee3fc66bfc07f52bc
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040169"
---
# <a name="loadtypelibwithresolver-function"></a>Funzione LoadTypeLibWithResolver
Carica una libreria dei tipi e utilizza l' [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) fornita per risolvere le librerie dei tipi a cui si fa riferimento internamente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a>Parametri  
 `szFile`  
 in Percorso del file della libreria dei tipi.  
  
 `regkind`  
 in Flag di [enumerazione REGKIND](https://docs.microsoft.com/windows/win32/api/oleauto/ne-oleauto-regkind) che controlla la modalità di registrazione della libreria dei tipi. I valori possibili sono:  
  
- `REGKIND_DEFAULT`: Usare il comportamento di registrazione predefinito.  
  
- `REGKIND_REGISTER`: Registrare questa libreria di tipi.  
  
- `REGKIND_NONE`: Non registrare questa libreria di tipi.  
  
 `pTlbResolver`  
 in Puntatore all'implementazione dell' [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).  
  
 `pptlib`  
 out Riferimento alla libreria dei tipi che viene caricata.  
  
## <a name="return-value"></a>Valore restituito  
 Uno dei valori HRESULT elencati nella tabella seguente.  
  
|Valore restituito|Significato|  
|------------------|-------------|  
|`S_OK`|Operazione completata.|  
|`E_OUTOFMEMORY`|Memoria insufficiente.|  
|`E_POINTER`|Uno o più puntatori non sono validi.|  
|`E_INVALIDARG`|Uno o più argomenti non sono validi.|  
|`TYPE_E_IOERROR`|La funzione non è in grado di scrivere nel file.|  
|`TYPE_E_REGISTRYACCESS`|Non è stato possibile aprire il database di registrazione del sistema.|  
|`TYPE_E_INVALIDSTATE`|Non è stato possibile aprire la libreria dei tipi.|  
|`TYPE_E_CANTLOADLIBRARY`|Non è stato possibile caricare la libreria dei tipi o la DLL.|  
  
## <a name="remarks"></a>Note  
 [Tlbexp. exe (](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) utilità di esportazione della libreria dei tipi) `LoadTypeLibWithResolver` chiama la funzione durante il processo di conversione da assembly a libreria dei tipi.  
  
 Questa funzione carica la libreria dei tipi specificata con accesso minimo al registro di sistema. La funzione esamina quindi la libreria dei tipi per le librerie dei tipi a cui si fa riferimento internamente, ciascuna delle quali deve essere caricata e aggiunta alla libreria dei tipi padre.  
  
 Prima di poter caricare una libreria dei tipi a cui viene fatto riferimento, il percorso del file di riferimento deve essere risolto in un percorso file completo. Questa operazione viene eseguita tramite il [metodo ResolveTypeLib](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) fornito dall' [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), che viene `pTlbResolver` passata nel parametro.  
  
 Quando è noto il percorso completo del file della libreria dei tipi a cui si `LoadTypeLibWithResolver` fa riferimento, la funzione carica e aggiunge la libreria dei tipi a cui si fa riferimento nella libreria dei tipi padre, creando una libreria dei tipi master combinata.  
  
 Dopo che la funzione risolve e carica tutte le librerie dei tipi a cui si fa riferimento internamente, restituisce un riferimento alla libreria dei tipi `pptlib` risolta master nel parametro.  
  
 La `LoadTypeLibWithResolver` funzione viene in genere chiamata da [Tlbexp. exe (utilità di esportazione della libreria dei tipi)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), che fornisce un'implementazione dell' `pTlbResolver` [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) interna nel parametro.  
  
 Se si chiama `LoadTypeLibWithResolver` direttamente, è necessario fornire un'implementazione dell' [interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) personalizzata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** TlbRef. h  
  
 **Libreria** TlbRef.lib  
  
 **Versione .NET Framework:** 3,5, 3,0, 2,0  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di supporto Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [LoadTypeLibEx (funzione)](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)

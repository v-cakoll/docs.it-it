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
ms.openlocfilehash: adbb5eca3b7ffa36d0c963d0dacc3b2afdb664d4
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935554"
---
# <a name="loadtypelibwithresolver-function"></a>Funzione LoadTypeLibWithResolver
Carica una libreria dei tipi e utilizza l' [interfaccia ITypeLibResolver](itypelibresolver-interface.md) fornita per risolvere le librerie dei tipi a cui si fa riferimento internamente.  
  
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
 in Flag di [enumerazione REGKIND](/windows/win32/api/oleauto/ne-oleauto-regkind) che controlla la modalità di registrazione della libreria dei tipi. I valori possibili sono:  
  
- `REGKIND_DEFAULT`: usare il comportamento di registrazione predefinito.  
  
- `REGKIND_REGISTER`: registrare questa libreria di tipi.  
  
- `REGKIND_NONE`: non registrare questa libreria di tipi.  
  
 `pTlbResolver`  
 in Puntatore all'implementazione dell' [interfaccia ITypeLibResolver](itypelibresolver-interface.md).  
  
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
 [Tlbexp. exe (utilità di esportazione della libreria dei tipi)](../../tools/tlbexp-exe-type-library-exporter.md) chiama la funzione `LoadTypeLibWithResolver` durante il processo di conversione da assembly a libreria dei tipi.  
  
 Questa funzione carica la libreria dei tipi specificata con accesso minimo al registro di sistema. La funzione esamina quindi la libreria dei tipi per le librerie dei tipi a cui si fa riferimento internamente, ciascuna delle quali deve essere caricata e aggiunta alla libreria dei tipi padre.  
  
 Prima di poter caricare una libreria dei tipi a cui viene fatto riferimento, il percorso del file di riferimento deve essere risolto in un percorso file completo. Questa operazione viene eseguita tramite il [metodo ResolveTypeLib](resolvetypelib-method.md) fornito dall' [interfaccia ITypeLibResolver](itypelibresolver-interface.md), che viene passata nel parametro `pTlbResolver`.  
  
 Quando è noto il percorso completo del file della libreria dei tipi a cui si fa riferimento, la funzione `LoadTypeLibWithResolver` carica e aggiunge la libreria dei tipi a cui si fa riferimento nella libreria dei tipi padre, creando una libreria dei tipi master combinata.  
  
 Dopo che la funzione risolve e carica tutte le librerie dei tipi a cui si fa riferimento internamente, restituisce un riferimento alla libreria dei tipi risolta master nel parametro `pptlib`.  
  
 La funzione `LoadTypeLibWithResolver` viene in genere chiamata da [Tlbexp. exe (utilità di esportazione della libreria dei tipi)](../../tools/tlbexp-exe-type-library-exporter.md), che fornisce la propria implementazione dell' [interfaccia ITypeLibResolver](itypelibresolver-interface.md) interna nel parametro `pTlbResolver`.  
  
 Se si chiama direttamente `LoadTypeLibWithResolver`, è necessario fornire un'implementazione dell' [interfaccia ITypeLibResolver](itypelibresolver-interface.md) personalizzata.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** TlbRef. h  
  
 **Libreria:** TlbRef. lib  
  
 **Versione .NET Framework:** 3,5, 3,0, 2,0  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di supporto Tlbexp](index.md)
- [LoadTypeLibEx (funzione)](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)

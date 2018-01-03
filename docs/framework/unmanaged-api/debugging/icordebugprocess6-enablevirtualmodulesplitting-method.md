---
title: Metodo ICorDebugProcess6::EnableVirtualModuleSplitting
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34a2c2571ba7f3560d861d0a5271cc3a955253a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a>Metodo ICorDebugProcess6::EnableVirtualModuleSplitting
Abilita o disabilita la suddivisione dei moduli virtuali.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `enableSplitting`  
 `true` per abilitare la suddivisione dei moduli virtuali; `false` per disabilitarla.  
  
## <a name="remarks"></a>Note  
 Le cause di suddivisione dei moduli virtuali [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) per riconoscere i moduli uniti durante la compilazione processo e li presentano come gruppo di moduli separati invece di un unico grande modulo. In questo modo viene modificato il comportamento di vari [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) metodi descritti di seguito.  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
 In qualsiasi momento è possibile chiamare questo metodo e modificare il valore di `enableSplitting`. Non comporta modifiche funzionali con state in un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) oggetto, oltre alla modifica il comportamento dei metodi elencati nel [suddivisione dei moduli virtuali e le API di debug non gestite](#APIs) sezione al momento che vengono chiamati. L'uso dei moduli virtuali ha effetti negativi sulle prestazioni quando si chiamano questi metodi. Inoltre, la memorizzazione nella cache significativo dei metadati virtualizzati potrebbe essere necessario per implementare correttamente la [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) API e queste cache potrebbero essere mantenute anche dopo la suddivisione dei moduli virtuali è stata disattivata.  
  
## <a name="terminology"></a>Terminologia  
 Nella descrizione della suddivisione dei moduli virtuali vengono usati i seguenti termini:  
  
 moduli del contenitore o contenitori  
 I moduli aggregati.  
  
 moduli secondari o moduli virtuali  
 I moduli trovati in un contenitore.  
  
 moduli normali  
 I moduli non uniti durante la compilazione. Non corrispondono né ai moduli del contenitore né ai moduli secondari.  
  
 Entrambi i moduli del contenitore e i moduli secondari sono rappresentati da oggetti dell'interfaccia ICorDebugModule. Tuttavia, il comportamento dell'interfaccia è leggermente diverso in ogni caso, come il \<x-ref alla sezione > sezione viene descritto.  
  
## <a name="modules-and-assemblies"></a>Moduli e assembly  
 Gli assembly a più moduli non sono supportati per gli scenari di unione degli assembly, quindi esiste una relazione uno a uno tra un modulo e un assembly. Ogni oggetto ICorDebugModule, indipendentemente dal fatto che rappresenti un modulo del contenitore o un modulo secondario, è un oggetto ICorDebugAssembly corrispondente. Il [ICorDebugModule:: GetAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) metodo converte dal modulo all'assembly. Per eseguire il mapping in altra direzione, la [ICorDebugAssembly:: EnumerateModules](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md) metodo enumera solo 1 modulo. In questo caso l'assembly e il modulo formano una coppia strettamente collegata, quindi i termini assembly e modulo sono quasi del tutto intercambiabili.  
  
## <a name="behavioral-differences"></a>Differenze di comportamento  
 I moduli del contenitore hanno i seguenti comportamenti e caratteristiche:  
  
-   I metadati relativi a tutti i moduli secondari costitutivi sono uniti insieme.  
  
-   I nomi del tipo possono essere alterati.  
  
-   Il [ICorDebugModule:: GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) metodo restituisce il percorso a un modulo su disco.  
  
-   Il [ICorDebugModule:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) metodo restituisce la dimensione dell'immagine specificata.  
  
-   Il metodo ICorDebugAssembly3.EnumerateContainedAssemblies elenca i moduli secondari.  
  
-   Il metodo ICorDebugAssembly3.GetContainerAssembly restituisce `S_FALSE`.  
  
 I moduli secondari hanno i seguenti comportamenti e caratteristiche:  
  
-   Hanno un set di metadati limitato che corrisponde solo all'assembly originale unito.  
  
-   I nomi dei metadati non possono essere alterati.  
  
-   I token dei metadati solitamente non corrispondono ai token nell'assembly originale precedente al merge durante il processo di compilazione.  
  
-   Il [ICorDebugModule:: GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) metodo restituisce il nome dell'assembly, non un percorso file.  
  
-   Il [ICorDebugModule:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) metodo restituisce le dimensioni dell'immagine non unita originale.  
  
-   Il metodo ICorDebugModule3.EnumerateContainedAssemblies restituisce `S_FALSE`.  
  
-   Il metodo ICorDebugAssembly3.GetContainerAssembly restituisce il modulo contenitore.  
  
## <a name="interfaces-retrieved-from-modules"></a>Interfacce recuperate dai moduli  
 Dai moduli è possibile creare o recuperare diverse interfacce, tra cui:  
  
-   Un oggetto ICorDebugClass, che viene restituito dal [ICorDebugModule:: GetClassFromToken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md) metodo.  
  
-   Un oggetto ICorDebugAssembly, che viene restituito dal [ICorDebugModule:: GetAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) metodo.  
  
 Questi oggetti vengono sempre memorizzati nella cache da [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md), e hanno la stessa identità puntatore indipendentemente dal fatto che sono stati creati o il modulo del contenitore o un modulo secondario in una query. Il modulo secondario fornisce una visualizzazione filtrata di questi oggetti nella cache, non una cache separata con delle proprie copie.  
  
<a name="APIs"></a>   
## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a>Suddivisione dei moduli virtuali e API di debug non gestite  
 La tabella seguente illustra in che modo la suddivisione dei moduli virtuali influisce sul comportamento degli altri metodi nell'API di debug non gestita.  
  
|Metodo|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[ICorDebugFunction:: GetModule](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|Restituisce il modulo secondario in cui questa funzione è stata definita in origine|Restituisce il modulo del contenitore a cui questa funzione è stata unita|  
|[ICorDebugClass:: GetModule](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|Restituisce il modulo secondario in cui questa classe è stata definita in origine.|Restituisce il modulo del contenitore a cui questa classe è stata unita.|  
|ICorDebugModuleDebugEvent::GetModule|Restituisce il modulo del contenitore caricato. I moduli secondari non vengono associati a eventi di caricamento a prescindere da questa impostazione.|Restituisce il modulo del contenitore caricato.|  
|[ICorDebugAppDomain:: EnumerateAssemblies](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|Restituisce un elenco di assembly secondari e normali. Non sono inclusi assembly del contenitore. **Nota:** se mancano i simboli in qualsiasi assembly del contenitore, nessuno dei relativi assembly secondari saranno enumerati. Se mancano i simboli in qualsiasi assembly normale, l'enumerazione potrebbe essere eseguita.|Restituisce un elenco di assembly del contenitore e normali; non sono inclusi assembly secondari. **Nota:** se mancano i simboli in qualsiasi assembly normale, è possibile o potrebbe non essere enumerato.|  
|[ICorDebugCode:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md) (quando si fa riferimento solo al codice IL)|Restituisce IL, valido in un'immagine di assembly pre-merge. In particolare, quando i tipi a cui si fa riferimento non sono definiti nel modulo virtuale che contiene IL, gli eventuali token di metadati inline corrispondono correttamente a TypeRef o MemberRef. I token TypeRef o MemberRef possono essere cercati [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) oggetto per l'oggetto ICorDebugModule virtuale corrispondente.|Restituisce IL nell'immagine di assembly post-merge.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugProcess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

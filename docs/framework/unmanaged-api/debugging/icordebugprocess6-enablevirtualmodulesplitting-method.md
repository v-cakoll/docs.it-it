---
title: Metodo ICorDebugProcess6::EnableVirtualModuleSplitting
ms.date: 03/30/2017
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
ms.openlocfilehash: 8ad15d11ce81323b30434b3db98259a74a198f29
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178564"
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a>Metodo ICorDebugProcess6::EnableVirtualModuleSplitting
Abilita o disabilita la suddivisione dei moduli virtuali.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `enableSplitting`  
 `true` per abilitare la suddivisione dei moduli virtuali; `false` per disabilitarla.  
  
## <a name="remarks"></a>Osservazioni  
 La suddivisione del modulo virtuale fa in modo che [ICorDebug](icordebug-interface.md) riconosca i moduli Uniti durante il processo di compilazione e li presenti come un gruppo di moduli separati anziché un singolo modulo di grandi dimensioni. Questa operazione modifica il comportamento di vari metodi [ICorDebug](icordebug-interface.md) descritti di seguito.  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
 In qualsiasi momento è possibile chiamare questo metodo e modificare il valore di `enableSplitting`. Non provoca modifiche funzionali con stato in un oggetto [ICorDebug](icordebug-interface.md) , oltre alla modifica del comportamento dei metodi elencati nella [suddivisione del modulo virtuale e delle API di debug non gestite](#APIs) al momento della chiamata. L'uso dei moduli virtuali ha effetti negativi sulle prestazioni quando si chiamano questi metodi. Inoltre, la memorizzazione nella cache in memoria significativa dei metadati virtualizzati potrebbe essere necessaria per implementare correttamente le API [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) e tali cache possono essere mantenute anche dopo che la suddivisione del modulo virtuale è stata disattivata.  
  
## <a name="terminology"></a>Terminologia  
 Nella descrizione della suddivisione dei moduli virtuali vengono usati i seguenti termini:  
  
 moduli del contenitore o contenitori  
 I moduli aggregati.  
  
 moduli secondari o moduli virtuali  
 I moduli trovati in un contenitore.  
  
 moduli normali  
 I moduli non uniti durante la compilazione. Non corrispondono né ai moduli del contenitore né ai moduli secondari.  
  
 I moduli del contenitore e i moduli secondari sono rappresentati dagli oggetti dell'interfaccia ICorDebugModule. Tuttavia, il comportamento dell'interfaccia è leggermente diverso in ogni caso, come descritto nella \<sezione> della sezione x-ref a.  
  
## <a name="modules-and-assemblies"></a>Moduli e assembly  
 Gli assembly a più moduli non sono supportati per gli scenari di unione degli assembly, quindi esiste una relazione uno a uno tra un modulo e un assembly. Ogni oggetto ICorDebugModule, a prescindere che rappresenti un modulo del contenitore o un modulo secondario, ha un oggetto corrispondente ICorDebugAssembly. Il metodo [ICorDebugModule:: GetAssembly](icordebugmodule-getassembly-method.md) esegue la conversione dal modulo all'assembly. Per eseguire il mapping nell'altra direzione, il metodo [ICorDebugAssembly:: EnumerateModules](icordebugassembly-enumeratemodules-method.md) enumera solo 1 modulo. In questo caso l'assembly e il modulo formano una coppia strettamente collegata, quindi i termini assembly e modulo sono quasi del tutto intercambiabili.  
  
## <a name="behavioral-differences"></a>Differenze di comportamento  
 I moduli del contenitore hanno i seguenti comportamenti e caratteristiche:  
  
- I metadati relativi a tutti i moduli secondari costitutivi sono uniti insieme.  
  
- I nomi del tipo possono essere alterati.  
  
- Il metodo [ICorDebugModule:: GetName](icordebugmodule-getname-method.md) restituisce il percorso di un modulo su disco.  
  
- Il metodo [ICorDebugModule:: GetSize](icordebugmodule-getsize-method.md) restituisce le dimensioni dell'immagine.  
  
- Il metodo ICorDebugAssembly3.EnumerateContainedAssemblies elenca i moduli secondari.  
  
- Il metodo ICorDebugAssembly3.GetContainerAssembly restituisce `S_FALSE`.  
  
 I moduli secondari hanno i seguenti comportamenti e caratteristiche:  
  
- Hanno un set di metadati limitato che corrisponde solo all'assembly originale unito.  
  
- I nomi dei metadati non possono essere alterati.  
  
- I token dei metadati solitamente non corrispondono ai token nell'assembly originale precedente al merge durante il processo di compilazione.  
  
- Il metodo [ICorDebugModule:: GetName](icordebugmodule-getname-method.md) restituisce il nome dell'assembly, non un percorso di file.  
  
- Il metodo [ICorDebugModule:: GetSize](icordebugmodule-getsize-method.md) restituisce le dimensioni originali dell'immagine non unita.  
  
- Il metodo ICorDebugModule3.EnumerateContainedAssemblies restituisce `S_FALSE`.  
  
- Il metodo ICorDebugAssembly3.GetContainerAssembly restituisce il modulo contenitore.  
  
## <a name="interfaces-retrieved-from-modules"></a>Interfacce recuperate dai moduli  
 Dai moduli è possibile creare o recuperare diverse interfacce, tra cui:  
  
- Oggetto ICorDebugClass, restituito dal metodo [ICorDebugModule:: GetClassFromToken](icordebugmodule-getclassfromtoken-method.md) .  
  
- Oggetto ICorDebugAssembly, restituito dal metodo [ICorDebugModule:: GetAssembly](icordebugmodule-getassembly-method.md) .  
  
 Questi oggetti vengono sempre memorizzati nella cache da [ICorDebug](icordebug-interface.md)e avranno la stessa identità del puntatore, indipendentemente dal fatto che siano stati creati o sottoposti a query dal modulo contenitore o da un modulo secondario. Il modulo secondario fornisce una visualizzazione filtrata di questi oggetti nella cache, non una cache separata con delle proprie copie.  
  
<a name="APIs"></a>
## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a>Suddivisione dei moduli virtuali e API di debug non gestite  
 La tabella seguente illustra in che modo la suddivisione dei moduli virtuali influisce sul comportamento degli altri metodi nell'API di debug non gestita.  
  
|Metodo|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[ICorDebugFunction::GetModule](icordebugfunction-getmodule-method.md)|Restituisce il modulo secondario in cui questa funzione è stata definita in origine|Restituisce il modulo del contenitore a cui questa funzione è stata unita|  
|[ICorDebugClass::GetModule](icordebugclass-getmodule-method.md)|Restituisce il modulo secondario in cui questa classe è stata definita in origine.|Restituisce il modulo del contenitore a cui questa classe è stata unita.|  
|ICorDebugModuleDebugEvent::GetModule|Restituisce il modulo del contenitore caricato. I moduli secondari non vengono associati a eventi di caricamento a prescindere da questa impostazione.|Restituisce il modulo del contenitore caricato.|  
|[ICorDebugAppDomain::EnumerateAssemblies](icordebugappdomain-enumerateassemblies-method.md)|Restituisce un elenco di assembly secondari e normali. Non sono inclusi assembly del contenitore. **Nota:**  Se nell'assembly del contenitore mancano i simboli, nessuno dei relativi assembly secondari verrà enumerato. Se mancano i simboli in qualsiasi assembly normale, l'enumerazione potrebbe essere eseguita.|Restituisce un elenco di assembly del contenitore e normali; non sono inclusi assembly secondari. **Nota:**  Se nell'assembly normale mancano i simboli, è possibile che venga enumerata o meno.|  
|[ICorDebugCode:: GetCode](icordebugcode-getcode-method.md) (quando si fa riferimento solo al codice il)|Restituisce IL, valido in un'immagine di assembly pre-merge. In particolare, quando i tipi a cui si fa riferimento non sono definiti nel modulo virtuale che contiene IL, gli eventuali token di metadati inline corrispondono correttamente a TypeRef o MemberRef. Questi token TypeRef o MemberRef possono essere cercati nell'oggetto [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) per l'oggetto ICorDebugModule virtuale corrispondente.|Restituisce IL nell'immagine di assembly post-unione.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia ICorDebugProcess6](icordebugprocess6-interface.md)
- [Interfacce di debug](debugging-interfaces.md)

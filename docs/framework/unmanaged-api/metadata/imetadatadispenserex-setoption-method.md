---
title: Metodo IMetaDataDispenserEx::SetOption
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.SetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::SetOption
helpviewer_keywords:
- IMetaDataDispenserEx::SetOption method [.NET Framework metadata]
- SetOption method [.NET Framework metadata]
ms.assetid: 9f1c7ccd-7fb2-41d8-aa00-24b823376527
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9869efee18549c3d0c8b9ee9ca27cf31c1ccf452
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050142"
---
# <a name="imetadatadispenserexsetoption-method"></a>Metodo IMetaDataDispenserEx::SetOption
Imposta l'opzione specificata in un determinato valore per l'ambito dei metadati corrente. L'opzione controlla la modalità di gestione delle chiamate all'ambito dei metadati corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetOption (  
    [in] REFGUID optionId,   
    [in] const VARIANT *pValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `optionId`  
 [in] Un puntatore a un GUID che specifica l'opzione da impostare.  
  
 `pValue`  
 [in] Il valore da usare per impostare l'opzione. Il tipo di questo valore deve essere una variante di tipo dell'opzione specificata.  
  
## <a name="remarks"></a>Note  
 La tabella seguente elenca i GUID disponibili che il `optionId` parametro può puntare a e i corrispondenti valori validi per il `pValue` parametro.  
  
|GUID|Descrizione|`pValue` Parametro|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|Consente di controllare quali elementi vengono controllati i duplicati. Ogni volta che si chiama un' [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) metodo che crea un nuovo elemento, è possibile chiedere al metodo per verificare se l'elemento esiste già nell'ambito corrente. Ad esempio, è possibile controllare l'esistenza della `mdMethodDef` degli elementi; in questo caso, quando si chiama [DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), verificherà che il metodo non esiste già nell'ambito corrente. Questo controllo Usa la chiave che identifica un metodo specifico: padre di tipo, nome e firma.|Deve essere una variante di tipo UI4 e deve contenere una combinazione dei valori del [CorCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) enumerazione.|  
|MetaDataRefToDefCheck|I controlli che fa riferimento a elementi vengono convertiti alle definizioni. Per impostazione predefinita, il motore dei metadati consente di ottimizzare il codice mediante la conversione di un elemento di cui si fa riferimento alla relativa definizione se l'elemento di riferimento viene effettivamente definita nell'ambito corrente.|Deve essere una variante di tipo UI4 e deve contenere una combinazione dei valori del [CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) enumerazione.|  
|MetaDataNotificationForTokenMovement|Determina quale token avvenuti durante un'unione di metadati generano i callback. Usare la [SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) metodo per stabilire le [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interfaccia.|Deve essere una variante di tipo UI4 e deve contenere una combinazione dei valori del [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) enumerazione.|  
|MetaDataSetENC|Controlla il comportamento di modifica e continuazione (ENC). Solo una modalità di comportamento può essere impostata in un momento.|Deve essere una variante di tipo UI4 e deve contenere un valore di [CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) enumerazione. Il valore non è una maschera di bit.|  
|MetaDataErrorIfEmitOutOfOrder|Controlla gli errori generati out-ordine generano callback. Emissione di metadati non in ordine non è un errore irreversibile. Tuttavia, se si generano metadati in un ordine in cui viene accettato dal motore di metadati, i metadati sono più compatto e pertanto possono eseguire la ricerca in modo più efficiente. Usare la `IMetaDataEmit::SetHandler` metodo per stabilire il [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) interfaccia.|Deve essere una variante di tipo UI4 e deve contenere una combinazione dei valori del [CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) enumerazione.|  
|MetaDataImportOption|Controlla quali tipi di elementi che sono stati eliminati durante un ENC vengono recuperati da un enumeratore.|Deve essere una variante di tipo UI4 e deve contenere una combinazione dei valori del [Enumerazione CorImportOptions](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) enumerazione.|  
|MetaDataThreadSafetyOptions|Controlla se il motore di metadati ottiene reader e writer blocchi, in modo da garantire la sicurezza dei thread. Per impostazione predefinita, il motore si presuppone che l'accesso a thread singolo dal chiamante, in modo che nessun blocco viene ottenuto. I client sono tenuti a mantenere la sincronizzazione dei thread appropriato quando si usa l'API dei metadati.|Deve essere una variante di tipo UI4 e deve contenere un valore di [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) enumerazione. Il valore non è una maschera di bit.|  
|MetaDataGenerateTCEAdapters|Controlla se l'utilità di importazione della libreria di tipi deve generare le schede di evento fortemente accoppiata (TCE crittografia) per i contenitori di punto di connessione COM.|Deve essere una variante di tipo BOOL. Se `pValue` è impostata su `true`, l'utilità di importazione della libreria di tipi genera gli adapter TCE crittografia.|  
|MetaDataTypeLibImportNamespace|Specifica uno spazio dei nomi non predefiniti per la libreria dei tipi da importare.|Deve essere un valore null o una variante di tipo BSTR. Se `pValue` è un valore null, lo spazio dei nomi corrente è impostato su null; in caso contrario, lo spazio dei nomi corrente viene impostato per la stringa contenuta nel tipo della variante BSTR.|  
|MetaDataLinkerOptions|Controlla se il linker deve generare un assembly o un file di modulo .NET Framework.|Deve essere una variante di tipo UI4 e deve contenere una combinazione dei valori del [CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) enumerazione.|  
|MetaDataRuntimeVersion|Specifica la versione di common language runtime rispetto a cui è stata compilata questa immagine. La versione viene archiviata sotto forma di stringa, ad esempio "v1.0.3705".|Deve essere un valore null, un valore VT_EMPTY o una variante di tipo BSTR. Se `pValue` è null, la versione del runtime è impostata su null. Se `pValue` è VT_EMPTY, la versione è impostata su un valore predefinito, che viene disegnato dalla versione di Mscorwks. dll all'interno del quale viene eseguito il codice di metadati. In caso contrario, la versione del runtime è impostata per la stringa contenuta nel tipo della variante BSTR.|  
|MetaDataMergerOptions|Specifica le opzioni per l'unione dei metadati.|Deve essere una variante di tipo UI4 e deve contenere una combinazione dei valori del `MergeFlags` enumerazione, che è descritti nel file corhdr. H.|  
|MetaDataPreserveLocalRefs|Disabilita l'ottimizzazione di riferimenti locali nelle definizioni.|Deve contenere una combinazione dei valori del [CorLocalRefPreservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) enumerazione.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Interfaccia IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)

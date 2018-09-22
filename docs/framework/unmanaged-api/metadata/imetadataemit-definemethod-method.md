---
title: Metodo IMetaDataEmit::DefineMethod
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2dbc6b5ffaa3a381bdd657059a682a3d12dc4cf1
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46584266"
---
# <a name="imetadataemitdefinemethod-method"></a>Metodo IMetaDataEmit::DefineMethod
Crea una definizione per un metodo o una funzione globale con la firma specificata e restituisce un token per tale definizione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineMethod (      
    [in]  mdTypeDef         td,   
    [in]  LPCWSTR           szName,   
    [in]  DWORD             dwMethodFlags,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [in]  ULONG             ulCodeRVA,   
    [in]  DWORD             dwImplFlags,   
    [out] mdMethodDef      *pmd  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `td`  
 [in] Il `mdTypedef` token della classe padre o dell'interfaccia padre del metodo. Impostare `td` a `mdTokenNil`, se si sta definendo una funzione globale.  
  
 `szName`  
 [in] Il nome del membro in formato Unicode.  
  
 `dwMethodFlags`  
 [in] Valore di [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumerazione che specifica gli attributi del metodo o funzione globale.  
  
 `pvSigBlob`  
 [in] La firma del metodo. La firma viene reso persistente come fornito. Se è necessario specificare informazioni aggiuntive per tutti i parametri, usare il [SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) (metodo).  
  
 `cbSigBlob`  
 [in] Il numero di byte in `pvSigBlob`.  
  
 `ulCodeRVA`  
 [in] L'indirizzo del codice.  
  
 `dwImplFlags`  
 [in] Valore di [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumerazione che specifica le funzionalità di implementazione del metodo.  
  
 `pmd`  
 [out] Il token di membro.  
  
## <a name="remarks"></a>Note  
 L'API dei metadati garantisce che vengano mantenuti metodi nello stesso ordine in cui il chiamante vengono generati per una determinata classe di inclusione o l'interfaccia, specificata nel `td` parametro.  
  
 Informazioni aggiuntive sull'uso di `DefineMethod` e le impostazioni dei parametri specifico sono indicati di seguito.  
  
## <a name="slots-in-the-v-table"></a>Slot nella V-table  
 Il runtime Usa le definizioni di metodo per configurare gli slot di v-table. Nel caso in cui devono essere ignorate, ad esempio uno o più slot per mantenere la parità con un layout di interfaccia COM, un metodo fittizio è definito in modo da occupare lo slot o slot nella tabella v. impostare il `dwMethodFlags` per il `mdRTSpecialName` pari al [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumerazione e specificare il nome come:  
  
 VtblGap\<*SequenceNumber*>\<\_*NumeroDiSlot*>
  
 in cui *SequenceNumber* è il numero di sequenza del metodo e *NumeroDiSlot* è il numero di slot da ignorare nella v-table. Se *NumeroDiSlot* viene omesso, viene usato il valore 1. Questi metodi fittizi non richiamabili da codice gestito o non gestito e qualsiasi tentativo di chiamarle da codice gestito o non gestito, genera un'eccezione. Il loro unico scopo è a occupare spazio nella v-table generata dal runtime per l'integrazione con COM.  
  
## <a name="duplicate-methods"></a>Metodi di duplicati  
 Non è necessario definire metodi duplicati. Vale a dire, non chiamare `DefineMethod` con un set duplicato di valori nel `td`, `wzName`, e `pvSig` parametri. (Questi tre parametri insieme definiscono in modo univoco il metodo.). Tuttavia, è possibile utilizzare un duplicata condizione che, per una delle definizioni di metodo, è stato impostato il `mdPrivateScope` bit nel `dwMethodFlags` parametro. (Il `mdPrivateScope` bit significa che il compilatore non genererà un riferimento a questa definizione di metodo.)  
  
## <a name="method-implementation-information"></a>Informazioni sulla modalità di implementazione  
 Informazioni sull'implementazione del metodo spesso non sono noto al momento che il metodo viene dichiarato. Pertanto, non è necessario passare i valori nel `ulCodeRVA` e `dwImplFlags` i parametri quando si chiama `DefineMethod`. I valori possono essere specificati in un secondo momento attraverso [SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) oppure [SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), nel modo appropriato.  
  
 In alcune situazioni, ad esempio la chiamata di piattaforma (PInvoke) o scenari di interoperabilità COM, non verrà fornito il corpo del metodo, e `ulCodeRVA` deve essere impostato su zero. In questi casi, il metodo non deve essere contrassegnato come abstract, perché il runtime consente di trovare l'implementazione.  
  
## <a name="defining-a-method-for-pinvoke"></a>Definizione di un metodo per PInvoke  
 Per ogni funzione non gestita essere chiamate tramite PInvoke, è necessario definire un metodo gestito che rappresenta la funzione non gestita di destinazione. Per definire il metodo gestito, usare `DefineMethod` con alcuni dei parametri impostati su determinati valori, a seconda del modo in cui viene usato PInvoke:  
  
-   True PInvoke: comporta la chiamata di un metodo non gestito esterno che si trova in una DLL non gestita.  
  
-   PInvoke locale - comporta una chiamata di un metodo non gestito nativo incorporato nel modulo gestito corrente.  
  
 Le impostazioni dei parametri sono fornite nella tabella seguente.  
  
|Parametro|Valori per true PInvoke|Valori per locale PInvoke|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Impostare `mdStatic`; Cancella `mdSynchronized` e `mdAbstract`.|  
|`pvSigBlob`|Una firma del metodo di common language runtime (CLR) valido con i parametri validi di tipi gestiti.|Una firma di metodo CLR valida con i parametri validi di tipi gestiti.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Impostare `miCil` e `miManaged`.|Impostare `miNative` e `miUnmanaged`.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

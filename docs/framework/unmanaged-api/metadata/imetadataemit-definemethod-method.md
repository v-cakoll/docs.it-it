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
ms.openlocfilehash: 514f227e3c0c385f61090079d2f5214dac9b3924
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004530"
---
# <a name="imetadataemitdefinemethod-method"></a>Metodo IMetaDataEmit::DefineMethod
Crea una definizione per un metodo o una funzione globale con la firma specificata e restituisce un token a tale definizione del metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="parameters"></a>Parametri  
 `td`  
 in `mdTypedef`Token della classe padre o dell'interfaccia padre del metodo. Impostare `td` su `mdTokenNil` se si definisce una funzione globale.  
  
 `szName`  
 in Nome del membro in Unicode.  
  
 `dwMethodFlags`  
 in Valore dell'enumerazione [CorMethodAttr](cormethodattr-enumeration.md) che specifica gli attributi del metodo o della funzione globale.  
  
 `pvSigBlob`  
 in Firma del metodo. La firma viene salvata in modo permanente come fornito. Se è necessario specificare informazioni aggiuntive per qualsiasi parametro, usare il metodo [IMetaDataEmit:: SetParamProps](imetadataemit-setparamprops-method.md) .  
  
 `cbSigBlob`  
 in Numero di byte in `pvSigBlob` .  
  
 `ulCodeRVA`  
 in Indirizzo del codice.  
  
 `dwImplFlags`  
 in Valore dell'enumerazione [CorMethodImpl](cormethodimpl-enumeration.md) che specifica le funzionalità di implementazione del metodo.  
  
 `pmd`  
 out Token del membro.  
  
## <a name="remarks"></a>Commenti  
 L'API dei metadati garantisce la conservazione dei metodi nello stesso ordine in cui il chiamante li emette per una classe o un'interfaccia contenitore specificata, specificata nel `td` parametro.  
  
 Di seguito sono riportate informazioni aggiuntive sull'utilizzo di `DefineMethod` e delle impostazioni dei parametri particolari.  
  
## <a name="slots-in-the-v-table"></a>Slot nella tabella V  
 Il runtime usa definizioni di metodo per configurare gli slot della tabella v. Nel caso in cui uno o più slot debbano essere ignorati, ad esempio per mantenere la parità con un layout dell'interfaccia COM, viene definito un metodo fittizio per occupare lo slot o gli slot nella tabella v. impostare sul `dwMethodFlags` `mdRTSpecialName` valore dell'enumerazione [CorMethodAttr](cormethodattr-enumeration.md) e specificare il nome come:  
  
 _VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*>
  
 dove *SequenceNumber* è il numero di sequenza del metodo e *NumeroDiSlot* è il numero di slot da ignorare nella tabella v. Se *NumeroDiSlot* viene omesso, viene utilizzato 1. Questi metodi fittizi non possono essere richiamati dal codice gestito o non gestito e qualsiasi tentativo di chiamarli, dal codice gestito o non gestito, genera un'eccezione. Il loro unico scopo è quello di assumere spazio nella tabella v generata dal runtime per l'integrazione COM.  
  
## <a name="duplicate-methods"></a>Metodi duplicati  
 Non definire metodi duplicati. In altre parole, non è necessario chiamare `DefineMethod` con un set di valori duplicati `td` nei `wzName` parametri, e `pvSig` . Questi tre parametri definiscono insieme in modo univoco il metodo. Tuttavia, è possibile usare una tripla duplicata purché, per una delle definizioni del metodo, si imposti il `mdPrivateScope` bit nel `dwMethodFlags` parametro. Il `mdPrivateScope` bit indica che il compilatore non genererà un riferimento a questa definizione del metodo.  
  
## <a name="method-implementation-information"></a>Informazioni sull'implementazione del metodo  
 Le informazioni sull'implementazione del metodo spesso non sono note nel momento in cui viene dichiarato il metodo. Non è quindi necessario passare i valori nei `ulCodeRVA` parametri e quando si `dwImplFlags` chiama `DefineMethod` . I valori possono essere specificati in un secondo momento tramite [IMetaDataEmit:: SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) o [IMetaDataEmit:: SetRVA](imetadataemit-setrva-method.md), a seconda dei casi.  
  
 In alcune situazioni, ad esempio gli scenari di chiamata della piattaforma (PInvoke) o di interoperabilità COM, il corpo del metodo non verrà fornito e `ulCodeRVA` deve essere impostato su zero. In queste situazioni, il metodo non deve essere contrassegnato come abstract, perché il runtime individuerà l'implementazione.  
  
## <a name="defining-a-method-for-pinvoke"></a>Definizione di un metodo per PInvoke  
 Per ogni funzione non gestita da chiamare tramite PInvoke, è necessario definire un metodo gestito che rappresenti la funzione non gestita di destinazione. Per definire il metodo gestito, utilizzare `DefineMethod` con alcuni parametri impostati su determinati valori, a seconda della modalità di utilizzo di PInvoke:  
  
- True PInvoke: implica la chiamata di un metodo esterno non gestito che risiede in una DLL non gestita.  
  
- PInvoke locale: implica la chiamata di un metodo non gestito nativo incorporato nel modulo gestito corrente.  
  
 Le impostazioni dei parametri sono fornite nella tabella seguente.  
  
|Parametro|Valori per true PInvoke|Valori per PInvoke locale|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Set `mdStatic` ; Clear `mdSynchronized` e `mdAbstract` .|  
|`pvSigBlob`|Firma di un metodo di Common Language Runtime (CLR) valida con parametri che sono tipi gestiti validi.|Firma di un metodo CLR valida con parametri che sono tipi gestiti validi.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Impostare `miCil` e `miManaged`.|Impostare `miNative` e `miUnmanaged`.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)

---
title: Metodo IMetaDataImport::GetInterfaceImplProps
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
ms.openlocfilehash: 4b8ddf7fec12d175f030c0ea0ed982c6fb334aee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175382"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a>Metodo IMetaDataImport::GetInterfaceImplProps
Ottiene un puntatore ai <xref:System.Type> token di metadati per il che implementa il metodo specificato e per l'interfaccia che dichiara tale metodo.
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `iiImpl`  
 [in] Token di metadati che rappresenta il metodo per cui restituire la classe e i token di interfaccia.  
  
 `pClass`  
 [fuori] Token di metadati che rappresenta la classe che implementa il metodo.  
  
 `ptkIface`  
 [fuori] Token di metadati che rappresenta l'interfaccia che definisce il metodo implementato.  

## <a name="remarks"></a>Osservazioni

 È possibile ottenere `iImpl` il valore per chiamando il [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) metodo.

 Si supponga, ad esempio, `mdTypeDef` che una classe abbia un valore token pari a 0x02000007 e che implementi tre interfacce i cui tipi dispongono di token:For example, suppose that a class has an token value of 0x02000007 and that it implements three interfaces whose types have tokens:

- 0x02000003 (TypeDef)
- 0x0100000A (TypeRef)
- 0x0200001C (TypeDef)

Concettualmente, queste informazioni vengono archiviate in una tabella di implementazione dell'interfaccia come segue:Conceptually, this information is stored into an interface implementation table as:

| Numero di riga | Token di classe | Token di interfaccia |
|------------|-------------|-----------------|
| 4          |             |                 |
| 5          | 02000007    | 02000003        |
| 6          | 02000007    | 0100000A        |
| 7          |             |                 |
| 8          | 02000007    | 0200001C        |

Ricordiamo che il token è un valore a 4 byte:Recall, the token is a 4-byte value:

- I 3 byte inferiori contengono il numero di riga o RID.
- Il byte superiore contiene il tipo di `mdtInterfaceImpl`token – 0x09 per .

`GetInterfaceImplProps`restituisce le informazioni contenute nella riga `iImpl` di cui si fornisce il token nell'argomento.
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

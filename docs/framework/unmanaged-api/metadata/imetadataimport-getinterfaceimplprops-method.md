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
ms.openlocfilehash: 1c9d9647084aa729817eeeb17ee3f5cd320c0d29
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491244"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a>Metodo IMetaDataImport::GetInterfaceImplProps
Ottiene un puntatore ai token di metadati per l'oggetto <xref:System.Type> che implementa il metodo specificato e per l'interfaccia che dichiara il metodo.
  
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
 in Token di metadati che rappresenta il metodo per restituire i token di interfaccia e di classe per.  
  
 `pClass`  
 out Token di metadati che rappresenta la classe che implementa il metodo.  
  
 `ptkIface`  
 out Token di metadati che rappresenta l'interfaccia che definisce il metodo implementato.  

## <a name="remarks"></a>Osservazioni

 Per ottenere il valore `iImpl` di, chiamare il metodo [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) .

 Si supponga, ad esempio, che una classe disponga `mdTypeDef` di un valore token di 0x02000007 e che implementi tre interfacce i cui tipi includono token:

- 0x02000003 (TypeDef)
- 0x0100000A (TypeRef)
- 0x0200001C (TypeDef)

Concettualmente, queste informazioni vengono archiviate in una tabella di implementazione dell'interfaccia come:

| Numero di riga | Token di classe | Token di interfaccia |
|------------|-------------|-----------------|
| 4          |             |                 |
| 5          | 02000007    | 02000003        |
| 6          | 02000007    | 0100000A        |
| 7          |             |                 |
| 8          | 02000007    | 0200001C        |

Si ricordi che il token è un valore a 4 byte:

- I 3 byte inferiori contengono il numero di riga o il RID.
- Il byte superiore include il tipo di token – 0x09 per `mdtInterfaceImpl` .

`GetInterfaceImplProps`Restituisce le informazioni contenute nella riga il cui token è stato fornito nell' `iImpl` argomento.
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)

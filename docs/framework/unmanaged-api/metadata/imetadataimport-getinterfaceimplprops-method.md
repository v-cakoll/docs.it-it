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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76e2ebbd47a5e36a722fce33ba67d7efb4db8675
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115934"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a>Metodo IMetaDataImport::GetInterfaceImplProps
Ottiene un puntatore al token di metadati per il <xref:System.Type> che implementa il metodo specificato e per l'interfaccia che dichiara tale metodo.
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `iiImpl`  
 [in] Il token di metadati che rappresenta il metodo per restituire i token di classe e l'interfaccia per.  
  
 `pClass`  
 [out] Il token di metadati che rappresenta la classe che implementa il metodo.  
  
 `ptkIface`  
 [out] Il token di metadati che rappresenta l'interfaccia che definisce il metodo implementato.  

## <a name="remarks"></a>Note

 Ottenere il valore per `iImpl` chiamando il [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) (metodo).
 
 Ad esempio, si supponga che una classe ha un `mdTypeDef` token valore 0x02000007 e l'implementazione di tre interfacce i cui tipi sono token: 

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

Tenere presente, il token è un valore a 4 byte:

- I 3 byte meno significativi contenere il numero di riga o RID.
- Il byte alto contiene il tipo di token – 0x09 per `mdtInterfaceImpl`.

`GetInterfaceImplProps` Restituisce le informazioni contenute nella riga il cui token è fornire la `iImpl` argomento. 
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

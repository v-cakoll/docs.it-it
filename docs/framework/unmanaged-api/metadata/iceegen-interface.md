---
title: Interfaccia ICeeGen
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fb081c48abf899b44da1c1351efa3f6036f1c8d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050207"
---
# <a name="iceegen-interface"></a>Interfaccia ICeeGen
Fornisce metodi per la compilazione dinamica del codice.  
  
 Questa interfaccia è obsoleta e non deve essere utilizzata.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|Obsoleta. Aggiunge un'istruzione. reloc alla base di codice.|  
|[Metodo AllocateMethodBuffer](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|Obsoleta. Crea un buffer della dimensione specificata per un metodo e ottiene l'indirizzo virtuale relativo del metodo.|  
|[Metodo ComputePointer](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|Obsoleta. Determina il buffer per la sezione di codice specificato.|  
|[Metodo EmitString](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|Obsoleta. Genera la stringa specificata nella codebase.|  
|[Metodo GenerateCeeFile](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|Obsoleta. Genera un file di base di codice contenente la base di codice attualmente caricata in `ICeeGen`.|  
|[Metodo GenerateCeeMemoryImage](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|Obsoleta. Genera un'immagine in memoria per la base di codice.|  
|[Metodo GetIlSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|Obsoleta. Ottiene la sezione di codice Microsoft intermediate language base fa riferimento l'handle specificato.|  
|[Metodo GetIMapTokenIface](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|Obsoleta. Ottiene l'interfaccia fa riferimento il token specificato.|  
|[Metodo GetMethodBuffer](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|Obsoleta. Ottiene un buffer di dimensione appropriata per il metodo in corrispondenza dell'indirizzo virtuale relativo specificato.|  
|[Metodo GetSectionBlock](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|Obsoleta. Ottiene un blocco di sezione del codice di base.|  
|[Metodo GetSectionCreate](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|Obsoleta. Genera l'errore e ottiene una sezione di codice usando il nome specificato e i valori di flag.|  
|[Metodo GetSectionDataLen](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|Obsoleta. Ottiene la lunghezza della sezione specificata.|  
|[Metodo GetString](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|Obsoleta. Ottiene la stringa archiviata all'indirizzo virtuale relativo specificato.|  
|[Metodo GetStringSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|Obsoleta. Ottiene una rappresentazione di stringa della sezione di codice fa riferimento l'handle specificato.|  
|[Metodo TruncateSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|Obsoleta. Tronca la sezione di codice specificato per la lunghezza specificata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

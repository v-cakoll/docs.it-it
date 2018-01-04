---
title: Interfaccia ICeeGen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen
helpviewer_keywords: ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73af58ac55fd22e5b4f19f715cb0b1a137a640a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
|[Metodo GenerateCeeFile](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|Obsoleta. Genera un file di base di codice che contiene il codice base attualmente caricato in `ICeeGen`.|  
|[Metodo GenerateCeeMemoryImage](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|Obsoleta. Genera un'immagine in memoria per la base di codice.|  
|[Metodo GetIlSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|Obsoleta. Ottiene la sezione di codice Microsoft intermediate language base a cui fa riferimento l'handle specificato.|  
|[Metodo GetIMapTokenIface](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|Obsoleta. Ottiene l'interfaccia a cui fa riferimento il token specificato.|  
|[Metodo GetMethodBuffer](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|Obsoleta. Ottiene un buffer di dimensioni appropriate per il metodo all'indirizzo virtuale relativo specificato.|  
|[Metodo GetSectionBlock](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|Obsoleta. Ottiene un blocco di sezione di base di codice.|  
|[Metodo GetSectionCreate](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|Obsoleta. Genera l'errore e ottiene una sezione di codice utilizzando il nome specificato e i valori di flag.|  
|[Metodo GetSectionDataLen](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|Obsoleta. Ottiene la lunghezza della sezione specificata.|  
|[Metodo GetString](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|Obsoleta. Ottiene la stringa archiviata nell'indirizzo virtuale relativo specificato.|  
|[Metodo GetStringSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|Obsoleta. Ottiene una rappresentazione di stringa della sezione di codice a cui fa riferimento l'handle specificato.|  
|[Metodo TruncateSection](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|Obsoleta. Tronca la sezione di codice specificati dalla lunghezza specificata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

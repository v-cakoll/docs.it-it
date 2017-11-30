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
ms.openlocfilehash: 8342c79dd8b7452599af8d9782b0fbec5f83e964
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iceegen-interface"></a>Interfaccia ICeeGen
Fornisce metodi per la compilazione dinamica del codice.  
  
 Questa interfaccia è obsoleta e non deve essere utilizzata.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[AddSectionReloc (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|Obsoleta. Aggiunge un'istruzione. reloc alla base di codice.|  
|[AllocateMethodBuffer (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|Obsoleta. Crea un buffer della dimensione specificata per un metodo e ottiene l'indirizzo virtuale relativo del metodo.|  
|[ComputePointer (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|Obsoleta. Determina il buffer per la sezione di codice specificato.|  
|[EmitString (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|Obsoleta. Genera la stringa specificata nella codebase.|  
|[GenerateCeeFile (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|Obsoleta. Genera un file di base di codice che contiene il codice base attualmente caricato in `ICeeGen`.|  
|[GenerateCeeMemoryImage (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|Obsoleta. Genera un'immagine in memoria per la base di codice.|  
|[GetIlSection (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|Obsoleta. Ottiene la sezione di codice Microsoft intermediate language base a cui fa riferimento l'handle specificato.|  
|[GetIMapTokenIface (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|Obsoleta. Ottiene l'interfaccia a cui fa riferimento il token specificato.|  
|[GetMethodBuffer (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|Obsoleta. Ottiene un buffer di dimensioni appropriate per il metodo all'indirizzo virtuale relativo specificato.|  
|[GetSectionBlock (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|Obsoleta. Ottiene un blocco di sezione di base di codice.|  
|[GetSectionCreate (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|Obsoleta. Genera l'errore e ottiene una sezione di codice utilizzando il nome specificato e i valori di flag.|  
|[GetSectionDataLen (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|Obsoleta. Ottiene la lunghezza della sezione specificata.|  
|[GetString (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|Obsoleta. Ottiene la stringa archiviata nell'indirizzo virtuale relativo specificato.|  
|[GetStringSection (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|Obsoleta. Ottiene una rappresentazione di stringa della sezione di codice a cui fa riferimento l'handle specificato.|  
|[TruncateSection (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|Obsoleta. Tronca la sezione di codice specificati dalla lunghezza specificata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

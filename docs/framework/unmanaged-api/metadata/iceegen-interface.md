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
ms.openlocfilehash: e6cf0aa6f731d0a417e1a2be0ca1d0f8c9299379
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008274"
---
# <a name="iceegen-interface"></a>Interfaccia ICeeGen
Fornisce metodi per la compilazione dinamica del codice.  
  
 Questa interfaccia è obsoleta e non deve essere utilizzata.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo AddSectionReloc](iceegen-addsectionreloc-method.md)|Obsoleto. Aggiunge un'istruzione. reloc alla codebase.|  
|[Metodo AllocateMethodBuffer](iceegen-allocatemethodbuffer-method.md)|Obsoleto. Crea un buffer con la dimensione specificata per un metodo e ottiene l'indirizzo virtuale relativo del metodo.|  
|[Metodo ComputePointer](iceegen-computepointer-method.md)|Obsoleto. Determina il buffer per la sezione di codice specificata.|  
|[Metodo EmitString](iceegen-emitstring-method.md)|Obsoleto. Genera la stringa specificata nella codebase.|  
|[Metodo GenerateCeeFile](iceegen-generateceefile-method.md)|Obsoleto. Genera un file di base del codice che contiene la codebase attualmente caricata in questo oggetto `ICeeGen` .|  
|[Metodo GenerateCeeMemoryImage](iceegen-generateceememoryimage-method.md)|Obsoleto. Genera un'immagine in memoria per la codebase.|  
|[Metodo GetIlSection](iceegen-getilsection-method.md)|Obsoleto. Ottiene la sezione della base di codice del linguaggio intermedio a cui fa riferimento l'handle specificato.|  
|[Metodo GetIMapTokenIface](iceegen-getimaptokeniface-method.md)|Obsoleto. Ottiene l'interfaccia a cui fa riferimento il token specificato.|  
|[Metodo GetMethodBuffer](iceegen-getmethodbuffer-method.md)|Obsoleto. Ottiene un buffer delle dimensioni appropriate per il metodo in corrispondenza dell'indirizzo virtuale relativo specificato.|  
|[Metodo GetSectionBlock](iceegen-getsectionblock-method.md)|Obsoleto. Ottiene un blocco di sezione della codebase.|  
|[Metodo GetSectionCreate](iceegen-getsectioncreate-method.md)|Obsoleto. Genera e ottiene una sezione di codice utilizzando il nome e i valori del flag specificati.|  
|[Metodo GetSectionDataLen](iceegen-getsectiondatalen-method.md)|Obsoleto. Ottiene la lunghezza della sezione specificata.|  
|[Metodo GetString](iceegen-getstring-method.md)|Obsoleto. Ottiene la stringa archiviata nell'indirizzo virtuale relativo specificato.|  
|[Metodo GetStringSection](iceegen-getstringsection-method.md)|Obsoleto. Ottiene una rappresentazione di stringa della sezione di codice a cui fa riferimento l'handle specificato.|  
|[Metodo TruncateSection](iceegen-truncatesection-method.md)|Obsoleto. Tronca la sezione di codice specificata in base alla lunghezza specificata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di metadati](metadata-interfaces.md)

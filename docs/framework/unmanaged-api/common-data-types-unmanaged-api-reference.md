---
title: Tipi di dati comuni (riferimenti alle API non gestite)
ms.date: 03/30/2017
ms.assetid: e4ab2c4c-9433-4eba-9e9a-096de406cafb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c359c9b14452e82b7fd2425409b373ead430d3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="common-data-types-unmanaged-api-reference"></a>Tipi di dati comuni (riferimenti alle API non gestite)
In questo argomento sono elencati i tipi di dati semplici usati dalle API non gestite per .NET Framework e definiti dalle istruzioni `typedef` di C/C++. Questi tipi di dati sono in genere alias di tipi di dati primitivi di C/C++. I valori di questi tipi di dati normalmente sono opachi, cioè vengono restituiti da una determinata funzione o metodo in modo da poter essere passati ad altre funzioni o metodi senza modifiche.  
  
|Tipo di dati|Definizione|Definito in|Descrizione|  
|---------------|----------------|----------------|-----------------|  
|AppDomainID|`typedef UINT_PTR AppDomainID;`|corprof.h|Identificatore di un dominio di applicazione.|  
|AssemblyID|`typedef UINT_PTR AssemblyID;`|corprof.h|Identificatore di un assembly.|  
|ClassID|`typedef UINT_PTR ClassID;`|corprof.h|Identificatore di una classe gestita.|  
|CONNID|`typedef DWORD CONNID;`|cordebug.h, mscoree.h|Identificatore della connessione per un thread connesso a un'istanza di Microsoft SQL Server.|  
|ContextID|`typedef UINT_PTR ContextID;`|corprof.h|Identificatore del contesto associato a un thread gestito specifico.|  
|COR_PRF_ELT_INFO|`typedef UINT_PTR COR_PRF_ELT_INFO;`|corprof.h|Handle opaco che rappresenta le informazioni su un determinato stack frame.|  
|COR_PRF_FRAME_INFO|`typedef UINT_PTR COR_PRF_FRAME_INFO;`|corprof.h|Handle opaco che punta a uno stack frame. È valido solo durante il callback a cui viene passato.|  
|CORDB_ADDRESS|`typedef ULONG64 CORDB_ADDRESS;`|cordebug.h|Indirizzo in memoria.|  
|CORDB_CONTINUE_STATUS|`typedef DWORD CORDB_CONTINUE_STATUS;`|cordebug.h|Stato di continuazione.|  
|CORDB_REGISTER|`typedef ULONG64 CORDB_REGISTER;`|cordebug.h|Valore di un registro della CPU.|  
|FunctionID|`typedef UINT_PTR FunctionID;`|corprof.h|Identificatore di una funzione o di un metodo.|  
|GCHandleID|`typedef UINT_PTR GCHandleID;`|corprof.h|Handle di Garbage Collection.|  
|mdToken|`typedef UINT32 mdToken;`|corprof.h|Token di metadati (una riga in una tabella di metadati).|  
|ModuleID|`typedef UINT_PTR ModuleID;`|corprof.h|Identificatore di un modulo di assembly.|  
|ObjectID|`typedef UINT_PTR ObjectID;`|corprof.h|Identificatore di un oggetto.|  
|ProcessID|`typedef UINT_PTR ProcessID;`|corprof.h|Identificatore di un processo gestito.|  
|ReJITID|`typedef UINT_PTR ReJITID;`|corprof.h|Identificatore di una funzione Just-In-Time.|  
|TASKID|`typedef UINT64 TASKID;`|cordebug.h, mscoree.h|L'identificatore di un [ICLRTask](../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza.|  
|ThreadID|`typedef UINT_PTR ThreadID;`|corprof.h|Identificatore di un thread gestito.|  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti alle API non gestite](../../../docs/framework/unmanaged-api/index.md)

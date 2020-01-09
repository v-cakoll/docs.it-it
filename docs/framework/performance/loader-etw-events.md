---
title: Eventi ETW del caricatore
ms.date: 03/30/2017
helpviewer_keywords:
- loader events [.NET Framework]
- ETW, loader events (CLR)
ms.assetid: cb403cc6-56f8-4609-b467-cdfa09f07909
ms.openlocfilehash: 73665915a70225c2b1da47c7b60347b089564884
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716034"
---
# <a name="loader-etw-events"></a>Eventi ETW del caricatore
Questi eventi raccolgono le informazioni relative al caricamento e allo scaricamento di domini applicazioni, assembly e moduli.  
  
 Tutti gli eventi del caricatore vengono generati con la parola chiave `LoaderKeyword` (0x8). Gli eventi `DCStart` e `DCEnd` vengono generati in `LoaderRundownKeyword` (0x8) con `StartRundown`/`EndRundown` abilitato. Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).  

## <a name="application-domain-events"></a>Eventi del dominio applicazioni
 La tabella seguente illustra la parola chiave e il livello  
  
|Parola chiave per la generazione dell'evento|Event|Livello|  
|-----------------------------------|-----------|-----------|  
|`LoaderKeyword` (0x8)|`AppDomainLoad_V1` e `AppDomainUnLoad_V1`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `StartRundownKeyword`|`AppDomainDCStart_V1`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `EndRundownKeyword`|`AppDomainDCEnd_V1`|Informativo (4)|  
  
 La tabella seguente mostra le informazioni sull'evento.  
  
|Event|ID evento|Descrizione|  
|-----------|--------------|-----------------|  
|`AppDomainLoad_V1` (registrato per tutti i domini applicazioni)|156|Generato se un dominio applicazioni viene creato nel corso di un processo.|  
|`AppDomainUnLoad_V1`|157|Generato se un dominio applicazioni viene eliminato nel corso di un processo.|  
|`AppDomainDCStart_V1`|157|Enumera i domini applicazioni durante un rundown di avvio.|  
|`AppDomainDCEnd_V1`|158|Enumera i domini applicazioni durante un rundown di fine.|  
  
 La tabella seguente mostra i dati dell'evento.  
  
|Nome del campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|AppDomainID|win:UInt64|Identificatore univoco per un dominio applicazioni.|  
|AppDomainFlags|win:UInt32|0x1: dominio predefinito.<br /><br /> 0x2: eseguibile.<br /><br /> 0x4: dominio applicazioni, bit 28-31: condivisione dei criteri di questo dominio.<br /><br /> 0: dominio condiviso.|  
|AppDomainName|win:UnicodeString|Nome descrittivo del dominio applicazioni. Può cambiare nel corso del processo.|  
|AppDomainIndex|win:UInt32|Indice di questo dominio applicazioni.|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|  

## <a name="clr-loader-assembly-events"></a>Eventi assembly del caricatore CLR  
 La tabella seguente illustra la parola chiave e il livello  
  
|Parola chiave per la generazione dell'evento|Event|Livello|  
|-----------------------------------|-----------|-----------|  
|`LoaderKeyword` (0x8)|`AssemblyLoad` e `AssemblyUnload`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `StartRundownKeyword`|`AssemblyDCStart`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `EndRundownKeyword`|`AssemblyDCEnd`|Informativo (4)|  
  
 La tabella seguente mostra le informazioni sull'evento.  
  
|Event|ID evento|Descrizione|  
|-----------|--------------|-----------------|  
|`AssemblyLoad_V1`|154|Generato quando viene caricato un assembly.|  
|`AssemblyUnload_V1`|155|Generato quando viene scaricato un assembly.|  
|`AssemblyDCStart_V1`|155|Enumera gli assembly durante un rundown di avvio.|  
|`AssemblyDCEnd_V1`|156|Enumera gli assembly durante un rundown di fine.|  
  
 La tabella seguente mostra i dati dell'evento.  
  
|Nome del campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|AssemblyID|win:UInt64|ID univoco per l'assembly.|  
|AppDomainID|win:UInt64|ID del dominio dell'assembly.|  
|BindingID|win:UInt64|ID che identifica univocamente l'associazione di assembly.|  
|AssemblyFlags|win:UInt32|0x1: assembly indipendente dal dominio.<br /><br /> 0x2: assembly dinamico.<br /><br /> 0x4: assembly con immagine nativa.<br /><br /> 0x8: assembly ritirabile.|  
|AssemblyName|win:UnicodeString|Nome completo dell'assembly.|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|   

## <a name="module-events"></a>Eventi modulo
 La tabella seguente illustra la parola chiave e il livello  
  
|Parola chiave per la generazione dell'evento|Event|Livello|  
|-----------------------------------|-----------|-----------|  
|`LoaderKeyword` (0x8)|`ModuleLoad_V2` e `ModuleUnload_V2`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `StartRundownKeyword`|`ModuleDCStart_V2`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `EndRundownKeyword`|`ModuleDCEnd_V2`|Informativo (4)|  
||||  
  
 La tabella seguente mostra le informazioni sull'evento.  
  
|Event|ID evento|Descrizione|  
|-----------|--------------|-----------------|  
|`ModuleLoad_V2`|152|Generato se un modulo viene caricato nel corso di un processo.|  
|`ModuleUnload_V2`|153|Generato se un modulo viene scaricato nel corso di un processo.|  
|`ModuleDCStart_V2`|153|Enumera i moduli durante un rundown di avvio.|  
|`ModuleDCEnd_V2`|154|Enumera i moduli durante un rundown di fine.|  
  
 La tabella seguente mostra i dati dell'evento.  
  
|Nome del campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|ModuleID|win:UInt64|ID univoco per il modulo.|  
|AssemblyID|win:UInt64|ID dell'assembly in cui si trova il modulo.|  
|ModuleFlags|win:UInt32|0x1: modulo indipendente dal dominio.<br /><br /> 0x2: modulo con immagine nativa.<br /><br /> 0x4: modulo dinamico.<br /><br /> 0x8: modulo del manifesto.|  
|Reserved1|win:UInt32|Campo riservato.|  
|ModuleILPath|win:UnicodeString|Percorso dell'immagine Microsoft Intermediate Language (MSIL) per il modulo oppure nome del modulo dinamico se si tratta di un assembly dinamico (con terminazione null).|  
|ModuleNativePath|win:UnicodeString|Percorso dell'immagine nativa del modulo, se presente (con terminazione null).|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|  
|ManagedPdbSignature|win:GUID|Firma GUID del database del programma gestito (PDB) che corrisponde al modulo. (Vedere Note).|  
|ManagedPdbAge|win:UInt32|Numero della durata scritto nel PDB gestito che corrisponde al modulo. (Vedere Note).|  
|ManagedPdbBuildPath|win:UnicodeString|Percorso alla posizione in cui è stato compilato il PDB gestito che corrisponde al modulo. In alcuni casi, può essere semplicemente un nome file. (Vedere Note).|  
|NativePdbSignature|win:GUID|Firma GUID del file PDB del generatore di immagini native (NGen) che corrisponde al modulo, se applicabile. (Vedere Note).|  
|NativePdbAge|win:UInt32|Numero della durata scritto nel PDB di NGen che corrisponde al modulo, se applicabile. (Vedere Note).|  
|NativePdbBuildPath|win:UnicodeString|Percorso alla posizione in cui è stato compilato il PDB di NGen che corrisponde al modulo, se applicabile. In alcuni casi, può essere semplicemente un nome file. (Vedere Note).|  
  
### <a name="remarks"></a>Note  
  
- I campi che contengono "Pdb" nel nome possono essere usati dagli strumenti di profilazione per individuare i PDB che corrispondono ai moduli caricati durante la sessione di profilazione. I valori di questi campi corrispondono ai dati scritti nelle sezioni IMAGE_DIRECTORY_ENTRY_DEBUG del modulo normalmente usato dai debugger per individuare i PDB che corrispondono ai moduli caricati.  
  
- I nomi dei campi che iniziano con "ManagedPdb" fanno riferimento al PDB gestito che corrisponde al modulo MSIL generato dal compilatore gestito (ad esempio, il compilatore C# o Visual Basic). Questo PDB usa il formato PDB gestito e descrive in che modo gli elementi del codice sorgente gestito originale, ad esempio file, numeri di riga e nomi di simboli, eseguono il mapping agli elementi MSIL compilati nel form MSIL.  
  
- I nomi dei campi che iniziano con "NativePdb" fanno riferimento al PDB di NGen generato chiamando `NGEN createPDB`. Questo PDB usa il formato PDB nativo e descrive in che modo gli elementi del codice sorgente gestito originale, ad esempio file, numeri di riga e nomi di simboli, eseguono il mapping agli elementi nativi compilati nel modulo NGen.  

## <a name="clr-domain-module-events"></a>Eventi modulo del dominio CLR
 La tabella seguente illustra la parola chiave e il livello  
  
|Parola chiave per la generazione dell'evento|Event|Livello|  
|-----------------------------------|-----------|-----------|  
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `StartRundownKeyword`|`DomainModuleDCStart_V1`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `EndRundownKeyword`|`DomainModuleDCEnd_V1`|Informativo (4)|  
  
 La tabella seguente mostra le informazioni sull'evento.  
  
|Event|ID evento|Descrizione|  
|-----------|--------------|-----------------|  
|`DomainModuleLoad_V1`|151|Generato quando un modulo viene caricato per un dominio applicazioni.|  
|`DomainModuleDCStart_V1`|151|Enumera i moduli caricati per un dominio applicazioni durante un rundown di avvio e viene registrato per tutti i domini applicazioni.|  
|`DomainModuleDCEnd_V1`|152|Enumera i moduli caricati per un dominio applicazioni durante un rundown di fine e viene registrato per tutti i domini applicazioni.|  
  
 La tabella seguente mostra i dati dell'evento.  
  
|Nome del campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|ModuleID|win:UInt64|Identifica l'assembly al quale appartiene il modulo.|  
|AssemblyID|win:UInt64|ID dell'assembly in cui si trova il modulo.|  
|AppDomainID|win:UInt64|ID del dominio applicazioni in cui viene usato il modulo.|  
|ModuleFlags|win:UInt32|0x1: modulo indipendente dal dominio.<br /><br /> 0x2: modulo con immagine nativa.<br /><br /> 0x4: modulo dinamico.<br /><br /> 0x8: modulo del manifesto.|  
|Reserved1|win:UInt32|Campo riservato.|  
|ModuleILPath|win:UnicodeString|Percorso dell'immagine MSIL per il modulo oppure nome del modulo dinamico se si tratta di un assembly dinamico (con terminazione null)|  
|ModuleNativePath|win:UnicodeString|Percorso dell'immagine nativa del modulo, se presente (con terminazione null).|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|  

## <a name="module-range-events"></a>Eventi di intervallo modulo
 La tabella seguente illustra la parola chiave e il livello  
  
|Parola chiave per la generazione dell'evento|Event|Livello|  
|-----------------------------------|-----------|-----------|  
|`PerfTrackKeyWord`)|`ModuleRange`|Informativo (4)|  
|`PerfTrackKeyWord`|`ModuleRangeDCStart`|Informativo (4)|  
|`PerfTrackKeyWord`|`ModuleRangeDCEnd`|Informativo (4)|  
  
 La tabella seguente mostra le informazioni sull'evento.  
  
|Event|ID evento|Descrizione|  
|-----------|--------------|-----------------|  
|`ModuleRange`|158|Questo evento è presente se un'immagine del generatore di immagini native (NGen) è stata ottimizzata con IBC e contiene informazioni sulle sezioni critiche dell'immagine NGen.|  
|`ModuleRangeDCStart`|160|Evento `ModuleRange` generato all'avvio di un rundown.|  
|`ModuleRangeDCEnd`|161|Evento `ModuleRange` generato alla fine di un rundown.|  
  
 La tabella seguente mostra i dati dell'evento.  
  
|Nome del campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|ClrInstanceID|win:UInt16|Identifica in modo univoco un'istanza specifica di CLR in un processo se vengono caricate più istanze di CLR.|  
|ModuleID|win:UInt64|Identifica l'assembly al quale appartiene il modulo.|  
|RangeBegin|win:UInt32|Offset nel modulo che rappresenta l'inizio dell'intervallo per il tipo di intervallo specificato.|  
|RangeSize|win:UInt32|Dimensione dell'intervallo specificato in byte.|  
|RangeType|win:UInt32|Valore singolo, 0x4, che rappresenta gli intervalli IBC a freddo. In futuro, questo campo potrebbe rappresentare più valori.|  
|RangeSize1|win:UInt32|0 indica dati non validi.|  
|RangeBegin2|win:UnicodeString||  
  
### <a name="remarks"></a>Note  
 Se un'immagine NGen caricata in un processo di .NET Framework è stata ottimizzata con IBC, l'evento `ModuleRange` che contiene gli intervalli critici nell'immagine NGen viene registrato insieme a `moduleID` e `ClrInstanceID`.  Se l'immagine NGen non è ottimizzata con IBC, l'evento non viene registrato. Per determinare il nome del modulo, questo evento deve essere collazionato con gli eventi ETW di caricamento del modulo.  
  
 Le dimensioni del payload per questo evento sono variabili. Il campo `Count` indica il numero di offset dell'intervallo contenuti nell'evento.  L'evento deve essere collazionato con l'evento `IStart` di Windows per determinare gli intervalli effettivi. L'evento di caricamento dell'immagine di Windows viene registrato quando viene caricata un'immagine e contiene l'indirizzo virtuale dell'immagine caricata.  
  
 Gli eventi di intervallo form vengono generati in un qualsiasi livello ETW maggiore o uguale a 4 e vengono classificati come eventi informativi.  
  
## <a name="see-also"></a>Vedere anche

- [Eventi ETW di CLR](clr-etw-events.md)

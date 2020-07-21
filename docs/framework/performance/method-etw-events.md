---
title: Eventi EWT dei metodi
description: Vedere eventi ETW che raccolgono informazioni specifiche dei metodi, ad esempio eventi del metodo CLR, marcatore del metodo CLR o eventi dettagliati del metodo CLR, e MethodJittingStarted.
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, method events (CLR)
- method events [.NET Framework]
ms.assetid: 167a4459-bb6e-476c-9046-7920880f2bb5
ms.openlocfilehash: f48867a0aef417ad0b19a15d78e0c0f01a7c30a1
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474319"
---
# <a name="method-etw-events"></a>Eventi EWT dei metodi

Questi eventi raccolgono informazioni specifiche dei metodi. Il payload di questi eventi è necessario per la risoluzione dei simboli. Questi eventi forniscono inoltre informazioni utili, ad esempio il numero di volte in cui un metodo è stato chiamato.

Tutti gli eventi dei metodi hanno un livello "Informativo (4)". Tutti gli eventi dettagliati dei metodi hanno un livello "Dettagliato (5)".

Tutti gli eventi dei metodi vengono generati dalla parola chiave `JITKeyword` (0x10) o `NGenKeyword` (0x20) nel provider di runtime oppure da `JitRundownKeyword` (0x10) o `NGENRundownKeyword` (0x20) nel provider di rundown.

## <a name="clr-method-events"></a>Eventi dei metodi CLR

La tabella seguente illustra la parola chiave e il livello Per altre informazioni, vedere [parole chiave e livelli ETW di CLR](clr-etw-keywords-and-levels.md).

|Parola chiave per la generazione dell'evento|Level|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) nel provider di runtime|Informativo (4)|
|`NGenKeyword` (0x20) nel provider di runtime|Informativo (4)|
|`JitRundownKeyword` (0x10) nel provider di rundown|Informativo (4)|
|`NGENRundownKeyword` (0x20) nel provider di rundown|Informativo (4)|

La tabella seguente mostra le informazioni sull'evento:

|Evento|ID evento|Descrizione|
|-----------|--------------|-----------------|
|`MethodLoad_V1`|136|Generato per un metodo con caricamento JIT (JIT-loaded) o quando viene caricata un'immagine NGEN. I metodi dinamici e generici non usano questa versione per il caricamento. Gli helper JIT non usano mai questa versione.|
|`MethodUnLoad_V1`|137|Generato quando viene scaricato un modulo o viene distrutto un dominio dell'applicazione. I metodi dinamici non usano mai questa versione per lo scaricamento.|
|`MethodDCStart_V1`|137|Enumera i metodi durante un rundown di avvio.|
|`MethodDCEnd_V1`|138|Enumera i metodi durante un rundown di fine.|

La tabella seguente mostra i dati dell'evento:

|Nome del campo|Tipo di dati|Descrizione|
|----------------|---------------|-----------------|
|MethodID|win:UInt64|Identificatore univoco di un metodo. Per i metodi helper JIT, è impostato sull'indirizzo iniziale del metodo.|
|ModuleID|win:UInt64|Identificatore del modulo a cui appartiene il metodo (0 per helper JIT).|
|MethodStartAddress|win:UInt64|Indirizzo iniziale del metodo.|
|MethodSize|win:UInt32|Dimensioni del metodo.|
|MethodToken|win:UInt32|0 per metodi dinamici e helper JIT.|
|MethodFlags|win:UInt32|0x1: metodo dinamico.<br /><br /> 0x2: metodo generico.<br /><br /> 0x4: metodo del codice con compilazione JIT (in caso contrario, codice di un'immagine nativa NGEN).<br /><br /> 0x8: metodo helper.|
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|

## <a name="clr-method-marker-events"></a>Eventi marcatori dei metodi CLR

Questi eventi vengono generati solo nel provider di rundown. Indicano la fine dell'enumerazione dei metodi durante un rundown di avvio o di fine. Ovvero, vengono generati quando è abilitata la parola chiave `NGENRundownKeyword`, `JitRundownKeyword`, `LoaderRundownKeyword`o `AppDomainResourceManagementRundownKeyword` .

La tabella seguente illustra la parola chiave e il livello:

|Parola chiave per la generazione dell'evento|Level|
|-----------------------------------|-----------|
|`AppDomainResourceManagementRundownKeyword` (0x800) nel provider di rundown|Informativo (4)|
|`JitRundownKeyword` (0x10) nel provider di rundown|Informativo (4)|
|`NGENRundownKeyword` (0x20) nel provider di rundown|Informativo (4)|

La tabella seguente mostra le informazioni sull'evento:

|Evento|ID evento|Descrizione|
|-----------|--------------|----------------|
|`DCStartInit_V1`|147|Inviato prima dell'avvio dell'enumerazione durante un rundown di avvio.|
|`DCStartComplete_V1`|145|Inviato alla fine dell'enumerazione durante un rundown di avvio.|
|`DCEndInit_V1`|148|Inviato prima dell'avvio dell'enumerazione durante un rundown di fine.|
|`DCEndComplete_V1`|146|Inviato alla fine dell'enumerazione durante un rundown di fine.|

La tabella seguente mostra i dati dell'evento:

|Nome del campo|Tipo di dati|Descrizione|
|----------------|---------------|-----------------|
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|

## <a name="clr-method-verbose-events"></a>Eventi dettagliati dei metodi CLR

La tabella seguente illustra la parola chiave e il livello:

|Parola chiave per la generazione dell'evento|Level|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) nel provider di runtime|Dettagliato (5)|
|`NGenKeyword` (0x20) nel provider di runtime|Dettagliato (5)|
|`JitRundownKeyword` (0x10) nel provider di rundown|Dettagliato (5)|
|`NGENRundownKeyword` (0x20) nel provider di rundown|Dettagliato (5)|

La tabella seguente mostra le informazioni sull'evento:

|Evento|ID evento|Descrizione|
|-----------|--------------|-----------------|
|`MethodLoadVerbose_V1`|143|Generato per un metodo con caricamento JIT o quando viene caricata un'immagine NGEN. I metodi dinamici e generici usano sempre questa versione per il caricamento. Gli helper JIT usano sempre questa versione.|
|`MethodUnLoadVerbose_V1`|144|Generato quando viene distrutto un metodo dinamico, viene scaricato un modulo o viene distrutto un dominio dell'applicazione. I metodi dinamici usano sempre questa versione per lo scaricamento.|
|`MethodDCStartVerbose_V1`|141|Enumera i metodi durante un rundown di avvio.|
|`MethodDCEndVerbose_V1`|142|Enumera i metodi durante un rundown di fine.|

La tabella seguente mostra i dati dell'evento:

|Nome del campo|Tipo di dati|Descrizione|
|----------------|---------------|-----------------|
|MethodID|win:UInt64|Identificatore univoco del metodo. Per i metodi helper JIT, è impostato sull'indirizzo iniziale del metodo.|
|ModuleID|win:UInt64|Identificatore del modulo a cui appartiene il metodo (0 per helper JIT).|
|MethodStartAddress|win:UInt64|Indirizzo iniziale.|
|MethodSize|win:UInt32|Lunghezza del metodo.|
|MethodToken|win:UInt32|0 per metodi dinamici e helper JIT.|
|MethodFlags|win:UInt32|0x1: metodo dinamico.<br /><br /> 0x2: metodo generico.<br /><br /> 0x4: metodo con compilazione JIT (in caso contrario, generato da NGen.exe)<br /><br /> 0x8: metodo helper.|
|MethodNameSpace|win:UnicodeString|Nome completo dello spazio dei nomi associato al metodo.|
|MethodName|win:UnicodeString|Nome completo della classe associata al metodo.|
|MethodSignature|win:UnicodeString|Firma del metodo (elenco con valori delimitati da virgole di nomi di tipo).|
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|

## <a name="methodjittingstarted-event"></a>Evento MethodJittingStarted

La tabella seguente illustra la parola chiave e il livello:

|Parola chiave per la generazione dell'evento|Level|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) nel provider di runtime|Dettagliato (5)|
|`NGenKeyword` (0x20) nel provider di runtime|Dettagliato (5)|
|`JitRundownKeyword` (0x10) nel provider di rundown|Dettagliato (5)|
|`NGENRundownKeyword` (0x20) nel provider di rundown|Dettagliato (5)|

La tabella seguente mostra le informazioni sull'evento:

|Evento|ID evento|Descrizione|
|-----------|--------------|-----------------|
|`MethodJittingStarted`|145|Generato quando un metodo viene compilato tramite JIT.|

La tabella seguente mostra i dati dell'evento:

|Nome del campo|Tipo di dati|Descrizione|
|----------------|---------------|-----------------|
|MethodID|win:UInt64|Identificatore univoco del metodo.|
|ModuleID|win:UInt64|Identificatore del modulo a cui appartiene il metodo.|
|MethodToken|win:UInt32|0 per metodi dinamici e helper JIT.|
|MethodILSize|win:UInt32|Dimensioni del codice MSIL (Microsoft Intermediate Language) per il metodo con compilazione JIT.|
|MethodNameSpace|win:UnicodeString|Nome completo della classe associata al metodo.|
|MethodName|win:UnicodeString|Nome del metodo.|
|MethodSignature|win:UnicodeString|Firma del metodo (elenco con valori delimitati da virgole di nomi di tipo).|
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|

## <a name="see-also"></a>Vedere anche

- [Eventi ETW di CLR](clr-etw-events.md)

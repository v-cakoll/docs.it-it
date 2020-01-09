---
title: Eventi ETW di contesa-.NET
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
ms.openlocfilehash: 98fc2adcaebe4c9646ab9960f796982681a9015a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716130"
---
# <a name="contention-etw-events"></a>Eventi ETW di contesa

Gli eventi di conflitto vengono generati ogni volta che si verifica un conflitto per i blocchi <xref:System.Threading.Monitor?displayProperty=nameWithType> o nativi usati dal runtime. Un conflitto si verifica quando un thread attende un blocco mentre un altro thread possiede tale blocco.

La tabella seguente illustra le parole chiave con cui vengono generati gli eventi e il livello degli eventi stessi. Per altre informazioni, vedere [parole chiave e livelli ETW di CLR](clr-etw-keywords-and-levels.md).

|Parola chiave per la generazione dell'evento|Livello|
|-----------------------------------|-----------|
|`ContentionKeyword` (0x4000)|Informativo (4)|

Nella tabella seguente vengono illustrate le informazioni sugli eventi:

|Event|ID evento|Generato quando|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|81|Inizio del conflitto. Questo evento non include il tempo di rotazione che intercorre prima che un thread attenda l'acquisizione di un blocco; viene generato soltanto quando il thread attende di acquisire un blocco.|
|`ContentionStop`|91|Fine del conflitto.|

La tabella seguente mostra i dati dell'evento:

|Nome del campo|Tipo di dati|Descrizione|
|----------------|---------------|-----------------|
|Flag|win:UInt8|0 per gestito, 1 per nativo.|
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR.|

## <a name="see-also"></a>Vedere anche

- [Eventi ETW di CLR](clr-etw-events.md)

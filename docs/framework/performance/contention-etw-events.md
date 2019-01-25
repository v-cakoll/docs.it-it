---
title: Eventi ETW di conflitto - .NET
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 95f56a6c8b51c58ed36d5d0de428bf57b728009c
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857645"
---
# <a name="contention-etw-events"></a>Eventi ETW di conflitto

Gli eventi di conflitto vengono generati ogni volta che si verifica un conflitto per i blocchi <xref:System.Threading.Monitor?displayProperty=nameWithType> o nativi usati dal runtime. Un conflitto si verifica quando un thread attende un blocco mentre un altro thread possiede tale blocco.

La tabella seguente illustra le parole chiave con cui vengono generati gli eventi e il livello degli eventi stessi. Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).

|Parola chiave per la generazione dell'evento|Livello|
|-----------------------------------|-----------|
|`ContentionKeyword` (0x4000)|Informativo (4)|

Nella tabella seguente mostra le informazioni sull'evento:

|event|ID evento|Generato quando|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|81|Inizio del conflitto. Questo evento non include il tempo di rotazione che intercorre prima che un thread attenda l'acquisizione di un blocco; viene generato soltanto quando il thread attende di acquisire un blocco.|
|`ContentionStop`|91|Fine del conflitto.|

Nella tabella seguente mostra i dati dell'evento:

|Nome campo|Tipo di dati|Descrizione|
|----------------|---------------|-----------------|
|Flag|win:UInt8|0 per gestito, 1 per nativo.|
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR.|

## <a name="see-also"></a>Vedere anche

- [Eventi ETW di CLR](clr-etw-events.md)

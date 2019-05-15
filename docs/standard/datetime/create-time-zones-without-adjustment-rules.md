---
title: 'Procedura: Creare fusi orari senza regole di regolazione'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff4cfe2b492b676c061043f018390844f1807440
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586405"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a>Procedura: Creare fusi orari senza regole di regolazione

Le informazioni del fuso orario preciso richiesto da un'applicazione potrebbero non essere presente in un sistema specifico per diversi motivi:

* Il fuso orario non è mai stato definito nel Registro di sistema locale.

* I dati sul fuso orario sono stati modificati o rimossi dal Registro di sistema.

* Il fuso orario esiste ma non dispone di informazioni accurate sulle regolazioni del fuso orario per un determinato periodo cronologico.

In questi casi, è possibile chiamare il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo per definire il fuso orario richiesto dall'applicazione. È possibile usare gli overload di questo metodo per creare un fuso orario con o senza regole di regolazione. Se il fuso orario supporta l'ora legale, è possibile definire le regolazioni con entrambe le regole di rettifica fissa o mobile. (Per le definizioni di questi termini, vedere la sezione "Terminologia fuso orario" nella [Panoramica sul fuso orario](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> Fusi orari personalizzati creati tramite la chiamata di <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> (metodo) non vengono aggiunti al Registro di sistema. Al contrario, è possibile accedervi solo tramite il riferimento all'oggetto restituito dal <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> chiamata al metodo.

In questo argomento viene illustrato come creare un fuso orario senza regole di regolazione. Per creare un fuso orario che supporta regole di regolazione dell'ora legale, vedere [come: Creare fusi orari con regole di regolazione](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

### <a name="to-create-a-time-zone-without-adjustment-rules"></a>Per creare un fuso orario senza regole di regolazione

1. Definire nome visualizzato del fuso orario.

   Il nome visualizzato segue un formato piuttosto standard in cui è racchiuso tra parentesi offset del fuso orario dall'ora Coordinated Universal Time (UTC) ed è seguito da una stringa che identifica il fuso orario, una o più delle città nel fuso orario o uno più il cou Mo o aree geografiche nel fuso orario.

2. Definire il nome dell'ora solare del fuso orario. In genere, questa stringa viene utilizzata anche come identificatore del fuso orario.

3. Se si desidera usare un identificatore differente rispetto al nome del fuso orario standard, definire l'identificatore del fuso orario.

4. Creare un'istanza di un <xref:System.TimeSpan> oggetto che definisce l'offset del fuso orario rispetto all'ora UTC. Fusi orari con volte in cui siano successivi rispetto all'ora UTC avere un offset positivi. Fusi orari con ore indietro rispetto all'ora UTC hanno una differenza negativa.

5. Chiamare il <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> metodo per creare un'istanza del nuovo fuso orario.

## <a name="example"></a>Esempio

L'esempio seguente definisce un fuso orario personalizzato per Mawson, Antartide, che non dispone di alcuna regola di rettifica.

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

La stringa assegnata al <xref:System.TimeZoneInfo.DisplayName%2A> proprietà segue un formato standard in cui l'offset del fuso orario rispetto all'ora UTC è seguito da una semplice descrizione del fuso orario.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

* Che siano importati spazi dei nomi seguenti:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Panoramica sui fusi orari](../../../docs/standard/datetime/time-zone-overview.md)
- [Procedura: Creare fusi orari con regole di regolazione](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)

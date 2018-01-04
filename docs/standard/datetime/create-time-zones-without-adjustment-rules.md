---
title: 'Procedura: creare fusi orari senza regole di regolazione'
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 14c5e02ce5af03d063260af19e9dd1a970a93ab6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a>Procedura: creare fusi orari senza regole di regolazione

Le informazioni di fuso orario preciso richiesto da un'applicazione potrebbero non essere presente in un determinato sistema per diversi motivi:

* Il fuso orario non è mai stato definito nel Registro di sistema del sistema locale.

* Dati sul fuso orario sono stati modificati o rimossi dal Registro di sistema.

* Il fuso orario esiste ma non dispone di informazioni accurate sulle regolazioni del fuso orario per un determinato periodo storico.

In questi casi, è possibile chiamare il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo per definire il fuso orario richiesto dall'applicazione. È possibile utilizzare l'overload di questo metodo per creare un fuso orario con o senza regole di regolazione. Se il fuso orario supporta l'ora legale, è possibile definire le regolazioni con entrambe le regole di regolazione fissa o mobile. (Per le definizioni di questi termini, vedere la sezione "Terminologia fuso orario" in [Panoramica sul fuso orario](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> Fusi orari personalizzati creati tramite la chiamata di <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> (metodo) non vengono aggiunti al Registro di sistema. Ma è possibile accedervi solo tramite il riferimento all'oggetto restituito dal <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> chiamata al metodo.

In questo argomento viene illustrato come creare un fuso orario senza regole di regolazione. Per creare un fuso orario che supporta le regole di regolazione dell'ora legale, vedere [procedura: creare fusi orari con regole di regolazione](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

### <a name="to-create-a-time-zone-without-adjustment-rules"></a>Per creare un fuso orario senza regole di regolazione

1. Definire nome visualizzato del fuso orario.

   Il nome visualizzato segue un formato pressoché standard in cui l'offset del fuso orario dall'ora Coordinated Universal Time (UTC) è racchiuso tra parentesi ed è seguito da una stringa che identifica il fuso orario, una o più delle città nel fuso orario, o in uno o più di cou Mo o aree del fuso orario.

2. Definire il nome dell'ora solare del fuso orario. In genere, questa stringa viene utilizzata anche come identificatore del fuso orario.

3. Se si desidera utilizzare un identificatore nome standard del fuso orario diverso, definire l'identificatore del fuso orario.

4. Creare un'istanza di un <xref:System.TimeSpan> oggetto che definisce l'offset del fuso orario dall'ora UTC. Fusi orari con ore in avanti rispetto all'ora UTC hanno un offset positivo. Fusi orari con ore precedenti rispetto all'ora UTC hanno un offset negativo.

5. Chiamare il <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> metodo per creare un'istanza del nuovo fuso orario.

## <a name="example"></a>Esempio

Nell'esempio seguente definisce un fuso orario personalizzato per Mawson, Antartide senza regole di regolazione.

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

La stringa assegnata al <xref:System.TimeZoneInfo.DisplayName%2A> proprietà segue un formato standard in cui l'offset del fuso orario dall'ora UTC è seguito da una semplice descrizione del fuso orario.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

* Un riferimento a System.Core.dll essere aggiunto al progetto.

* Che importati spazi dei nomi seguenti:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Vedere anche

[Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
[Panoramica sul fuso orario](../../../docs/standard/datetime/time-zone-overview.md)
[procedura: creare fusi orari con regole di regolazione](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)

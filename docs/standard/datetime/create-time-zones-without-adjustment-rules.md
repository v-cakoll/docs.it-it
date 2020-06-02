---
title: 'Procedura: creare fusi orari senza regole di regolazione'
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
ms.openlocfilehash: 1d8aae1284e9ee9871c6f201c6a00e0b547f95fa
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84278038"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a>Procedura: creare fusi orari senza regole di regolazione

Le informazioni esatte sul fuso orario richieste da un'applicazione potrebbero non essere presenti in un sistema specifico per diversi motivi:

- Il fuso orario non è mai stato definito nel registro di sistema del sistema locale.

- I dati relativi al fuso orario sono stati modificati o rimossi dal registro di sistema.

- Il fuso orario esiste ma non dispone di informazioni accurate sulle regolazioni del fuso orario per un determinato periodo cronologico.

In questi casi, è possibile chiamare il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo per definire il fuso orario richiesto dall'applicazione. È possibile usare gli overload di questo metodo per creare un fuso orario con o senza regole di regolazione. Se il fuso orario supporta l'ora legale, è possibile definire le regolazioni con regole di rettifica fisse o mobili. Per le definizioni di questi termini, vedere la sezione "terminologia del fuso orario" nella [Panoramica del fuso orario](time-zone-overview.md).

> [!IMPORTANT]
> I fusi orari personalizzati creati chiamando il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo non vengono aggiunti al registro di sistema. Al contrario, è possibile accedervi solo tramite il riferimento all'oggetto restituito dalla <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> chiamata al metodo.

In questo argomento viene illustrato come creare un fuso orario senza regole di rettifica. Per creare un fuso orario che supporta le regole di regolazione dell'ora legale, vedere [procedura: creare fusi orari con regole di rettifica](create-time-zones-with-adjustment-rules.md).

### <a name="to-create-a-time-zone-without-adjustment-rules"></a>Per creare un fuso orario senza regole di rettifica

1. Definire il nome visualizzato del fuso orario.

   Il nome visualizzato segue un formato abbastanza standard in cui l'offset del fuso orario rispetto all'ora UTC (Coordinated Universal Time) è racchiuso tra parentesi ed è seguito da una stringa che identifica il fuso orario, una o più città del fuso orario o uno o più paesi o aree del fuso orario.

2. Definire il nome dell'ora solare del fuso orario. In genere, questa stringa viene usata anche come identificatore del fuso orario.

3. Se si vuole usare un identificatore diverso dal nome standard del fuso orario, definire l'identificatore del fuso orario.

4. Creare un'istanza di un <xref:System.TimeSpan> oggetto che definisce l'offset del fuso orario rispetto all'ora UTC. I fusi orari con tempi successivi all'ora UTC hanno un offset positivo. I fusi orari con tempi precedenti all'ora UTC hanno un offset negativo.

5. Chiamare il <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> metodo per creare un'istanza del nuovo fuso orario.

## <a name="example"></a>Esempio

Nell'esempio seguente viene definito un fuso orario personalizzato per Mawson, Antartide, che non dispone di regole di rettifica.

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

La stringa assegnata alla <xref:System.TimeZoneInfo.DisplayName%2A> proprietà segue un formato standard in cui l'offset del fuso orario rispetto all'ora UTC è seguito da una descrizione descrittiva del fuso orario.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Che vengano importati gli spazi dei nomi seguenti:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](index.md)
- [Panoramica sul fuso orario](time-zone-overview.md)
- [Procedura: creare fusi orari con regole di rettifica](create-time-zones-with-adjustment-rules.md)

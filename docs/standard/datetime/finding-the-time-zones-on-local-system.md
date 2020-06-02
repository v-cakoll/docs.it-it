---
title: Ricerca dei fusi orari definiti in un sistema locale
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], local
- time zones [.NET Framework], finding local system time zones
- time zone identifiers [.NET Framework]
- local time zone access
- time zones [.NET Framework], retrieving
- UTC times, finding local system time zones
- time zones [.NET Framework], UTC
ms.assetid: 3f63b1bc-9a4b-4bde-84ea-ab028a80d3e1
ms.openlocfilehash: d313bbed3cc525a74b90537dd4f1742c09c62cd4
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277024"
---
# <a name="finding-the-time-zones-defined-on-a-local-system"></a>Ricerca dei fusi orari definiti in un sistema locale

La classe <xref:System.TimeZoneInfo> non espone un costruttore pubblico. Di conseguenza, non è possibile usare la parola chiave `new` per creare un nuovo oggetto <xref:System.TimeZoneInfo>. Le istanze degli oggetti <xref:System.TimeZoneInfo> vengono invece create recuperando le informazioni sui fusi orari predefiniti dal Registro di sistema oppure creando un fuso orario personalizzato. Questo argomento descrive la creazione dell'istanza di un fuso orario da dati archiviati nel Registro di sistema. Inoltre, le proprietà `static` (`shared` in Visual Basic) della classe <xref:System.TimeZoneInfo> forniscono accesso all'ora Coordinated Universal Time (UTC) e al fuso orario locale.

> [!NOTE]
> Per i fusi orari non definiti nel Registro di sistema, è possibile creare fusi orari personalizzati chiamando gli overload del metodo <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>. Per creare un fuso orario personalizzato, vedere gli argomenti [procedura: creare fusi orari senza regole di rettifica](create-time-zones-without-adjustment-rules.md) e [procedura: creare fusi orari con regole di rettifica](create-time-zones-with-adjustment-rules.md) . Inoltre, è possibile creare l'istanza di un oggetto <xref:System.TimeZoneInfo> ripristinando l'oggetto da una stringa serializzata con il metodo <xref:System.TimeZoneInfo.FromSerializedString%2A>. La serializzazione e la deserializzazione di un <xref:System.TimeZoneInfo> oggetto sono illustrate nella [procedura: salvare fusi orari in una risorsa incorporata](save-time-zones-to-an-embedded-resource.md) e [procedura: ripristinare i fusi orari da una risorsa incorporata](restore-time-zones-from-an-embedded-resource.md) .

## <a name="accessing-individual-time-zones"></a>Accesso a singoli fusi orari

La classe <xref:System.TimeZoneInfo> fornisce due oggetti fuso orario predefiniti che rappresentano l'ora UTC e il fuso orario locale. Questi oggetti sono disponibili rispettivamente nelle proprietà <xref:System.TimeZoneInfo.Utc%2A> e <xref:System.TimeZoneInfo.Local%2A>. Per istruzioni sull'accesso all'ora UTC o ai fusi orari locali, vedere [procedura: accedere agli oggetti predefiniti dell'ora UTC e del fuso orario locale](access-utc-and-local.md).

È anche possibile creare l'istanza di un oggetto <xref:System.TimeZoneInfo> che rappresenta qualsiasi fuso orario definito nel Registro di sistema. Per istruzioni sulla creazione di un'istanza di un oggetto fuso orario specifico, vedere [procedura: creare un'istanza di un oggetto TimeZoneInfo](instantiate-time-zone-info.md).

## <a name="time-zone-identifiers"></a>Identificatori del fuso orario

L'identificatore del fuso orario è un campo chiave che identifica in modo univoco il fuso orario. Benché la maggior parte delle chiavi sia relativamente breve, in confronto l'identificatore del fuso orario è piuttosto lungo. Nella maggior parte dei casi, il suo valore corrisponde alla proprietà <xref:System.TimeZoneInfo.StandardName%2A?displayProperty=nameWithType>, che viene usata per fornire il nome dell'ora solare del fuso orario. Esistono tuttavia alcune eccezioni. Il modo migliore per assicurarsi di specificare un identificatore univoco consiste nell'enumerare i fusi orari disponibili nel sistema e annotare gli identificatori associati.

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](index.md)
- [Procedura: accedere agli oggetti predefiniti dell'ora UTC e del fuso orario locale](access-utc-and-local.md)
- [Procedura: creare un'istanza di un oggetto TimeZoneInfo](instantiate-time-zone-info.md)
- [Conversione degli orari tra fusi orari](converting-between-time-zones.md)

---
title: 'Procedura: ripristinare fusi orari da una risorsa incorporata'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99d38b336b5e655dd1c96682eec90c5fbe8469d6
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47077396"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>Procedura: ripristinare fusi orari da una risorsa incorporata

In questo argomento viene descritto come ripristinare i fusi orari che sono state salvate in un file di risorse. Per informazioni e istruzioni sul salvataggio di fusi orari, vedere [procedura: salvare fusi orari in una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>Per deserializzare un oggetto TimeZoneInfo da una risorsa incorporata

1. Se il fuso orario da recuperare non è un fuso orario personalizzato, provare a crearne un'istanza utilizzando il <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> (metodo).

2. Creare un'istanza di un <xref:System.Resources.ResourceManager> passando il nome completo del file di risorse incorporato e un riferimento all'assembly che contiene il file di risorse.

   Se non è possibile determinare il nome completo del file di risorse incorporato, usare il [Ildasm.exe (Disassembler IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) per esaminare il manifesto dell'assembly. Un `.mresource` ingresso identifica la risorsa. Nell'esempio, il nome della risorsa completo è `SerializeTimeZoneData.SerializedTimeZones`.

   Se il file di risorse è incorporato nello stesso assembly che contiene il codice di creazione di un'istanza di fusi orari, è possibile recuperare un riferimento a esso chiamando il `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> (metodo).

3. Se la chiamata ai <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> metodo ha esito negativo, o se deve essere creata un'istanza di un fuso orario personalizzato, recuperare una stringa contenente il fuso orario serializzato chiamando il <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> (metodo).

4. Deserializzare i dati del fuso orario chiamando il <xref:System.TimeZoneInfo.FromSerializedString%2A> (metodo).

## <a name="example"></a>Esempio

Nell'esempio seguente viene deserializzato un <xref:System.TimeZoneInfo> oggetto archiviato in un file di risorsa XML .NET incorporato.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

Questo codice illustra la gestione delle eccezioni per assicurarsi che un <xref:System.TimeZoneInfo> oggetto richiesta dall'applicazione è presente. Tenta innanzitutto di creare un'istanza di un <xref:System.TimeZoneInfo> oggetto recuperandolo dal Registro di sistema utilizzando la <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> (metodo). Se il fuso orario non è possibile creare un'istanza, il codice si recupera dal file di risorsa incorporata.

Perché i dati per i fusi orari personalizzati (fusi orari creata un'istanza usando il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo) non vengono archiviate nel Registro di sistema non chiama il codice il <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> per creare un'istanza del fuso orario per Palmer, Antartide. Al contrario, Cerca immediatamente il file di risorse incorporate per recuperare una stringa che contiene i dati del fuso orario, prima di chiamare il <xref:System.TimeZoneInfo.FromSerializedString%2A> (metodo).

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

* Aggiungere un riferimento alla DLL e Forms al progetto.

* Che siano importati spazi dei nomi seguenti:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Vedere anche

* [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
* [Panoramica sui fusi orari](../../../docs/standard/datetime/time-zone-overview.md)
* [Procedura: Salvare fusi orari in una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)

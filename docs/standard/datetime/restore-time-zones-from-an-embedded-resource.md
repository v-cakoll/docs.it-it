---
title: 'Procedura: ripristinare i fusi orari da una risorsa incorporata'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
ms.openlocfilehash: cd2119d6d22f3f676b7167ed545aeb058123cfb5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122196"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>Procedura: ripristinare i fusi orari da una risorsa incorporata

In questo argomento viene descritto come ripristinare i fusi orari salvati in un file di risorse. Per informazioni e istruzioni sul salvataggio dei fusi orari, vedere [procedura: salvare fusi orari in una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>Per deserializzare un oggetto TimeZoneInfo da una risorsa incorporata

1. Se il fuso orario da recuperare non è un fuso orario personalizzato, provare a crearne un'istanza usando il metodo <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>.

2. Creare un'istanza di un oggetto <xref:System.Resources.ResourceManager> passando il nome completo del file di risorse incorporato e un riferimento all'assembly che contiene il file di risorse.

   Se non è possibile determinare il nome completo del file di risorse incorporato, utilizzare [Ildasm. exe (DISASSEMBLER il)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) per esaminare il manifesto dell'assembly. Una voce di `.mresource` identifica la risorsa. Nell'esempio, il nome completo della risorsa è `SerializeTimeZoneData.SerializedTimeZones`.

   Se il file di risorse è incorporato nello stesso assembly contenente il codice di creazione dell'istanza del fuso orario, è possibile recuperare un riferimento a esso chiamando il metodo `static` (`Shared` Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>.

3. Se la chiamata al metodo <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> ha esito negativo o se è necessario creare un'istanza di un fuso orario personalizzato, recuperare una stringa che contiene il fuso orario serializzato chiamando il metodo <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>.

4. Deserializzare i dati del fuso orario chiamando il metodo <xref:System.TimeZoneInfo.FromSerializedString%2A>.

## <a name="example"></a>Esempio

Nell'esempio seguente viene deserializzato un oggetto <xref:System.TimeZoneInfo> archiviato in un file di risorse XML .NET incorporato.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

In questo codice viene illustrata la gestione delle eccezioni per assicurarsi che sia presente un <xref:System.TimeZoneInfo> oggetto richiesto dall'applicazione. Tenta innanzitutto di creare un'istanza di un oggetto <xref:System.TimeZoneInfo> tramite il recupero dal registro di sistema tramite il metodo <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>. Se non è possibile creare un'istanza del fuso orario, il codice lo recupera dal file di risorse incorporato.

Poiché i dati per i fusi orari personalizzati (fusi orari creati con il metodo <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>) non vengono archiviati nel registro di sistema, il codice non chiama il <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> per creare un'istanza del fuso orario per Palmer, Antartide. Al contrario, cerca immediatamente il file di risorse incorporato per recuperare una stringa che contiene i dati del fuso orario prima di chiamare il metodo <xref:System.TimeZoneInfo.FromSerializedString%2A>.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Che un riferimento a System. Windows. Forms. dll e System. Core. dll venga aggiunto al progetto.

- Che vengano importati gli spazi dei nomi seguenti:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Panoramica sui fusi orari](../../../docs/standard/datetime/time-zone-overview.md)
- [Procedura: Salvare fusi orari in una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
